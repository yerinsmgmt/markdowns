# Cover image prompts

**Rewritten 2026-08-22.** Five images: four course covers and the front-door
lead. Everything before this was written for a direction that produced twenty
pictures of empty desks, and has been deleted rather than left to confuse the
next person.

Generate them, name the files `1` to `5` by prompt number, and drop the folder
anywhere. Any of `.png`, `.jpg` or `.webp`. The number is the only thing that
has to be right; I map them to products from it.

---

## Paste this first, every time

This block is what makes five separate generations look like one catalogue
instead of a folder of stock photos. The per-image text goes after it.

> Wide 16:9 photographic image, 1600x900. **A Black person at work, doing the
> thing the course teaches.** One or two people, never a crowd. Natural
> daylight, soft shadows, shallow depth of field. The person is absorbed in the
> work, mid task, with visible competence and calm focus: this is somebody the
> viewer would want to be. Real environments, warm neutrals and off white, with
> one restrained accent of deep blue. No text, no letters, no numbers, no
> logos, no watermarks, no readable screen content. Nothing glowing, no circuit
> boards, no robots, no blue neon, no floating holograms. Leave clear space in
> roughly a third of the frame for a title to sit over.

### Why it says that

**A person, and a Black person.** This is the rule that changed. The old block
said "no people looking at the camera" and asked for "real objects and real
workspaces", and got back twenty pictures of desks and laptops. They were not
badly made. They were unrelatable: a bare screen says a tool exists, it does
not say what somebody becomes by learning this, and nobody looks at a desk and
thinks "I want that to be me".

The academy sells a role, not software. Every course name and description
already promises what the learner can build or become; the imagery was
contradicting the copy. Black people specifically, because the audience is
African first and a catalogue of white professionals tells that audience the
product was made for somebody else.

Two things this does not license. Nobody grinning at the camera holding a
laptop, which is the stock photography failure mode and reads as an
advertisement rather than as work. And no fake diversity crowd shots: one or
two people, doing something real.

**No text.** Generated lettering is almost always subtly wrong, and it is the
first thing that makes a page look cheap. Every title on the site is real text
rendered above the image, so the image never needs to carry words.

**Clear space in a third of the frame.** These get cropped to 16:10 in the
swipe rows and to a tall panel on the front door. A subject filling the frame
loses its head or its edges.

**One accent of deep blue.** The brand colour, `--brand` `#0b4ab8`. One accent
per image is what makes a row of them look deliberate; every image being blue
makes the catalogue look like a filter was applied.

---

## The five

**1. Build and Ship Software With AI.** A Black man in his late twenties in a
quiet room at dusk, leaning back from a laptop with one hand on his chin,
thinking rather than typing. A small deployed-looking side project on a second
screen, unreadable. A notebook of handwritten flow diagrams open beside him.
The moment of working something out, not the moment of typing.

**2. AI Product Shots.** A Black woman photographing a small product on a
tabletop set she has built herself, adjusting a light with one hand. Fabric
backdrop, clamps, a bounce card. Her camera is real and in use. The finished
shot is not visible; the craft of making it is.

**3. AI Video and Motion.** A Black man at an editing desk in a dim room,
colour-grading footage, one hand on a control surface. Warm key light on his
face from the monitor side. Storyboard cards pinned above the desk. Absorbed,
mid decision.

**4. Prompt Systems for Teams.** Two Black colleagues at a whiteboard covered
in a hand-drawn process diagram, one mid sentence with a marker, the other
listening and pointing at a step. An office with daylight. This is a course
about how a team works, so the picture is two people working.

**5. Front-door lead art.** A Black woman in her early thirties standing at a
desk in a bright studio, mid conversation with someone off frame, laptop open
but not the subject. Confident, capable, unposed. Clear space on the left third
for the headline. This one carries the whole first viewport, so it has to be
the strongest image in the set.

---

## Check one before generating the rest

Generate 5 first and drop it in as the front-door lead, because it is the image
that has to work hardest. If it reads as a stock photo, the cause is almost
always the same: the person is posing rather than working. Add what their hands
are doing.

## Where they go

| Prompt | File | Used by |
| --- | --- | --- |
| 1 | `public/courses/ai-in-vs-code.jpg` | Build and Ship Software With AI |
| 2 | `public/courses/demo-product-shots.jpg` | AI Product Shots |
| 3 | `public/courses/demo-video-motion.jpg` | AI Video and Motion |
| 4 | `public/courses/demo-prompt-systems.jpg` | Prompt Systems for Teams |
| 5 | `public/courses/ai-first-steps.jpg` | Front-door lead slide |

Replacing a file in place means nothing else has to change: the covers are
referenced by path from the course records, and the front-door slide by
`imageKey`. Keep the same filenames and the same 16:9 shape.
