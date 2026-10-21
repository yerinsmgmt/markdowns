# 17. Launch trailer: audit and plan (21 October 2026)

Owner, 21 October:
> "Create a launch video or a trailer video … mix real-life playing and the graphics … short clips of different scenes … play match (table tennis and kpako), bounce, practice … different camera angles … the opponent using different styles … very stylish serving … the ball touching the net, hovering over the board … overview, camera at the top, a drone watching … very clean, very professional, no gap, no glitching … if the graphics need improvement, improve it (the Kpako stick looks plain) … write the document first."

This is the plan only. **Nothing is built or rendered yet.** The owner reads this, changes what they want, and says go.

Clips go to **`~/Desktop/pac9-trailer/`**. The folder exists now, with two stills of the current look in `00-current-look/`.

---

## 1. The idea in one paragraph

Every clip is **the real game engine** (three.js, the real players, the real ball physics), filmed with a new **cinematic camera** and a **frame-by-frame recorder**. Each clip is rendered one frame at a time and stitched at a perfect 60 fps, so it is smooth even on this 2019 MacBook. Anything we improve for the trailer goes **into the game itself** (as an "Ultra" quality setting where it is too heavy for normal play). So what people see in the trailer is what they get when they play. The owner cuts the clips together with their real-life phone footage.

---

## 2. Audit: what we have today

### Modes we can film

| Mode | What it shows today | Usable for the trailer? |
|---|---|---|
| **Play Match: Table tennis** | Indoor hall, blue table, Kofi and Tunde. `?attract` already plays AI vs AI with both bodies visible and no UI | Yes. Best source of rallies |
| **Play Match: Kpako** | Bench with a plank net, dusty compound, water tank, crates, palms, house | Yes, after the upgrades in section 3 |
| **Bounce** | Bat and ball on a dark navy background, target zones, score and combo | Yes, but the background is bare |
| **Practice (ball machine)** | Same hall, ball machine, target zones, no player body | Yes, with a better machine and a player in shot |

### What already looks good
- The two players (Kofi and Tunde): their bodies, skin and kit read well.
- The stroke animations, including real contact timing on the ball.
- The hall layout and the African-pattern PAC9 barrier boards.
- The Kpako idea itself: the ground colour and warm light.

### What looks plain (checked in code and in the stills)

**Rendering, all scenes**
- No post-processing: no glow, no soft shadows in corners, no depth of field. The light strips and windows look like flat paint.
- Real shadows only reach about 3 m around the table. Walls, props and most of the Kpako compound have none.
- The ready-made studio lighting map (Poly Haven HDRI) is in the repo but not used.
- A bright white smear on the hall floor, bottom right of the default view (see `00-current-look/attract-center.png`).
- Default quality renders at 1× resolution. Even "high" caps at 1.5×.

**Table tennis hall**
- Walls and ceiling are flat-colour boxes.
- The windows are cream rectangles with nothing outside them.
- Every advert board shows the same placeholder; the scoreboard is plain Arial with no names.
- The floor pattern visibly repeats every 2 m.
- No crowd. This is on purpose: the standing rule is no people until they are high quality.

**Table, bat, ball**
- **Table:** a flat blue top with no edge bevel, and stick legs.
- **Bat:** plain cylinders, with no rubber texture.
- **Ball:** no logo, so spin is invisible.
- **Trails:** only 1-pixel lines, and only in replay and practice.
- **Hit effect:** one small puff. There is no dust or spark on a bounce.

**Kpako compound** (the owner's point about the stick is right)
- **The plank "net"** is one sharp, untextured dark-brown box with no grain, wear, rough edges or anything holding it up. It looks pasted on.
- **The bench's wood grain** most likely runs the wrong way and is stretched about 17 times along the bench. It is hard to see from behind the player, but obvious in any close-up.
- **The palms** are three flat cut-out cards, and they look like cards from the side.
- **The sky** is a flat picture glued to the screen. It does not move when the camera moves, which kills any drone shot.
- **The light** is the indoor hall's lighting, so there are no long late-sun shadows, though the Kpako doc asks for them.
- **The walls** have a stretched texture with odd blotches. The props are plain boxes.
- **The players wear the tournament kit,** not local clothes (the Kpako doc plans local outfits).

**Cameras**
- Only behind-the-player views. There is no side-on (TV) view and no free or cinematic camera.
- The old `?shot=` setting no longer does anything.
- Attract mode skips replays and the intro orbit.

**Bounce and Practice**
- **Bounce:** a bare dark background with no shadows.
- **The ball machine:** a box with a tube on it.
- Both open on the phone-pairing screen, so filming needs a scripted pretend phone. The existing test scripts already do this.

### The animation pack (Motion Cast Vol. 2)

**What it contains:** 131 Blender files, cut into 245 clips. All 245 are already converted for our players and sitting in the game, but only 78 are switched on in matches.

**The pack's best trailer moves:**

| Move | Clips | In matches today? |
|---|---|---|
| Hammer serve (the most stylish serve in the pack) | 1 | No |
| Flat serve | 1 | No |
| Backhand topspin serves | 3 | No |
| Side-backspin and push serves | 5 | Partly |
| Forehand smashes | 5 | 1 of 5 |
| Backhand smashes | 4 | No |
| Flips, including a **double flip** | 8 | Partly |
| Forehand and backhand slide (hook) spins, including multi-shot runs | 10 | Backhand only |
| Topspin loops | 5 | Yes |
| **Ball-choice ritual** before serving (bouncing, picking a ball) | 5 | 3 |
| Warm-up routines, about 15–20 s each | 2 | No |
| **Point won** celebrations | 12 | 1 |
| **Point lost** reactions | 10 | No |
| Full raw rallies, 50–100 s each | 4 | No |

**What the pack does not have:**
- pendulum, reverse, tomahawk or high-toss serves;
- lobs and chops;
- a walk-on, a handshake or a bow.

**Where the missing moves can come from:**
- **Walking, Victory and Cheering:** these already exist as Mixamo files in the Monkey Post folder, and Mixamo uses the same skeleton as our players.
- **Handshake:** Mixamo has handshake clips, but they need downloading with an Adobe sign-in.

**Licence:**
- **Motion Cast:** Superhive Royalty Free allows commercial use, so rendering the moves into a promo video is fine. We must never share the `.blend` files themselves.
- **Shorts and trainers:** they are CC-BY, so the video description or end card should credit them (the credit text is in `apps/web/public/ASSET-CREDITS.txt`).

---

## 3. Improvements before filming

Ranked by how much they show on camera. **P1** must happen before any clip is final. **P2** is worth doing if time allows. **P3** is a proposal for the owner.

### Kpako (biggest gain)

| # | Improvement | How | Priority |
|---|---|---|---|
| K1 | **A real plank net:** a rough-sawn board with splintered, uneven edges, worn grain, a nail or two, a chip out of the top, and two small wooden wedges or bricks holding it upright | Blender model and textures (like the Kpako paddle) | P1 |
| K2 | **Fix the bench's wood grain** so it runs along the bench, with worn edges, a darker sweat-worn middle, and nail heads | Fix the texture mapping, plus a Blender texture bake | P1 |
| K3 | **A real sky dome** that moves with the camera, with a warm low sun | three.js sky dome | P1 |
| K4 | **Outdoor light:** a warm sun with long shadows over the whole compound, plus outdoor (not studio) fill light | Wider shadow area, plus the sky as the lighting map | P1 |
| K5 | **3D palms and a tree** in place of the flat cards | Blender low-poly plants, or a free CC0 model | P1 |
| K6 | **Dust:** floating specks in the sun, and a dust puff when the ball lands | Particles | P2 |
| K7 | **More life in the props:** a parked motorbike, plastic chairs, a clothesline, an electric pole and wires, a cleaner wall texture with real paint peeling | Blender and CC0 models | P2 |
| K8 | **Local outfits for Kofi and Tunde:** a singlet or plain tee, older shorts, sandals or worn trainers | Blender, the planned "painted kit" job from the Kpako doc | P2 |
| K9 | **Onlookers** around the bench | Only if they reach high quality (standing rule). Owner's call | P3 |

### Table tennis hall

| # | Improvement | How | Priority |
|---|---|---|---|
| H1 | **An "Ultra" quality setting** (also used for filming): soft glow on lights and the hittable ball, ambient shadowing, sharper edges, 2× resolution, and real shadows across the whole hall | three.js post-processing. Off by default; default quality is unchanged | P1 |
| H2 | **Remove the white floor smear**, and add a floor texture with less obvious repeats plus a soft reflection | Material fix | P1 |
| H3 | **Use the HDRI lighting map** that is already in the repo, for real reflections on the table and players | Load the existing file | P1 |
| H4 | **A better table:** a rounded edge, a fine surface texture, a proper steel undercarriage and wheels, and a small PAC9 mark on the side | Blender model | P1 |
| H5 | **A better bat:** rubber texture, edge tape, a shaped handle | Blender, the same treatment as the Kpako paddle | P1 |
| H6 | **Ball with a small logo** so spin shows; a soft trail ribbon (not a 1-pixel line) | Code | P1 |
| H7 | **Glowing light fixtures and windows** with a soft sky outside, and dust in the light shafts | Code and textures | P2 |
| H8 | **A broadcast scoreboard** with player names, games and the server | Canvas texture | P2 |
| H9 | **Hall dressing without people:** an umpire's table, towel boxes, team benches, banners and flags in pac9 colours | Blender and code | P2 |
| H10 | A crowd | Only if high quality (standing rule). Owner's call | P3 |

### Bounce and Practice

| # | Improvement | How | Priority |
|---|---|---|---|
| B1 | **Bounce staging:** a soft-lit studio look instead of the flat void, with a real shadow, a sparkle burst when a zone is hit, and a bigger "FLIP!" moment | Code | P1 |
| P1 | **A real ball machine:** a tripod robot with a ball hopper and a spinning head, generic with no brand | Blender model | P1 |
| P2 | **A player in Practice shots,** hitting the machine's balls, so the trailer shows a person training (the game itself stays as it is) | Trailer camera plus the player animator | P1 |

### Moves to add to the game (so the trailer shows real moves)

| # | Move | Source | Priority |
|---|---|---|---|
| M1 | Hammer, flat and backhand-topspin serves, plus the ball-choice ritual before serving | Already in the game files; switch them on | P1 |
| M2 | Backhand smashes, all forehand smashes, double flip, forehand slide spins | Already in the files; switch them on | P1 |
| M3 | Point won celebrations and point lost reactions after each point | Already in the files. They play today only in a review mode, so they need wiring into normal matches | P1 |
| M4 | **Warm-up and walk-on:** both players walk in, warm up, then take position | Pack warm-ups plus the Mixamo walk (already on this Mac) | P2 |
| M5 | **Handshake at the net** at match end | Mixamo handshake. **Owner action:** sign in to Mixamo once and download it (I'll give the exact clip). The alternative, hand-posing it in Blender, looks stiffer | P2 |
| M6 | Pendulum, tomahawk and high-toss serves; lobs and chops | **Not in the pack.** Options: film a real player and convert it (Rokoko Vision, Move.ai), or buy a second pack. Owner's call | P3 |

---

## 4. How the clips are made

1. **A trailer mode** (`play.html?trailer=<shot>`, practice and bounce too). It is dev-only and never on the live site. It:
   - hides all on-screen text and buttons;
   - turns on Ultra quality;
   - runs a named shot script.
2. **A cinematic camera,** with keyframed paths, smooth easing and a choice of focus (ball, player, hand, bat, net). Camera moves:
   - **Dolly:** slides along a track.
   - **Orbit:** circles a subject.
   - **Crane:** rises or falls.
   - **Drone:** a high, slow circle around the whole venue.
   - **Top-down:** straight above the table.
   - **Net-level:** a low camera at net height.
   - **Hand close-up:** tight on the hand and bat.
   - **Broadcast side view:** the classic TV angle.
   - **Ball-follow:** tracks the ball through the air.

   Depth of field is used for close-ups.
3. **A director for each shot:**
   - It chooses the server, the serve type, the shots each player plays (forehand smash, backhand flip and so on) and when the point ends.
   - It uses the same match simulation as the game. Rallies are repeatable, so a re-render is identical.
   - Special moments are found by searching seeds or by steering the AI's aim:
     - the ball clipping the net cord and dribbling over;
     - the ball skimming just over the net;
     - an edge ball.
4. **The frame-by-frame recorder:**
   - Playwright drives Chrome with a fake clock that moves exactly 1/60 s per frame (the method used by timecut and CCapture).
   - Every frame is saved, and then ffmpeg joins them into an MP4.
   - The Mac's speed no longer matters: no dropped frames, no stutter, no glitches.
   - Slow-motion versions come almost free (render at 120 or 240 fps and play at 60), but only if the owner wants them.
5. **Bounce and Practice:** a scripted pretend phone inside the page, so the bat motion is smooth and repeatable.

### Lessons from the Monkey Post trailer (more than 1M views on X)

The Monkey Post session shared what worked for its trailer, which used the same three.js stack and the same frame-by-frame method. These points are added to the plan.

**Capture**
- **Use the Mac's real graphics chip.** Launch Chrome with `--use-angle=metal --enable-gpu --ignore-gpu-blocklist`. Without these flags, Chrome falls back to software rendering and crawls.
- **Grab frames directly from Chrome** (the DevTools `Page.captureScreenshot` command) and feed them straight to ffmpeg.
- **4K for hero shots only:** a 1920×1080 window at 2× pixel density gives 3840×2160 frames, which stay sharp when cropped. On this Mac, every clip is made at 1080p, and only the hero shots the owner picks from the contact sheet are rendered again in 4K.
- **Motion blur** makes a fast ball look real instead of strobing, and it is capture-only. **Monkey Post did not ship this, so it is untested reasoning to prove on our first test clip:**
  - Average the in-between frames in linear light, in a half-float render target before tone mapping, then apply tone mapping, sRGB and bloom once. Averaging finished screenshots darkens and muddies the glowing ball.
  - Use a 180° shutter: spread the in-between frames over the first half of each 1/60 s. Our 240 Hz simulation gives exactly 2 steps for 180° or 4 for 360°, so no interpolation is needed.
  - In slow motion, the shutter stays the same in output time, so it is shorter in game time.
  - The animation, the simulation and the particles must all step on the fake clock. If a fast arm shows separate copies instead of a smooth blur, something is still on real time.
  - If the streak is too faint, raise the ball's glow in trailer mode. Never brighten after averaging.
  - Use it only on rally, ball and smash shots. Never on calm beauty shots or anything with text.
  - On this Mac, blurred shots may need rendering at 1.5× instead of 2×.
- **Slow motion:** move the game forward by a fraction of a frame per captured frame. With the fixed 240 Hz simulation, only **2× (2 steps per frame) and 4× (1 step per frame)** are clean. Other factors (3×, 8×) give uneven steps that judder, unless the renderer blends between simulation states. Motion blur has the same rule.
- **Sound:** each clip is saved with an event log next to it, listing the frame of every bat hit, table bounce, net touch and point won. The game's real hit sounds can then be dropped onto exactly those frames in the edit, since the sound of the hits is half the feel of table tennis.
- **Several takes per shot,** with a quick contact sheet (`ffmpeg -vf fps=2,scale=480:-1,tile=6x2`) to pick the best one.
- **Player matte:** the same frames rendered again with only the players, white on black. In the edit, text can then sit behind the players.
- **Text cards:** rendered from HTML on the same frame clock to ProRes 4444 with a transparent background, in the game's own font and colours.

**Camera rigs:** three more are added to the list in point 2.
- **Tele:** a very long lens from far away (a field of view of 8–13°). It flattens the background, which suits rallies.
- **Ball cam:** follows the ball with a long lens.
- **Bat close-up at contact.**

Every rig smooths its movement so it never jerks.

**Pitfalls to avoid**
- Call `camera.updateMatrixWorld()` before any screen-position maths inside the per-frame hook. Otherwise the result is one frame stale.
- Keep close cameras a minimum distance from players' bodies, and turn off frustum culling on the players so limbs do not vanish at the edge of a close shot.
- Re-apply camera and scene changes every frame, because game timers and late-loading textures can undo them.
- Wait for a page to load plus a fixed settle time, never for "network idle". Then also wait for the game's own "ready" signal, because textures that load late can undo trailer changes.
- **Prime the camera:** snap it to its first keyframe, then run 0.3–0.5 s without recording. Otherwise the smoothing swings the camera in from wherever it was on the first frames.
- **Start each clip from an event, not a time:** the director starts recording a set time before a known event (serve contact, the net-cord touch), so the 1 s handles at each end land right.
- **Check camera paths against the scenery** before recording: draw the path in the debug view, and enforce a minimum distance from every mesh. Crane and drone moves through the hall roof, the compound walls or the players are the risky ones.
- **Score seeds for spectacle,** not only for the event happening: ball speed, rally length, a lunge, a smash winner. A technically correct but gentle point is the weakest kind of shot.
- **Depth of field follows the subject** (the ball, or the bat at contact) every frame. It is only used on close-ups.
- **Text cards** wait for `document.fonts.ready` before the first frame, or the first frames appear in the wrong font.
- Check the first and last frame of every shot for props blocking the view.

**Graphics (all capture-only, behind the trailer flag)**
- A rim light that separates the players from the background.
- Sharper texture filtering (anisotropy 8) on the table top and floor, which the camera sees at a grazing angle.
- Signs and light strips that glow (unlit materials).
- Larger shadow maps and full resolution.
- Bloom and depth of field.

**Blender:** Monkey Post found that filming the real engine was faster and more authentic than rendering in Blender. Here too, Blender is only for building models (the plank net, table, ball machine and plants), not for rendering clips.

**Editing advice for the owner**
- The first 2 seconds decide whether people keep watching. Open on action, never on a logo.
- Cut on the beat every 1–2 s, with a different camera for each cut.
- Use slow motion going into an impact, and real speed at the moment of contact.

### Output format

- **Video:** 1920×1080, 60 fps, high-bitrate H.264 MP4.
- **Optional extras:**
  - 4K renders of the hero shots the owner picks (slow on this Mac, but no quality cost);
  - ProRes versions for editing.
- **Length:** 4–8 s per clip, with 1 s of extra footage at each end so cuts have room.
- **Clean and HUD versions:** clean clips have no score or text on screen. A few clips also come in a version showing the game's on-screen display, for "this is the real game" moments.
- **File names:** `<section>/<number>-<short-name>-<camera>-t<take>.mp4`, for example `A-table-tennis/A04-hammer-serve-lowside-t2.mp4`.
- **A best-frame still with every clip:** a full-resolution PNG with the same name, for thumbnails and social posts.
- **Contact sheet:** `contact-sheet.html` in the folder, with a thumbnail and a one-line description per clip, so choosing clips is quick.

---

## 5. The shot list (first batch)

Each line is one clip. "Opp" means the far player, "Near" the near one.

### A. Table tennis (indoor hall): `A-table-tennis/`

| # | Shot | Camera | What happens |
|---|---|---|---|
| A01 | Empty hall reveal | Slow dolly in from the entrance, lights glowing | Table waiting, no players |
| A02 | Walk-on | Low, tracking alongside | Kofi and Tunde walk to the table (needs M4) |
| A03 | Ball choice | Close on the hands, shallow focus | Server bounces the ball and picks it, ritual clip |
| A04 | Hammer serve | Low side angle at table height | The stylish hammer serve in full |
| A05 | Hammer serve | From behind the server, then the ball flies away | Same serve, second angle |
| A06 | Backhand topspin serve | Front, across the net | Serve and the return |
| A07 | Side-backspin serve | Top-down overhead | The serve curving on the table |
| A08 | Forehand smash | Broadcast side view | Rally ends with a forehand smash and dust |
| A09 | Forehand smash | Slow orbit around the hitter at contact | Same smash, hero angle |
| A10 | Backhand smash | Behind the hitter, over the shoulder | Backhand put-away |
| A11 | Double flip | Close on the bat and hand | The flip move, bat face visible |
| A12 | Slide (hook) spin rally | Ball-follow camera | Ball curving across the table |
| A13 | Topspin loop exchange | Broadcast side, long rally | A long, fast rally with no cut |
| A14 | Net cord | Net-level, on the net | Ball clips the tape and dribbles over |
| A15 | Skimming the net | Net-level, low | Ball skims just above the net |
| A16 | Edge ball | Close on the table corner | Ball kisses the edge |
| A17 | Drone shot | High slow circle around the hall | A rally seen from above, the whole venue |
| A18 | Overhead | Straight down, slow rotate | Rally as a "chess board" view |
| A19 | Player's view (the real game camera) | Behind, the game's default | The way you actually see it with your phone |
| A20 | Point won | Front close-up | Celebration after a smash |
| A21 | Point lost | Front close-up | Frustration reaction |
| A22 | Match end handshake | Side, then a slow push in | Players meet at the net and shake hands (needs M5) |

### B. Kpako (local bench game): `B-kpako/`

| # | Shot | Camera | What happens |
|---|---|---|---|
| B01 | Compound establishing shot | Drone descending over the wall, golden hour | Reveal the compound and the bench |
| B02 | The bench close-up | Slow dolly along the bench at plank height | Wood grain, the plank net, dust (shows K1 and K2) |
| B03 | The plank net | Macro, rack focus | The rough-cut stick, the wedges holding it |
| B04 | The paddle | Close on the hand gripping the wooden paddle | Handle-up grip |
| B05 | Kpako serve | Low behind the server, sun behind | Straight serve down the bench |
| B06 | Kpako rally | Side view at bench height | Fast straight rally |
| B07 | Ball on the plank | Net-level | Ball clips the plank and drops over |
| B08 | Ball skimming the plank | Net-level | Close shave |
| B09 | Overhead | Straight down | Long thin bench, two players, long shadows |
| B10 | Drone orbit | High circle | The whole compound, water tank, roofs |
| B11 | Smash on the bench | Behind the hitter | Point-winner with a dust puff |
| B12 | Point won | Front, sun flare | Celebration in the compound |
| B13 | Handshake | Side | End of the game (needs M5) |
| B14 | Player's view | The game's behind camera | How it looks in play |

### C. Bounce: `C-bounce/`

| # | Shot | Camera | What happens |
|---|---|---|---|
| C01 | Bounce intro | Slow push in on the bat | Ball bouncing steadily |
| C02 | Hitting zones | The game's camera, with the score and combo shown | Orange zone hits, combo climbing to ×5 |
| C03 | Gold edge hit | Close | Risky gold rim hit, sparkle burst |
| C04 | FLIP! | Orbit around the bat | Bat turns over, the ball keeps going |
| C05 | High score | The game's view | Big score number, new personal best |

The owner's real-life clips of a hand twisting the phone pair with C02 and C04 as match cuts.

### D. Practice (ball machine): `D-practice/`

| # | Shot | Camera | What happens |
|---|---|---|---|
| D01 | The machine | Slow orbit, close | The ball machine, hopper full |
| D02 | Machine firing | From behind the machine | Balls streaming to the player |
| D03 | Training | Side | The player hits ball after ball |
| D04 | Target zones | The game's view | Hitting numbered targets |
| D05 | Overhead | Top-down | A stream of balls to the targets |

### E. Extras for editing: `E-plates/`

| # | Shot | Use |
|---|---|---|
| E01 | Empty hall, slow drift, no players | Behind the title |
| E02 | Kpako compound at golden hour, no players | Behind the title |
| E03 | Ball spinning in front of the camera, black background | Logo reveal |
| E04 | Table and bench side by side, split screen | "Two ways to play" |
| E05 | The phone bat image (the existing phone screen art) | Ties the real phone to the game |

---

## 6. Order of work

Each step ends with clips in the Desktop folder for the owner to look at.

1. **The recorder and cinematic camera.**
   - First proof: A04 (hammer serve), A17 (drone) and B05 (Kpako serve), rendered with today's graphics, so the owner sees the method early.
2. **The Kpako upgrades** K1–K5, then the Kpako batch B01–B14.
3. **The hall upgrades** H1–H6, plus moves M1–M3, then the table tennis batch A01–A21.
   - A02 and A22 come later, with the walk and handshake.
4. **Bounce B1 and Practice P1–P2,** then batches C and D.
5. **Extras:** the walk-on, the handshake (M4–M5), the E plates, and any P2 items still open.

---

## 7. Decisions for the owner

1. **Is this the right shot list?** Add, remove or change any shot.
2. **Crowd and onlookers:** keep the venues empty (the standing rule: no people until they are high quality), or try a crowd and show it only if it looks good?
3. **Handshake:** can you sign in to Mixamo once and download the handshake clip? Or should I hand-pose it in Blender?
4. **Missing serves** (pendulum, tomahawk, high toss): leave them out for now, or film a real player for them later?
5. **Slow motion:** you asked for normal speed. Should I also render slow-motion versions of the best moments (smash, net cord, hammer serve)? It costs almost nothing extra.
6. **4K:** every clip is made at 1080p, 60 fps, and you then pick hero shots from the contact sheet for a 4K render. Is that fine?
7. **Local outfits for Kpako** (K8): do them now, or keep the current kit for the first batch?
