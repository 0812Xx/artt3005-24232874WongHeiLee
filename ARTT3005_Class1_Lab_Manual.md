# ARTT3005 · Lab Manual — Class 1
## The Digital Collection of Loss

---

## What you are making today

One card. It has a photograph on the front. You press a button, it flips over, and the back is an archival specimen label built from a file you wrote.

Then the label starts to decay. Over fifteen seconds the words blur, fade, and drift apart until they cannot be read.

The catalog number, the field labels and the border stay perfectly sharp.

**The container survives. The content does not.** That is the whole course, in one card.

By the end of today you push that card to GitHub, with your own image and your own record inside it.

---

## Contents

| | |
|---|---|
| **Part 0** | Before class — what to install |
| **Part 1** | The terminal, in four commands |
| **Part 2** | GitHub Desktop |
| **Part 3** | Your folder, and the two files you edit |
| **Part 4** | Exercise A — the chat window (prompts 1–3) |
| **Part 5** | Exercise B — the IDE agent (prompts 4–9) |
| **Part 6** | When it breaks |
| **Part 7** | What to hand in |
| **Appendix A** | The flip snippet — paste-ready |
| **Appendix B** | record.json, field by field |
| **Appendix C** | Reference build |

---

# Part 0 · Before class

Four things. Two may already be on your machine.

| | What | Where |
|---|---|---|
| 1 | **Cursor** | cursor.com |
| 2 | **GitHub account** | github.com |
| 3 | **GitHub Desktop** | desktop.github.com |
| 4 | **Python** | already on Mac · Windows must install |

Throughout: **⌘** is the Command key on Mac, **Ctrl** is Control on Windows.

## 0.1 Install Cursor

1. Go to **cursor.com**, download for your system, install, open.
2. Sign up with your **personal** email. The free plan needs no payment details.

**Mac** — if it says *"Cursor can't be opened because it is from an unidentified developer"*: open **System Settings → Privacy & Security**, scroll down, press **Open Anyway**.

**Windows** — if a blue **SmartScreen** box appears: press **More info**, then **Run anyway**.

## 0.2 Make a GitHub account

1. Go to **github.com** and sign up.
2. **Use an email address you will still have after you graduate.** Not your student address if you can avoid it.
3. Verify the email they send you.

## 0.3 Install GitHub Desktop

Go to **desktop.github.com**, download, install, open, and sign in with the account you just made.

This is the app that saves versions of your work and sends them to GitHub. You will not need to type any git commands this term.

## 0.4 Check Python

You need this to view your own page. Open Cursor, then open the terminal:

| Mac | Windows |
|---|---|
| **⌘ + J** | **Ctrl + J** |

Type this and press Enter.

**Mac**
```
python3 --version
```

**Windows**
```
python --version
```

**If you see a version number** like `Python 3.12.1` — done.

**If you see "command not found":**

**Mac** — run `xcode-select --install` and accept the prompt.

**Windows** — go to **python.org/downloads**, download Python 3, run the installer, and **tick "Add python.exe to PATH" on the first screen.** It is a small checkbox at the bottom and it is easy to miss. If you forget, uninstall and run it again — that is faster than fixing it afterwards. Then close Cursor completely and reopen it.

> **The most common error in this class.**
> On Mac you type `python3`. On Windows you type `python`.
> Type the wrong one and you get *"command not found"*, which looks like a broken machine. It is not. You typed the wrong word.

---

# Part 1 · The terminal, in four commands

The terminal looks like something for hackers in films. It is not. It is a box where you type a command and the computer does it.

Open it inside Cursor with **⌘/Ctrl + J**. Four commands, all term.

### `pwd` — where am I?

```
pwd
```

Prints the folder you are in right now. **When something does not work, run this first.** Nine times out of ten you are in the wrong folder.

### `ls` (Mac) or `dir` (Windows) — what is in here?

```
ls
```
```
dir
```

Lists the files in this folder. Use it to check your files actually arrived where you think they did.

### `cd` — move into a folder

```
cd decaying-record
```

Moves into a folder called `decaying-record`. To go back out one level:

```
cd ..
```

**Tip:** type `cd ` (with a space) then drag the folder from Finder or File Explorer into the terminal window. It fills in the path for you, with the right slashes.

### `python3 -m http.server 8000` — serve this folder

**Mac**
```
python3 -m http.server 8000
```

**Windows**
```
python -m http.server 8000
```

Then open a browser and go to:

```
http://localhost:8000
```

To stop it, click in the terminal and press **Ctrl + C** — Control, even on Mac.

---

# Part 2 · GitHub Desktop

## 2.1 Make the repository

1. On **github.com**, press **+** at the top right → **New repository**.
2. Name it exactly: `artt3005-yourname`
3. **Public** is fine.
4. Tick **Add a README file**.
5. Press **Create repository**.

## 2.2 Bring it onto your machine

1. Open **GitHub Desktop**.
2. **File → Clone repository**.
3. Choose `artt3005-yourname` from the list.
4. Choose where to put it — your Desktop or Documents is fine. **Remember where.**
5. Press **Clone**.

You now have a folder on your machine that is connected to GitHub.

## 2.3 Open it in Cursor

In GitHub Desktop, press **Repository → Open in External Editor**, or just use **File → Open Folder** in Cursor and pick the folder you cloned.

Then open the terminal with **⌘/Ctrl + J**. You are already inside the right folder — check with `pwd`.

## 2.4 Save and send — three fields, one button

Do this at the end of the session, and any time something works.

1. Go to **GitHub Desktop**. Your changed files appear on the left.
2. Bottom left, in the **Summary** box, type what you did — for example `class 1: decaying record card`.
3. Press **Commit to main**.
4. Press **Push origin** at the top.

That is it. Refresh your repository page on github.com and your files are there.

### Why bother?

You are about to let an AI rewrite your files. One day — probably around week three — it will take something that works and break it.

A commit is how you get back to the version that worked.

**It is an undo button that survives being closed.**

---

# Part 3 · Your folder, and the two files you edit

Inside your cloned repository, make a folder called `decaying-record`. Everything today lives in it.

```
artt3005-yourname/
│
├── README.md
│
└── decaying-record/
    ├── record.html          ← the AI writes this. You do not type it.
    ├── record.json         ← you edit this. It is your record.
    └── assets/
        └── record.jpg      ← your image goes here
```

Three rules about that tree.

**`record.html` is not yours to type.** You will build it by prompting, in Parts 4 and 5. If you find yourself hand-typing HTML today, stop and ask.

**`record.json` is yours entirely.** It is the actual record. Everything on the back of the card comes from it.

**`assets/` holds your image.** One image today. Name it something plain — `record.jpg`, no spaces, no capitals, no Chinese characters in the filename. Filenames with spaces break in ways that are annoying to find.

## record.json — the starting file

Create this file inside `decaying-record/` and paste this in. Then change every value to your own.

```json
{
  "catalog_id": "REC-001",
  "title": "My grandmother's soup pot",
  "date": "2026-09-03",
  "place": "her kitchen, Sham Shui Po",
  "recorder": "your name",
  "image": "assets/record.jpg",
  "not_captured": "the smell, and the sound of the lid",
  "certainty": 3
}
```

Full explanation of each field is in **Appendix B**. Two of them matter more than the rest, and they are the reason this course exists:

**`not_captured`** — what this record fails to hold. Write a specific sentence. *"The smell of the room."* *"How heavy it was."* *"What my mother said just before this."*

**The word "nothing" is not an acceptable answer.** There is always something. If you cannot find it, you have not looked hard enough.

**`certainty`** — 1 to 5. A 5 is something you can prove. A 1 is something one person said once, years later.

## A note on commas

JSON is fussy. Every line ends with a comma **except the last one**. If your card loads empty, this is the second thing to check after the server.

Cursor will underline the mistake in red. Trust it.

---

# Part 4 · Exercise A — the chat window

Three prompts, in a **chat window** — Gemini, or any chat model in a browser tab.

## Setup

1. In Cursor, open `decaying-record/` and create an empty file called `record.html`.
2. Open a browser tab with your chat model.
3. In the terminal, serve the folder — **Mac:** `python3 -m http.server 8000` · **Windows:** `python -m http.server 8000`
4. Open `http://localhost:8000/record.html` in the browser.

## The loop

For every prompt you do the same four things:

**Copy** from the chat → **Paste** into `record.html` → **Save** → **Refresh** the browser.

Count how many times you do this. That is the point of Exercise A.

## Prompt A1 — the card

```
Create a single-file record.html with a centred card, about 460 by 520
pixels, on a pale background. Inside the card put a large image
placeholder, a title underneath it, a line of smaller grey text under
that, and a button at the bottom that says "Archive this".
```

**Check:** a card in the middle of the page, with a grey block where the image will go.

## Prompt A2 — the flip

```
Give the card a front face and a back face. The front holds what is
already there. The back is blank for now. When the button is pressed,
flip the card 180 degrees to show the back.
```

**Check:** press the button and the card turns over to a blank back.

> ⚠️ **This is the step that fails.** 3D flips in CSS are fiddly and models get them wrong often. You will get a card that flips to nothing, or a back with mirrored text.
>
> **Do not spend the session debugging it.** Go to **Appendix A**, paste the snippet, carry on.

## Prompt A3 — the label

```
Style the back face as an archival specimen label: monospace type, a
thin border, a catalog number at the top, and four labelled fields —
Title, Date and place, Recorded by, and What was not captured. Use
placeholder text for now.
```

**Check:** the back now looks like something out of a museum drawer.

## Stop and count

Three prompts. Three copy-pastes. Plus saving and refreshing each time.

Now imagine doing that nine times. **You are the courier.** That is what Exercise B changes.

---

# Part 5 · Exercise B — the IDE agent

Same card. Same words. The difference is that Cursor writes the file itself.

### B4 — the decay
```
When the card flips, start a 15 second decay on the field values.
Over that time blur them, fade their opacity, and widen their
letter-spacing so the words drift apart. Use CSS transitions, not
canvas.
```

**Check:** press the button, then watch. The words should come loose and dissolve over about fifteen seconds.

### B5 — what survives
```
Keep the catalog number, the field labels and the border completely
sharp. Only the values decay.
```

**Check:** after fifteen seconds you should be looking at a perfectly crisp, perfectly empty specimen label.

### B6 — the last to go
```
Make the "What was not captured" value decay last. It should stay
readable almost the whole time and only fade right at the end.
```

**This is the one that matters.** Before you type it, decide which field should be the last to disappear, and be able to say why.

If the title goes last, what survives is a record that *something* was here, without saying what.

If "what was not captured" goes last, what survives is a catalog number, a border, and a note saying something is missing.

There is no correct answer. Whichever you choose is an argument about what an archive is for, and you are about to build it into the code.

### B7 — read the record from a file

Now the card stops being a demo and starts being yours.

```
Instead of placeholder text, load the values from a file called
record.json in the same folder, using fetch. It has these keys:
catalog_id, title, date, place, recorder, image, not_captured,
certainty. Put them into the matching fields on the back.
```

**Check:** the back of the card now shows what you wrote in `record.json`. Change a word in the file, refresh, and watch it change on the card.

> If the card goes blank here, you are almost certainly not serving the folder. See Part 1.

### B8 — your image on the front
```
On the front of the card, show the image named in record.json from
the assets folder, with the title underneath and the place below
that in smaller grey text.
```

**Check:** your own photograph, your own words, and then the whole thing dissolves.

### B9 — a message when it fails
```
If record.json fails to load, replace the page with a short monospace
message saying "record.json did not load. Are you serving the folder?
Open http://localhost:8000".
```

---

# Part 6 · When it breaks

## The habit

When something fails, **do not ask for a rewrite.** You will get a new set of problems on top of the old ones.

Paste this instead:

```
Here is what I expected: [what should have happened].
Here is what actually happened: [paste the real error, or describe
what you saw].

Help me to <fix> or <implement> or <refine> it
```

## The five things that go wrong in this room

| What you see | What it actually is | Fix |
|---|---|---|
| `command not found: python` | You are on Mac and typed `python` | Type `python3` |
| `command not found: python3` | You are on Windows and typed `python3` | Type `python`. If it still fails, reinstall and tick **Add to PATH** |
| **Card loads completely empty** | You opened the file by double-clicking, so `record.json` is blocked | Serve the folder. Open `http://localhost:8000` |
| Card empty, and you *are* serving | A comma error in `record.json` | Look for the red underline in Cursor. Last line takes no comma |
| Image is a broken icon | The filename does not match | Check `assets/` and the `record.jpg` should be the filename

## Port 8000 already in use

Somebody — probably you, in another window — is already serving. Use another number:

**Mac**
```
python3 -m http.server 8001
```

**Windows**
```
python -m http.server 8001
```

## It gave me a huge block of code and now nothing works

You asked for too much at once. In GitHub Desktop, right-click the file and choose **Discard changes** to go back to your last commit.

Then ask again in smaller steps. **One thing, then run it.**

---

# Part 7 · What to hand in

By the end of today, pushed to GitHub:

```
artt3005-yourname/
│
├── README.md
│
└── decaying-record/
    ├── record.html
    ├── record.json
    └── assets/
        └── record.jpg
```

---

# Appendix A · The flip snippet

If Prompt A2 or B2 gives you a card that flips to a blank or mirrored back, paste this and move on. **Do not debug it live.**

```css
.card  { perspective: 1200px; }

.inner { position: relative; width: 100%; height: 100%;
         transition: transform .8s;
         transform-style: preserve-3d; }

.card.flipped .inner { transform: rotateY(180deg); }

.front, .back { position: absolute; inset: 0;
                backface-visibility: hidden; }

.back  { transform: rotateY(180deg); }
```

And in JavaScript, when the button is pressed:

```js
card.classList.add('flipped');
```

## The two lines models drop

1. **`transform-style: preserve-3d`** on the *inner* element — not the outer one. Without it the browser flattens everything and the back never appears.
2. **`.back { transform: rotateY(180deg); }`** — the back has to be pre-rotated. Without it the back is drawn facing away and you see it mirrored.

Understand those two and you can fix this yourself every time.

---

# Appendix B · record.json, field by field

```json
{
  "catalog_id": "REC-001",
  "title": "My grandmother's soup pot",
  "date": "2026-09-03",
  "place": "her kitchen, Sham Shui Po",
  "recorder": "your name",
  "image": "assets/record.jpg",
  "not_captured": "the smell, and the sound of the lid",
  "certainty": 3
}
```

| Field | What goes in it |
|---|---|
| `catalog_id` | Any code you like. `REC-001` is fine. It is the thing that never decays. |
| `title` | What the thing is, in a few words. |
| `date` | When you recorded it. Year, month, day. |
| `place` | Where. Be as specific as you can bear. |
| `recorder` | You. |
| `image` | The path to your picture — `assets/` then the filename, exactly as spelled. |
| `not_captured` | **What this record fails to hold.** A specific sentence. Never "nothing". |
| `certainty` | 1 to 5. How sure are you? A 5 you can prove. A 1 is one person's memory, years later. |

Note: last two fields do not exist in almost any archive system in the world. There is nowhere to write down what you missed, or how sure you were.
