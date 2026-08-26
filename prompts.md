# The Headshot Pack

Twenty five prompts that turn three phone selfies into a studio headshot, using
a free ChatGPT account.

Not a filter and not an app subscription. The prompts are the product, and the
reason they cost something is that a free ChatGPT account gives you **two or
three images a day**. You cannot afford to spend one of them finding out that a
prompt was vague.

---

## What this actually does

![Three phone selfies on the left, one studio headshot on the right](IMAGE:hero-before-after)

Left is a phone selfie taken indoors at night, under a lamp, in a checked
shirt. Right is what came back. Same face, same beard, same hairline. A navy
blazer nobody owns and a studio nobody booked.

That took one prompt and about forty seconds.

---

## Before you start

**Take three photographs, in one sitting.**

Not photographs from your camera roll. Photographs from different years, with
different hair and different light, teach the model that all of them are
equally you, and it hands back an average of several of you.

- One straight on, one turned slightly left, one turned slightly right
- Same shirt, same room, same light, same day
- Face the light. A window in daytime beats any lamp
- Phone at eye level or a touch above. Held low widens your jaw, and the model
  will faithfully reproduce that
- Plain wall behind you. No hat, no sunglasses
- Head and shoulders in frame, neutral or slight smile

Ten minutes. Everything else in this pack is built on those three photographs,
so they are the one thing worth doing twice.

---

## How to run these without ruining them

Read this once. It is four rules and each of them is the difference between a
photograph of you and a photograph of somebody else.

**1. One chat for everything.**

Open a new chat in ChatGPT. Upload all three photographs in your first message.
Do not open a new chat for each headshot: the thread is what holds your face
together, and starting fresh loses it.

**2. Every prompt goes back to the originals.**

Each prompt below starts by naming the photographs you uploaded at the top of
the chat. That line is not decoration. It is what stops the model from working
off the last picture it made.

**3. Never edit an edit.**

The single fastest way to ruin your own face. Do not say "now make that one
smart casual". Faces come apart after three or four consecutive edits: skin
goes waxy, features slide, people report looking thirty years older. Paste a
fresh prompt instead. Every time.

**4. Two or three a day, free.**

The quota is a rolling twenty four hours from your first image, not midnight.
Free, Plus and Pro all use the same image model, so a paid plan buys you more
attempts, not better ones. Pick the two prompts you want most and run those.

---

## Which tool, and why it matters more than you would think

![The same prompt and the same photographs, run through ChatGPT and through Gemini](IMAGE:chatgpt-vs-gemini)

Same three photographs. Same prompt, word for word. Two different tools.

The left one is him. The right one is a well lit stranger who happens to have a
similar beard.

Gemini is free and generous, twenty images a day against ChatGPT's two or
three, and for making pictures of things it is excellent. For keeping *your
face*, it was not close. It rounded the jaw, changed the eye shape, and
smoothed the skin until the texture was gone.

**Use ChatGPT for these.** If you only get two images a day, spend them
somewhere they will still be you.

---

## The line that does the most work

![The same prompt with and without the skin tone instructions](IMAGE:tone-comparison)

These two came from the same tool, the same photographs, and prompts that were
identical except for three sentences about skin.

The left one has a warm cast across the forehead and cheeks. It is not
dramatic, and on its own you might not notice. Beside the right one it is
obviously wrong, and the face is subtly rounder with a thinner beard.

The right one names the skin tone, asks for neutral white balance, and tells
the light to expose for deep brown skin rather than for an average face.

This is worth understanding rather than just copying. Image models are trained
on far more light skin than dark, so the defaults are built around it: warm
casts get amplified, and "brighten the face" quietly means "lighten the
person". Researchers have documented headshot tools lightening dark skin and
in one case turning brown eyes blue. The correction is not a trick. It is
telling the model the thing it was never shown enough of.

**Every prompt in this pack carries that block.** If you write your own, carry
it too.

---

# The prompts

Twenty five, in six groups. Each one is complete: paste it as it is, change
nothing, and it will work in a chat where your three photographs are already
uploaded.

The parts in **bold** in the notes are the parts worth changing if you want
something slightly different.

---

## Corporate and formal

For LinkedIn, a company directory, a bio page, a conference programme, a bank.

### 1. The standard

The one to run first if you only run one. Neutral, unarguable, works anywhere.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one professional headshot of this same person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1, face filling about 60% of the frame,
centred. 85mm portrait lens, camera at eye level, taken from very slightly
above the eye line.

Wearing: a well fitted navy blazer over a plain white crew neck shirt.

Background: smooth mid grey studio backdrop, softly out of focus.

Lighting: a large softbox at 45 degrees as the key, a reflector filling the
shadow side so nothing goes black, and a subtle rim light separating the head
from the background. Expose for deep brown skin so the face is fully detailed
rather than underexposed. Neutral white balance, no orange or yellow cast, no
blown out highlights on the forehead or nose.

Expression: relaxed, slight closed mouth smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin, no beauty filter, no reshaping.
```

### 2. Executive, dark suit

Heavier and more formal. **Charcoal** can be black or deep navy.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one executive portrait of this same person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: chest up, square 1:1, slightly wider than a tight headshot so the
shoulders read. 85mm lens, camera at eye level.

Wearing: a charcoal two piece suit, crisp white shirt, no tie, top button
undone.

Background: deep charcoal seamless, falling off to near black at the edges.

Lighting: single large softbox slightly above and to the left, a dark reflector
on the right to deepen the shadow side, gentle rim light along the jaw. Expose
for deep brown skin so the face holds detail against the dark background.
Neutral white balance, no orange cast.

Expression: composed, no smile, direct eye contact, chin level.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin, no beauty filter.
```

### 3. Corporate on white

For a site that needs the background removed, or a press kit.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one professional headshot of this same person on
a pure white background.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1, face filling about 60% of the frame.
85mm lens, eye level.

Wearing: a light grey blazer over a white shirt, open collar.

Background: clean pure white, evenly lit, no shadow falling on it, edges of the
hair clearly separated from the white so the image can be cut out.

Lighting: two softboxes at 45 degrees either side for even, shadowless light on
the face, plus a hair light for separation. Expose for deep brown skin: the
face must be fully lit and detailed, never a silhouette against the white.
Neutral white balance, no orange cast, no blown out forehead.

Expression: open, warm, slight smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 4. The office window

Corporate without a studio. Reads as taken at work.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one professional portrait of this same person in
an office.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and upper chest, square 1:1, subject slightly off centre. 85mm
lens at f2, eye level.

Wearing: a navy blazer over a pale blue shirt, no tie.

Background: a modern office interior thrown well out of focus, with a large
window on one side giving soft daylight and a suggestion of a city beyond.

Lighting: daylight from the window as the key on one side of the face, a
bounce card filling the other so nothing is lost to shadow. Expose for deep
brown skin so the window does not blow out behind him and leave the face dark.
Neutral white balance.

Expression: friendly, natural half smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

![Corporate and formal](IMAGE:section-corporate)

---

## Smart casual

For a personal site, a newsletter, a podcast page, a modern company that does
not wear suits.

### 5. The knit

Warm and approachable without being scruffy.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one relaxed professional portrait of this same
person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1, face filling about 55% of the frame.
85mm lens, eye level.

Wearing: a fine gauge charcoal crew neck knit, no jacket.

Background: warm mid grey studio backdrop with a soft gradient, out of focus.

Lighting: a large softbox close and slightly above for soft wrapping light, a
white reflector low to lift the shadows under the jaw, subtle hair light.
Expose for deep brown skin so the face is fully detailed. Neutral white
balance, no orange cast.

Expression: relaxed, genuine warm smile, slight head tilt, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin, no beauty filter.
```

### 6. Denim shirt

The least formal thing that still reads as professional.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one relaxed portrait of this same person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1. 85mm lens at f2, eye level.

Wearing: a well fitted mid blue denim shirt, top button open, sleeves not
visible.

Background: soft warm beige backdrop, gently out of focus.

Lighting: single large softbox at 45 degrees, generous fill on the shadow side,
warm but neutral. Expose for deep brown skin so the face holds full detail.
Neutral white balance, no orange or yellow cast.

Expression: easy, open smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 7. Black on black

Quietly striking. Good for a personal site header.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one portrait of this same person in low key
lighting.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1, subject centred. 85mm lens, eye level.

Wearing: a plain black crew neck.

Background: black, falling to complete darkness at the edges.

Lighting: this is the hard part and it matters. Two rim lights, one on each
side, drawing bright edges along the cheekbones, jaw and shoulders to separate
him from the black. A soft frontal fill at low power so the face is clearly
readable and never lost in the background. Deep brown skin against black
requires deliberate separation and generous fill: the face must be fully
visible with detail in the shadows, not a silhouette. Neutral white balance.

Expression: calm, no smile, direct eye contact.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin, no crushed blacks on the face.
```

### 8. Bright and open

For a page that needs to feel light. **White or cream** on white.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one bright, airy portrait of this same person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1, generous space above the head. 85mm
lens, eye level.

Wearing: a cream linen shirt, open collar, relaxed fit.

Background: soft off white, brightly and evenly lit, very slightly out of
focus.

Lighting: broad soft light from the front and above, minimal shadow, high key
overall. Expose carefully for deep brown skin against a bright background: the
face must be properly exposed and full of detail, not darkened to protect the
highlights. Neutral white balance, no orange cast, no blown out forehead or
nose.

Expression: warm, relaxed, easy smile.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

![Smart casual](IMAGE:section-smart-casual)

---

## Founder and startup

For a pitch deck, an about page, a press mention, an investor update.

### 9. The founder portrait

Confident without a suit. The standard startup about page shot.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one founder portrait of this same person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and upper chest, square 1:1, subject slightly off centre with
space to look into. 85mm lens at f1.8, eye level.

Wearing: a dark grey zip up merino sweater over a plain black t-shirt.

Background: a workspace thrown far out of focus, warm neutral tones, no
readable detail.

Lighting: soft directional key from one side, generous fill, gentle falloff
into the background. Expose for deep brown skin so the face is the brightest
and most detailed thing in the frame. Neutral white balance, no orange cast.

Expression: assured, closed mouth half smile, direct eye contact.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 10. Arms folded, wide

For a header, a press page, anywhere that needs a wider crop.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one three quarter length portrait of this same
person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: from the waist up, 4:5 portrait orientation, standing, arms lightly
folded. 50mm lens, camera at chest height. Face must remain sharp and
prominent.

Wearing: a navy overshirt over a white t-shirt, dark trousers.

Background: a plain concrete or plaster wall, softly out of focus, neutral
grey.

Lighting: large soft key from the front left, fill from the right, even across
the body. Expose for deep brown skin so the face is fully detailed and never
darker than the wall behind it. Neutral white balance.

Expression: settled, calm, slight smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin, correct hands and arms.
```

### 11. Working, candid

Reads as caught mid work rather than posed. Good beside a story.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one candid working portrait of this same person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, 4:5, subject off centre, looking slightly away
from camera rather than at it. 85mm lens at f1.8.

Wearing: a plain dark t-shirt.

Background: a desk and screen far out of focus, cool ambient tones.

Lighting: soft daylight from one side as the key, a screen giving a faint cool
fill on the shadow side, deliberate but subtle. Expose for deep brown skin so
the face is properly lit rather than falling into shadow. Neutral white
balance overall, no orange cast.

Expression: thinking, unposed, mouth relaxed and closed.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 12. Editorial, magazine

For a feature, an interview, a serious profile.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one editorial portrait of this same person in the
style of a business magazine profile.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, 4:5, tight and slightly asymmetric. 85mm lens.

Wearing: a black roll neck.

Background: deep desaturated teal, evenly lit, no texture.

Lighting: a single key light high and to one side giving defined but soft
shadow under the cheekbone, controlled fill so the shadow side still holds
detail, no rim light. Expose for deep brown skin: the lit side must be rich
and detailed and the shadow side must never go to black. Neutral white
balance.

Expression: serious, considered, no smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. Skin should look
like skin, with visible texture. No smoothing, no plastic finish.
```

![Founder and startup](IMAGE:section-founder)

---

## Creative and studio

For a portfolio, a design or media profile, anything where a grey backdrop
would be dull.

### 13. Coloured backdrop

**Deep blue** is the safe one. Burgundy, forest green and warm ochre also work.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one studio portrait of this same person on a
coloured backdrop.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1. 85mm lens, eye level.

Wearing: a plain white t-shirt under an unstructured sand coloured jacket.

Background: a rich deep blue seamless paper backdrop, evenly lit, slightly out
of focus.

Lighting: soft key at 45 degrees, white fill card on the opposite side, and a
separate light on the background so the blue stays saturated rather than going
muddy. Expose for deep brown skin so the face is fully detailed and does not
sit darker than the backdrop. Neutral white balance on the skin even though
the background is coloured, no colour cast on the face.

Expression: open, relaxed, slight smile.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 14. Window light

The simplest good light there is. Warm, soft, believable.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one natural light portrait of this same person
beside a window.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, 4:5, subject turned slightly towards the light.
85mm lens at f2.

Wearing: an oatmeal coloured crew neck.

Background: a plain interior wall in soft shade, well out of focus.

Lighting: large soft daylight from a window to one side, a bounce card on the
other lifting the shadows so the face reads evenly. Expose for deep brown
skin: the lit side detailed, the shadow side still fully visible. Neutral
white balance, no orange or yellow cast from the interior.

Expression: quiet, natural, small smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 15. Black and white

Timeless, and it sidesteps every colour problem at once.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one black and white portrait of this same person.

Identity comes first. Keep the exact facial structure from the source
photographs. Do not reshape the nose, lips, jaw or eyes. In monochrome, render
his skin at its true relative brightness: deep and rich with full detail in
both highlights and shadows. Do not render dark skin as a flat dark mass and
do not artificially brighten it.

Framing: head and shoulders, square 1:1. 85mm lens, eye level.

Wearing: a plain dark shirt, open collar.

Background: mid grey, softly graded, out of focus.

Lighting: classic single softbox at 45 degrees slightly above, reflector fill
below, gentle rim light along the jaw for separation. Full tonal range from
deep black to clean white with the face sitting in the detailed midtones.

Expression: still, composed, no smile, direct eye contact.

Photographic black and white, real film character. Keep natural skin texture
and pores. No smoothing, no plastic finish, no crushed blacks on the face.
```

### 16. Colour gel

Modern, for a creative or music profile. **Teal and magenta** can be any pair.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one contemporary studio portrait of this same
person with coloured lighting.

Identity comes first. Reproduce the underlying skin tone from the source
photographs. Do not lighten or alter the skin itself. Do not reshape the nose,
lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1. 85mm lens, eye level.

Wearing: a plain black t-shirt.

Background: dark neutral, unlit.

Lighting: a neutral white key light on the face so the skin keeps its true
colour and full detail, plus a teal rim from the left and a magenta rim from
the right touching only the edges of the head and shoulders. The colour is on
the edges, not on the face. Expose for deep brown skin so the face is clearly
and fully lit, never a dark shape between two coloured edges.

Expression: still, confident, no smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

![Creative and studio](IMAGE:section-creative)

---

## Speaker and stage

For a conference programme, an event page, a course or workshop listing.

### 17. Conference speaker

The standard event programme photograph.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one conference speaker portrait of this same
person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1, face filling about 60% of the frame.
85mm lens, eye level.

Wearing: a dark blazer over a plain black t-shirt.

Background: a large blurred auditorium with soft bokeh from stage lights, cool
neutral tones, nothing readable.

Lighting: clean soft key from the front, gentle fill, subtle rim from the stage
lights behind. Expose for deep brown skin so the face is clearly the brightest
and most detailed part of the frame. Neutral white balance, no orange cast
from the stage lighting.

Expression: engaged, warm, mid smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 18. Mid talk

Reads as a real moment rather than a portrait. Good beside a bio.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one candid photograph of this same person
speaking to an audience.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and upper chest, 4:5, subject off centre, looking off camera as
if addressing a room. 135mm lens at f2, shot from a distance.

Wearing: a dark grey blazer, no tie.

Background: a stage, deeply out of focus, warm ambient light.

Lighting: directional stage key from the front left, soft fill, slight rim.
Expose for deep brown skin so the face holds full detail against the darker
stage. Neutral white balance on the skin, no heavy orange cast.

Expression: mid sentence, animated, natural, mouth slightly open, eyes off
camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 19. Teaching

For a course page, a workshop, a training listing.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one portrait of this same person in a teaching
setting.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, 4:5, subject slightly off centre. 85mm lens at
f2.

Wearing: a plain navy crew neck.

Background: a bright modern classroom or studio, well out of focus, with a
large window giving daylight.

Lighting: soft daylight as the key from the side, bounce fill on the shadow
side, bright and even overall. Expose for deep brown skin so the daylight
behind does not leave the face underexposed. Neutral white balance.

Expression: approachable, mid explanation, warm open smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 20. Panel, seated

For an event page or a podcast listing.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one seated portrait of this same person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: from the chest up, 4:5, seated and leaning very slightly forward.
85mm lens, camera at eye level.

Wearing: a charcoal blazer over a white t-shirt.

Background: a dark neutral set, softly lit, well out of focus.

Lighting: soft key from the front left, fill from the right, subtle rim along
the shoulder. Expose for deep brown skin so the face is fully detailed against
the darker set. Neutral white balance, no orange cast.

Expression: listening, attentive, closed mouth half smile.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin, correct posture and shoulders.
```

![Speaker and stage](IMAGE:section-speaker)

---

## Outdoor and natural light

For a personal site, a newsletter, a social profile. Softer than a studio and
harder to get right, which is why the light instructions here are longer.

### 21. Golden hour

The most flattering light there is, and the easiest to overcook.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one outdoor portrait of this same person in late
afternoon light.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten or alter the skin. Do not reshape the nose, lips,
jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, 4:5. 85mm lens at f1.8.

Wearing: a plain white t-shirt under an open olive overshirt.

Background: an outdoor scene thrown completely out of focus, warm greens and
soft light.

Lighting: low late afternoon sun behind and to one side giving a warm rim on
the hair and shoulder, with a large bounce filling the face from the front.
The warm light must stay on the rim and the background: keep the face itself
at neutral white balance with its true skin tone, not tinted orange. Expose
for deep brown skin so the face is fully detailed rather than a shadow against
a bright sky.

Expression: relaxed, natural, easy smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin, no heavy orange grade.
```

### 22. Open shade

The reliable outdoor one. Even light, no squinting, works every time.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one outdoor portrait of this same person in open
shade.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, square 1:1. 85mm lens at f2.

Wearing: a mid grey crew neck.

Background: a plain wall in shade, softly out of focus, neutral tones.

Lighting: soft even shade light with no direct sun, open sky as the source so
the light is broad and shadowless. Expose for deep brown skin so the face is
bright and fully detailed. Neutral white balance: shade light goes blue, so
correct it rather than leaving a cool cast on the skin.

Expression: calm, natural, small smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 23. City street

Urban and modern. **Any city** works, the background is unreadable anyway.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one street portrait of this same person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and upper chest, 4:5, subject off centre. 85mm lens at f1.8,
shot from across a pavement.

Wearing: a black bomber jacket over a white t-shirt.

Background: a city street completely out of focus, buildings and light
reduced to soft shapes, cool neutral tones.

Lighting: soft overcast daylight from the front, no hard shadow, gentle
directional falloff. Expose for deep brown skin so the face is fully detailed
against the brighter street behind. Neutral white balance, no blue cast from
the overcast sky.

Expression: settled, closed mouth, direct eye contact.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 24. Café table

Warm and human. Good for a newsletter or an about page.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one relaxed portrait of this same person sitting
at a café table.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: head and shoulders, 4:5, subject off centre with the table edge just
visible. 85mm lens at f1.8.

Wearing: a soft grey knit.

Background: a café interior far out of focus, warm ambient tones, a window
giving daylight behind.

Lighting: window daylight from the side as the key, warm interior light only
as background ambience, bounce fill on the shadow side of the face. Expose for
deep brown skin so the window behind does not blow out and leave the face
dark. Neutral white balance on the skin despite the warm room.

Expression: at ease, mid conversation, natural smile, eyes to camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin.
```

### 25. Overcast, wide

The last one, and the most forgiving. **4:5 or 16:9** for a header.

```
Using the original photographs I uploaded at the start of this chat as the
identity reference, generate one wide outdoor portrait of this same person.

Identity comes first. Reproduce the exact skin tone from the source
photographs. Do not lighten, brighten or warm the skin. Do not reshape the
nose, lips, jaw or eyes, and keep the eye colour exactly as it is.

Framing: from the waist up, 16:9 landscape, subject to one side with open
space beside him for text. 50mm lens at f2.8. Face must remain sharp and
clearly readable despite the wider crop.

Wearing: a dark green jacket over a plain black t-shirt.

Background: an outdoor space under overcast sky, softly out of focus, muted
natural tones.

Lighting: broad even overcast daylight, soft and directionless, gentle
modelling on the face from a slight angle. Expose for deep brown skin so the
face is bright and detailed against the pale sky rather than underexposed.
Neutral white balance, no blue cast.

Expression: calm, unhurried, closed mouth, looking slightly off camera.

Photographic and real. Keep natural skin texture and pores. No skin smoothing,
no plastic or waxy skin, correct hands if visible.
```

![Outdoor and natural light](IMAGE:section-outdoor)

---

## When something goes wrong

**It does not look like me.** You are almost certainly editing an edit. Go back
and paste a fresh prompt instead of asking it to change the last image. If it
still misses, your three source photographs are probably from different days.

**The skin looks orange.** The prompt lost its white balance line. Paste the
whole prompt again rather than a shortened version.

**The face is waxy and smooth.** Something dropped the texture instructions.
The last four lines of every prompt are doing real work. Keep them.

**The forehead and nose are blown out.** Add this line to the lighting
paragraph: `soften the key light and lower its power so there are no specular
highlights on the forehead, nose or cheekbones`.

**The face is too dark.** Add: `raise the fill light so the shadow side of the
face holds full detail`.

**It changed my hairline or my beard.** Add to the identity paragraph: `keep
the exact hairline, hair shape and beard shape from the source photographs`.

**I ran out of images.** The quota is a rolling twenty four hours from your
first generation, not midnight. Come back tomorrow at the same time.

---

## What you can do with these

The images are yours. Use them on LinkedIn, on your site, in a deck, on a
programme, anywhere you would use a photograph of yourself.

Two honest notes. These are AI generated portraits of you, not photographs, and
a few contexts ask you to say so: press credentials, some journalism, some
official documents. And they are built from your own face, so do not run them
on somebody else's photographs without asking.

---

*The Headshot Pack, from Creovine Academy.*
