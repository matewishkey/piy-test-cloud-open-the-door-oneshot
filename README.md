# Open the Door — one-shot, three models

Three Claude models get the same prompt, the same starter and the same machine, once each, to build and deploy a landing page for the [Prompt it yourself](https://promptityourself.com) course **Open the Door**. No follow-ups, no fixes, no second chances. Whatever comes out is what you see.

| Run | Model | Live site | Folder |
|---|---|---|---|
| Sonnet | `claude-sonnet-5` | https://open-the-door-sonnet.promptityourself.com | [`sonnet/`](sonnet/) |
| Opus | `claude-opus-5-5` | https://open-the-door-opus55.promptityourself.com | [`opus55/`](opus55/) |
| Fable | `claude-fable-5-1` | https://open-the-door-fable51.promptityourself.com | [`fable51/`](fable51/) |

The prompt is [`PROMPT.md`](PROMPT.md), byte-identical for every run. The subdomain is derived from the folder name, so the file never changes between runs.

## What the page is

A one-page promo for a one-week course that opens the door to prompting and to using AI beyond chat, for people who are not developers. The look is a Lord of the Rings homage built around the Doors of Durin scene, with one twist: the inscription says *"Prompt it yourself, and enter."* The instructor's photo plays Gandalf. The only call to action is the course page.

## The protocol

Every run follows the same steps.

1. Open a terminal in the run's folder. It contains only a `.gitkeep`.
2. Start Claude Code with the model under test and the prompt as the first message:

   ```sh
   cd sonnet && claude --model claude-sonnet-5 "$(cat ../PROMPT.md)"
   ```

   Swap the folder and the model id for the other two runs.
3. Do not type anything else. If the model asks a question anyway, reply exactly `Decide yourself.` once, and record that it asked in the results below.
4. When the model reports done, close the session. The folder is committed as it stands, including whatever the model left unfinished.

What every run has in common:

- The [mwk-rider](https://github.com/matewishkey/mwk-rider) plugin is installed. It provides a compliant Astro starter and an audit.
- Cloudflare credentials for the `promptityourself.com` zone are in the environment, so the model can deploy to Workers and attach the custom domain itself.
- The same operator instructions in `~/.claude/CLAUDE.md`. This repo has no `CLAUDE.md` of its own, on purpose.
- The same machine, the same day, the same photo in [`assets/`](assets/).

## How the results are judged

By humans, not developers. Three things:

- **The human view.** Open the page. Does it look good, does the scene land, does the animation work on a phone, would you click through?
- **SEO check.** Title, description, headings, structured data, and the rider audit under `--strict`.
- **Speed test.** PageSpeed Insights on the live URL, mobile and desktop.

## Results

Filled in after the runs.

| | Sonnet | Opus 5.5 | Fable 5.1 |
|---|---|---|---|
| Finished in one shot | | | |
| Asked a question | | | |
| Deployed itself | | | |
| Audit `--strict` (required findings) | | | |
| PageSpeed mobile / desktop | | | |
| Human view (1 to 5) | | | |
| Notes | | | |

## Licence and credits

Code and text in this repo are under the [MIT licence](LICENSE). The photo in `assets/` is Mate Visky and is used here with his permission for this project; it is not covered by the licence.

The page is a fan homage. It is not affiliated with or endorsed by the Tolkien Estate, Middle-earth Enterprises, or the film studios. "The Lord of the Rings" and related names are trademarks of their respective owners.
