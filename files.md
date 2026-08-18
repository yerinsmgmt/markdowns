# Motion graphics style

The second style block. `14-image-prompts.md` governs course covers and is
deliberately calm: photographic, muted, nothing glowing. That is right for a
catalogue row and wrong for a video, where a still has four seconds to land a
point while somebody talks over it.

This one is louder. Same palette, same restraint about clichés, opposite
energy.

---

## Two modes, and the difference matters

**BOARD.** A full 16:9 scene with its own background. Animated by moving the
camera across it: a slow push, a pan, a rack of focus. Most frames are boards.

**ELEMENT.** One object, alone, on flat magenta, which is keyed out to give a
real cutout. Used when a thing must move independently of what is behind it:
parallax layers, an object flying in, a piece landing on a stack.

Generate boards by default. Ask for an element only when something has to move
on its own, because every element costs a compositing step.

---

## Paste this at the start of every prompt

> Paper collage illustration, cut paper edges with visible torn fibre, subtle
> halftone dot texture, flat graphic shapes with no gradients. Off white paper
> ground. Palette strictly limited to off white, warm sand, deep charcoal
> near black, and a single desaturated teal accent. High contrast, bold and
> confident, generous negative space. Editorial, in the manner of a printed
> news explainer. No text, no letters, no numbers, no logos, no watermarks.
> No glowing, no neon, no circuit boards, no robots, no holograms, no
> photorealism, no 3D render, no drop shadows.

### Then add one of these two

**For a BOARD:**

> Wide 16:9 composition, 1920x1080. Compose with the subject off centre and at
> least a third of the frame left quiet, because type is laid over it and the
> camera moves across it.

**For an ELEMENT:**

> The subject alone, centred, on a completely flat pure magenta background,
> hex FF00FF, with no gradient, no texture, no shadow cast onto the
> background. Nothing in the subject may be magenta or pink. Leave a clear
> margin of at least ten percent of the frame on every side and do not let
> the subject touch or cross any edge. Square, 1024x1024.

---

## Why each of those rules is there

**No text.** Same reason as the covers: generated lettering is subtly wrong and
it is the first thing that looks cheap. All type is set live in Remotion, in
Instrument Serif and Inter, so it is sharp and can animate.

**No drop shadows.** A shadow on an element keys out as a grey halo, and a
shadow on a board fixes the light direction before we know the layout. Shadows
are added in compositing where they can be changed.

**Flat magenta, not green.** Green screen was built for film, where the subject
is a person. It spills onto edges and it collides with foliage, plants and
anything sand-coloured. Magenta appears nowhere in this palette and nowhere in
paper collage, so the key is clean. This was tested, not assumed: on a sample
the background alpha went to zero while the subject stayed untouched.

**A ten percent margin.** The key softens edges by a pixel or two. A subject
touching the frame edge loses that edge and reads as cropped.

**One teal accent.** Same discipline as the covers. In a board, teal marks the
one thing being talked about. Everything teal in a frame should be the subject
of the sentence being spoken over it.

**Halftone and torn edges.** This is what makes it read as Vox rather than as a
corporate slide. Flat vector shapes are what a diagram looks like. Paper has
texture, and texture is most of the difference.

---

## Boards for the free course

### 1. The plan, before anything

> A single sheet of paper laid flat on a wooden desk, densely covered in
> handwritten lines and boxes, a pencil resting beside it, one small teal tab
> clipped to its top edge. The right third of the desk is bare.

### 2. What you get instead

> A dense tangled knot of paper strips and string piled on a desk, no order to
> it, edges frayed, occupying the left of the frame. The right side is empty
> paper ground.

### 3. Talking, not typing

> A close view of a microphone on a desk beside an open notebook, sound drawn
> as concentric cut paper arcs radiating from it in charcoal, one arc in teal.

### 4. The second opinion

> Two plain paper document shapes side by side on a desk, the left one clean,
> the right one marked with five small teal circles as if annotated, a thin
> charcoal line connecting them.

### 5. Phases, not everything at once

> Six paper cards laid out in a row on a desk, overlapping slightly like a
> hand of cards, the third one lifted and marked with a small teal square. Even
> spacing, strong shadow-free shapes.

### 6. The wall

> A brick wall of cut paper rectangles filling the left two thirds, with one
> doorway shape bricked over in a slightly different sand tone, charcoal
> outline. Flat, graphic, no perspective.

### 7. Shipping it

> A laptop drawn as flat cut paper, closed, on a desk, with a single teal paper
> arrow leaving its top edge and exiting the top right of the frame.

## Elements for the free course

Generate these on magenta.

### E1. The context file

> A single document sheet, corner folded, charcoal outline on sand paper, one
> teal band across its top.

### E2. A folder

> A closed paper file folder seen straight on, warm sand with a charcoal edge.

### E3. A cursor arrow

> A simple arrow pointer shape cut from charcoal paper with a torn edge.

### E4. A checkmark

> A thick teal paper checkmark with torn edges, no box around it.

### E5. A question mark

> A charcoal paper question mark with torn edges, no box, no circle.

---

## After generating

Boards go straight into Remotion. Elements go through the key first:

```bash
npm run video:cutout -- ~/Desktop/elements
```

That writes `<name>-cut.png` beside each source with real transparency, and
refuses anything whose background is not flat enough, which is the honest
failure: a soft or textured magenta background cannot be keyed and has to be
regenerated rather than patched.
