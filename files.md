# trackline.dev: setup, step by step

Bought 2026-09-24 at Namecheap. One step at a time; each ends with a check that
it worked. **You** = the user, **me** = Claude.

## The shape

| Address | What | Where |
|---|---|---|
| `https://trackline.dev` | the site, docs, sign-in, dashboard | Vercel project `trackline` |
| `https://www.trackline.dev` | redirects to `trackline.dev` | Vercel |
| `https://api.creovine.com/trackline/v1` | the backend, for now | Creovine EC2 |
| `https://api.trackline.dev` | the backend, later, optional | Creovine EC2 |
| `hello@trackline.dev` | contact address, forwards to your Gmail | Namecheap forwarding |

**Sign-in points at the site, never at the API.** GitHub returns people to
`https://trackline.dev/auth/github/callback`; Google's button needs only the
site's origin. So moving the API later never means touching the Google or GitHub
settings again.

---

## Step 1 · DNS at Namecheap (you)

Namecheap → Domain List → trackline.dev → **Manage** → **Advanced DNS**.

1. **Delete** the parking records Namecheap adds by default: a `CNAME` for `www`
   pointing at `parkingpage.namecheap.com`, and a `URL Redirect` for `@`. Left in
   place they override the records below.
2. **Add** these two:

| Type | Host | Value | TTL |
|---|---|---|---|
| A Record | `@` | `76.76.21.21` | Automatic |
| A Record | `www` | `76.76.21.21` | Automatic |

Keep Namecheap's nameservers ("Namecheap BasicDNS"). Do not switch to Vercel's:
email forwarding and verification records are simpler to manage here.

**Check (me):** `trackline.dev` resolves to Vercel and Vercel shows the domain as
valid. Can take a few minutes, occasionally an hour.

## Step 2 · HTTPS, and www to the bare domain (me)

- Vercel issues the certificate once DNS is right. `.dev` only works over HTTPS,
  so nothing is reachable until then.
- Set `www.trackline.dev` to redirect permanently to `trackline.dev`, so search
  engines see one address.

**Check:** both addresses load over HTTPS and `www` redirects.

## Step 3 · Point everything at the new address (me)

The checklist in `AGENTS.md`, "The site's address":

1. `SITE` in `site/lib/site.ts` becomes `https://trackline.dev`.
2. `site/README.md` address line.
3. `homepage` in the root `package.json` becomes `https://trackline.dev`.
4. The GitHub repo's website field.
5. Redeploy; `git grep` for anything missed.

`trackline-iota.vercel.app` keeps working, so prompts already pasted still do.

**Check:** the copy-prompt and `/install.md` say `trackline.dev`.

## Step 4 · SEO (me, then one thing for you)

Me, in the site:

- Titles and descriptions per page, and a **canonical URL** on every page, so the
  vercel.app copy never competes with trackline.dev in search.
- **Open Graph and Twitter images**: the card that appears when the link is
  shared on LinkedIn, X, Slack or WhatsApp.
- `sitemap.xml` and `robots.txt`.
- Structured data (`SoftwareApplication`), so search engines know it is a
  developer tool.
- `/privacy` and `/terms` pages (needed for Google sign-in in step 7 anyway).

You:

- **Google Search Console** → Add property → **Domain** → `trackline.dev`. It
  gives a `TXT` record; add it in Namecheap Advanced DNS (Host `@`). Then submit
  `https://trackline.dev/sitemap.xml`. Verifying the domain here also helps the
  Google sign-in screen in step 7.
- Optional: Bing Webmaster Tools, which can import from Search Console in one
  click.

**Check:** Search Console shows the domain verified and the sitemap read.

## Step 5 · An email address on the domain (you, optional but recommended)

Namecheap → trackline.dev → **Advanced DNS** → **Mail Settings** → **Email
Forwarding** → forward `hello@trackline.dev` to your personal Gmail. Free. The
privacy page names this address, so nobody has to see a personal one.

**Check:** a test email to `hello@trackline.dev` arrives. (Sent by you, from your
own account, to yourself.)

## Step 6 · Privacy and terms (me drafting, you approving)

Plain pages that say exactly what the cloud plan says: what is sent, what is
never sent, how long it is kept, how to delete it. Required by Google for the
sign-in screen, and honest to have before anyone signs in.

They are drafts written from the product's actual behaviour, not legal advice.

## Step 7 · Google sign-in (you, in Google Cloud)

A **new project** just for trackline, not Lira's or Brydg's: the sign-in screen
shows the project's app name, and it must say trackline.

1. console.cloud.google.com → project picker → **New project** → `trackline`.
2. **Google Auth Platform** (search "Google Auth Platform", or APIs & Services →
   OAuth consent screen) → **Get started**:
   - App name: `trackline`
   - User support email: your Gmail
   - Audience: **External**
   - Contact email: your Gmail
3. **Branding**:
   - App home page: `https://trackline.dev`
   - Privacy policy: `https://trackline.dev/privacy`
   - Terms of service: `https://trackline.dev/terms`
   - Authorised domain: `trackline.dev`
   - Logo: skip for now. Adding one triggers a brand review that can take days,
     and sign-in works without it.
4. **Data access** → scopes: only `openid`, `email` and `profile`. These are
   non-sensitive, so no Google review is needed.
5. **Audience** → **Publish app** (moves it from Testing to In production).
   Without this, only listed test users can sign in.
6. **Clients** → **Create client** → **Web application**, name `trackline web`:
   - Authorised JavaScript origins: `https://trackline.dev` and
     `http://localhost:3000`
   - Authorised redirect URIs: none (the button returns an ID token directly)
7. Send me the **Client ID**. It is public by design; no secret is needed for
   this kind of sign-in.

**Check (me):** the Google button on the site signs you in against the local
backend.

## Step 8 · GitHub sign-in (you)

GitHub → Settings → Developer settings → **OAuth Apps** → New OAuth App.
GitHub allows one callback per app, so two apps:

| | `trackline` | `trackline (local)` |
|---|---|---|
| Homepage URL | `https://trackline.dev` | `http://localhost:3000` |
| Authorization callback URL | `https://trackline.dev/auth/github/callback` | `http://localhost:3000/auth/github/callback` |

For each: **Generate a new client secret**. Put both client IDs and both secrets
in a file in the evalgate folder and tell me; I move them where they belong and
delete the file.

**Check (me):** GitHub sign-in works locally end to end.

## Step 9 · Secrets on the server (you and me)

The backend reads a `/trackline` secret from AWS Secrets Manager in production,
holding the GitHub secrets and trackline's own token signing key. Your laptop's
AWS credentials reach a different AWS account from the server's, so this is
created either in the AWS console (you) or from the server. Decided when we get
there; nothing is deployed before it.

## Later · `api.trackline.dev` (optional)

A DNS record to the Creovine server, a certificate, and an nginx entry. Only if
we want the API under the product's own name; nothing else depends on it.
