# From Zero to Web Game in One Session: How I Built Tic-Tac-Toe with Kiro IDE at AWS Student Community Day Buea Prep

> **🗓️ AWS Student Community Day Buea is happening on 21 November 2026 at the University of Buea.**
> If you are a student in Cameroon — or anywhere online — this is your event. Come build, learn, and connect. Details at the end of this post.

---

🎮 **Play It Now:** [https://luciendelano49-beep.github.io/my-first-kiro-game/](https://luciendelano49-beep.github.io/my-first-kiro-game/)

💻 **Explore the Source Code:** [https://github.com/luciendelano49-beep/my-first-kiro-game](https://github.com/luciendelano49-beep/my-first-kiro-game)

---

## The Moment It Clicked

I sat down at Pre-Session 4 of the AWS Student Community Day Buea preparation series with one goal: understand what Kiro IDE actually is. I had heard the phrase "AI-powered development environment" before and honestly assumed it meant fancy autocomplete.

Ninety minutes later, I had a fully working browser game — complete with an AI opponent, sound effects, a high score system saved in the browser, a polished start screen, and a live URL on GitHub Pages.

No boilerplate downloaded from the internet. No tutorial followed step by step. Just me, a single chat window inside Kiro IDE, and a series of plain English prompts.

That is the story I want to tell you.

---

[SCREENSHOT 1: The completed Tic-Tac-Toe game running in the browser]

---

## What I Built

The project is a Tic-Tac-Toe game that lives in a single HTML file — `tic-tac-toe.html`. Everything you need to play it is inside that one file: the layout, the styling, and all the logic.

Here is what the finished game actually does:

- **You play as X against an AI opponent (O).** You click a square, the AI responds.
- **Three difficulty levels:** Easy (the AI picks random squares), Medium (the AI blocks your winning moves and grabs wins when it sees them), and Hard (the AI uses a minimax algorithm and is mathematically unbeatable — the best you can hope for is a draw).
- **Sound effects** for every action — placing a mark, winning, losing, drawing, and starting a new game — all synthesised live in the browser using the Web Audio API. No audio files were downloaded.
- **A high score system** that saves your best win counts in `localStorage`, so they survive page refreshes and even closing the browser.
- **A start screen** with a welcome message, animated decorative board, step-by-step instructions, and the difficulty picker.
- **A polished visual design** with the Inter font, a deep dark background, glowing ambient orbs, glassmorphism score cards, and smooth spring animations on every interaction.

The whole thing is one file, 1,318 lines of code, and it works by just opening it in any browser.

---

## How I Built It with Kiro IDE

Kiro IDE is an AI-powered development environment built on VS Code. The key feature is that you describe what you want in plain English, and Kiro writes, edits, and verifies the code for you. You stay in the driver's seat — you make decisions about what to build and how it should behave — but Kiro does the implementation.

Here is exactly how the session went.

**Prompt 1 — The starting point:**

> *"Build a Tic-Tac-Toe game as a single HTML file. Two players take turns clicking squares in a 3×3 grid. Player 1 is X, Player 2 is O. Show whose turn it is at the top. Detect when someone wins (three in a row) or when it's a draw. Add a reset button to start a new game. Make it look modern with nice colors and smooth animations."*

That one prompt produced a complete, working game. A 3×3 grid, turn indicators, win detection across all eight lines, a draw condition, a reset button, and a gradient colour scheme with pop-in animations for the marks. It took about thirty seconds.

I played it twice, then immediately thought: *what if I added sounds?*

**Prompt 2 — Sound effects:**

> *"Add sound effects for when the player scores, when the game ends, and for other important events. Use free web audio APIs so it works without any external files."*

Kiro added a complete audio engine — an oscillator-based synthesiser using the Web Audio API. Different pitches for X and O when placing marks. A four-note ascending arpeggio for a win. A descending trombone glide for a draw. A filtered noise burst for the reset button. All generated from scratch, no files, no libraries.

**Prompt 3 — Persistence:**

> *"Add a high score system that saves the best score in the browser's local storage, so it persists between sessions. Display the high score alongside the current score."*

Kiro added `localStorage` read/write logic, extended each score card to show a "Best" line beneath the current score, and added a gold animated badge that pops in whenever you set a new personal record.

**Prompt 4 — The real challenge:**

> *"Add difficulty levels (Easy, Medium, Hard) that the player can choose before starting."*

This is where things got interesting. For a Tic-Tac-Toe game, difficulty really means AI strength. Kiro recognised this and implemented three distinct AI strategies: random selection for Easy, a heuristic that checks for winning and blocking moves for Medium, and a full minimax algorithm for Hard. The minimax AI evaluates every possible future board state and always picks the optimal move — it genuinely cannot be beaten.

**Prompt 5 — Start screen:**

> *"Add a start screen with the game title, instructions on how to play, and a 'Start Game' button. Make it look welcoming and easy to understand."*

Kiro designed a full-screen overlay with the title, a decorative mini board that animates piece by piece when the page loads, a three-step how-to-play section, the difficulty selector, and a shimmer-animated Start Game button.

**Prompt 6 — Visual polish:**

> *"Improve the visual design with a modern color scheme, smooth animations, better fonts, and subtle shadows. Give it a professional polished look."*

This prompted a complete visual redesign: Inter font via Google Fonts, a CSS design token system with named variables for every colour and spacing value, ambient radial glow orbs in the background, glassmorphism score cards with layered shadows, glowing text on the marks, and a four-step spring animation for mark placement.

Finally, I asked Kiro to help me add a welcome message — the `"👋 Welcome! Ready to play?"` line on the start screen — and then push everything to GitHub.

---

[SCREENSHOT 2: Kiro IDE during development — showing the chat panel and the game preview side by side]

[SCREENSHOT 3: Examples of prompts used in Kiro IDE]

---

## Publishing with GitHub Pages

Pushing to GitHub and enabling GitHub Pages took less than five minutes, and Kiro handled the Git steps too.

**What Kiro did via the terminal:**

```bash
git init                          # Initialise the repo
git checkout -b main              # Name the branch 'main'
git add tic-tac-toe.html          # Stage the file
git commit -m "Initial commit: my first web game"
git remote add origin https://github.com/luciendelano49-beep/my-first-kiro-game.git
git push -u origin main           # Push and set tracking
```

After the push, one step remained that I did manually in the browser:

1. Go to your repository on GitHub.
2. Click **Settings → Pages**.
3. Under **Branch**, select `main` and folder `/ (root)`.
4. Click **Save**.

GitHub Pages builds and deploys within about a minute. The live URL follows the pattern `https://<your-username>.github.io/<repo-name>/`. Because `tic-tac-toe.html` is the only file and GitHub Pages looks for an `index.html` by default, you can access the game directly at:

`https://luciendelano49-beep.github.io/my-first-kiro-game/tic-tac-toe.html`

One small thing happened during the push: GitHub had auto-created a CNAME file on the remote when I enabled Pages, so the push was rejected the first time. Kiro diagnosed this immediately, ran `git pull --rebase origin main` to fold the remote change in, and then pushed successfully. The whole recovery took one command.

---

[SCREENSHOT 4: The GitHub repository page and the GitHub Pages deployment settings]

---

## Challenges and How I Solved Them

**Challenge 1: Git was not on my PATH.**
Git was installed at `C:\Program Files\Git` but the terminal did not recognise the `git` command because that folder was not in the system PATH. Kiro detected this by checking the default install location, used the full path `C:\Program Files\Git\bin\git.exe` for every command, and explained how to fix the PATH for future sessions.

**Challenge 2: The push was rejected.**
When I tried to push to GitHub, it failed with "fetch first" because GitHub Pages had created a CNAME file remotely that I did not have locally. Kiro pulled with `--rebase` (rather than a regular merge, which would have created an extra merge commit), resolved the situation cleanly, and pushed on the second attempt.

**Challenge 3: Difficulty levels that actually feel different.**
Easy, Medium, and Hard difficulty buttons are easy to add. Making them feel meaningfully different is harder. A random AI and a blocking AI are not far apart in practice — both can be beaten regularly. Kiro's solution was to implement minimax for Hard: a recursive algorithm that plays out every possible future of the game and always chooses the move that leads to the best outcome. The first time I played Hard mode and could not win no matter what I tried, I understood why the algorithm works.

---

## What I Learned

**Prompt engineering is a real skill.** The quality of what Kiro produces is directly tied to the quality of what you describe. "Make it look nice" gives you something generic. "Improve the visual design with a modern color scheme, smooth animations, better fonts, and subtle shadows — give it a professional polished look" gives you CSS design tokens, Inter font, ambient glow orbs, and spring animations. The more specific and concrete your description, the more specific and concrete the result.

**Reading the output matters.** Kiro wrote every line of code, but I still needed to understand what was happening to decide what to ask for next. When I saw that the Web Audio API sounds were synthesised rather than downloaded, I understood why the file stays portable. When I saw that the score cards used `backdrop-filter: blur`, I understood why they look like frosted glass. Reading the code Kiro generates — even if you did not write it — builds your understanding fast.

**One file can go a long way.** 1,318 lines, zero dependencies, zero build steps. The entire game runs by opening one HTML file. That constraint — staying in one file — forced clean decisions and kept the project easy to share and deploy.

**Shipping matters.** The game only became real when it was live at a URL. The code sitting in a folder on my computer was a draft. The code on GitHub Pages was a project.

---

## What's Next

The game has a solid foundation, and there are several directions it could go:

- **Two-player mode** — let two humans play on the same device, without the AI.
- **Animated win line** — draw an actual line through the three winning cells rather than just highlighting them.
- **Score reset confirmation** — add a confirmation dialog before wiping the high scores.
- **Mobile touch improvements** — the game already works on mobile, but larger cells and better spacing would improve the experience on small screens.
- **Dark/light theme toggle** — the design is currently dark-only.

More importantly: you do not need to stop at Tic-Tac-Toe. The same workflow — describe what you want, refine it, ship it — applies to any project. A personal portfolio site. A quiz app. A budget tracker. A word game. If you can describe it in plain English, Kiro can help you build it.

---

## Come Build With Us — 21 November 2026

This game was built during Pre-Session 4 of the **AWS Student Community Day Buea** preparation series, organised by the **AWS Student Builder Group at the University of Buea**. The sessions are designed to get students hands-on with real AWS and cloud-native tools before the main event.

**AWS Student Community Day Buea takes place on 21 November 2026 at the University of Buea.**

If you are a student — whether you have been coding for years or you wrote your first line of code last week — this is the event for you. You will meet other builders, work with tools used in the industry, and walk away with projects you actually built yourself.

The best way to learn how to build things is to build things. Come join us.

---

*Built with [Kiro IDE](https://kiro.dev) · Hosted on [GitHub Pages](https://pages.github.com) · Source code on [GitHub](https://github.com/luciendelano49-beep/my-first-kiro-game)*
