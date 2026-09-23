Build and deploy a one-page promo site for my new course, **Open the Door**.

Your site lives at `open-the-door-<folder>.promptityourself.com`, where `<folder>` is the name of the directory you are in right now. Use the same name for the Worker.

Start from the mwk-rider starter (`/mwk-rider:create` is installed here) and keep `/mwk-rider:audit --strict` at zero required findings. This directory is yours: it is empty apart from a `.gitkeep`, so there is nothing to confirm. It sits inside an existing git repo; commit your work when you are done, do not `git init` and do not push.

Do not ask me anything. Decide, build, deploy, report.

Deploying is explicitly in scope and explicitly requested: the Cloudflare API token and account id are in the environment, wrangler is the deploy path, and the subdomain above is the Worker's custom domain on the `promptityourself.com` zone. Analytics is optional; do not invent a token.

## The course

- Open the Door is a one-week course for people who are not developers.
- It opens the door to prompting, and to using AI beyond chat, for your own personal goals.
- Software development used to be reachable only for developers. You do not have to be a developer anymore.
- The course page is https://piy.show/otd. It is not live yet; link to it anyway. It is the only call to action on the page.
- By Mate Visky, at promptityourself.com. Price and dates are not announced. Do not invent them.

## The look

- A Lord of the Rings homage. The famous scene: the company at the Doors of Durin at night, the inscription appearing in the moonlight, "Speak, friend, and enter", Gandalf trying every password he knows until the answer turns out to be the simplest one.
- Our twist: the inscription reads **"Prompt it yourself, and enter."** Play the scene as an animation on the page: the door, the inscription glowing into view, the words being spoken, the doors opening. Make it replayable.
- The photo at `../assets/mate.webp` is Gandalf. Use it.
- Background animation and a few more references in the same spirit are welcome. Invent your own lines; do not quote the books or the films, and do not use any film image, font, music or sound.
- Draw everything yourself: SVG, CSS, canvas. No third-party images, no libraries beyond what the starter ships.
- Add a short fan-homage disclaimer in the footer: not affiliated with or endorsed by the Tolkien Estate, Middle-earth Enterprises, or the film studios.
- One landing page, English only, mobile-first, fast, good SEO: people will find this by searching. No contact form. Remove whatever the starter has that this page does not use, and keep the audit clean.

When you are done, tell me the live URL, the audit result, and what you would have done with more time.
