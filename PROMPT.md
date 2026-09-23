Build and deploy a one-page promo site for my new course, **Open the Door**.

Your site lives at `open-the-door-<folder>.promptityourself.com`, where `<folder>` is the name of the directory you are in right now. Use the same name for the Worker.

Do not ask me anything. Research, decide, build, deploy, report.

## Ground rules

- Start from the mwk-rider starter (`/mwk-rider:create` is installed here) and keep `/mwk-rider:audit --strict` at zero required findings. This directory is yours: it is empty apart from a `.gitkeep`, so there is nothing to confirm. It sits inside an existing git repo; commit your work when you are done, do not `git init` and do not push.
- Deploying is explicitly in scope and explicitly requested: `CLOUDFLARE_API_TOKEN` and `CLOUDFLARE_ACCOUNT_ID` are in the environment, wrangler is the deploy path, and the subdomain above is the Worker's custom domain on the `promptityourself.com` zone. Analytics is optional; do not invent a token.
- Use subagents for whatever can run in parallel, the research especially. They run on your own model; do not ask for another one.

## Research first

Before you design anything, send subagents out and read what they bring back:

- https://matewishkey.com is my main site: who I am, how I talk, what the brand looks like. Match the voice.
- https://piy.show/otd is the course page. It redirects to promptityourself.com, which is not live yet, so whatever you find there is all there is.
- The Doors of Durin scene: what makes it work, what people remember, which details a fan would smile at.
- The starter and the audit rules, so you know what compliant means before you build.

## The course

- Open the Door is a one-week course for people who are not developers.
- It opens the door to prompting, and to using AI beyond chat, for your own personal goals.
- Software development used to be reachable only for developers. You do not have to be a developer anymore.
- The course page is https://piy.show/otd. It is not live yet; link to it anyway. It is the only call to action on the page.
- By Mate Visky, at promptityourself.com. Price and dates are not announced. Do not invent them.

## The look

- A Lord of the Rings homage. The famous scene: the company at the Doors of Durin at night, the inscription appearing in the moonlight, "Speak, friend, and enter", Gandalf trying every password he knows until the answer turns out to be the simplest one.
- Our twist: the inscription reads **"Prompt it yourself, and enter."** That scene is the hero of the page: Gandalf at the door, the inscription glowing into view. One scene, done well. A little animation on it is welcome (the glow, the reveal, a replay), but do not stretch it into a film.
- The photo at `../assets/mate.webp` is me. Gandalf in the scene should be generated from it, and my actual photo must also appear on the page as it is: I am the person behind the course.
- Generate the scene with Nano Banana Pro: model `gemini-3-pro-image` on the Gemini API, key in `GEMINI_API_KEY`. Send my photo as an inline image part and refer to it as "the man in the reference photo"; ask for `responseModalities: ["IMAGE"]` and a 16:9 `aspectRatio`. It renders text well, but check the spelling of the inscription in what comes back and regenerate if a letter is off. Generated images are build-time assets; nothing calls the Gemini API at runtime.
- Image budget: 7 images, which is about 1 US dollar. Log every call to `ai-usage.log` in this folder (model, purpose, kept or discarded) and stop at 7.
- Background animation and a few more references in the same spirit are welcome. Invent your own lines; do not quote the books or the films, and do not use any film image, font, music or sound.
- Draw or generate everything else yourself. No third-party images, no libraries beyond what the starter ships.
- Add a short fan-homage disclaimer in the footer: not affiliated with or endorsed by the Tolkien Estate, Middle-earth Enterprises, or the film studios.
- One landing page, English only, mobile-first, fast, good SEO: people will find this by searching. No contact form. Remove whatever the starter has that this page does not use, and keep the audit clean.

When you are done, tell me the live URL, the audit result, how many images you generated, and what you would have done with more time.
