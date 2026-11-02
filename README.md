# Bot Avatar Playground

An interactive React demo of [Libraries.dev bot avatars](https://libraries.dev/bots), using the real `bot-avatars` package.

## Features

- All 18 avatar shapes
- Idle, working, and sleeping states
- Fabric, plastic, crisp, smooth, and flat materials
- Body color, face, size, and animation speed controls
- Hats, glasses, headphones, and bow ties
- Light and dark preview surfaces
- Pause, pointer interaction, and spin ring controls
- Generated React snippet with a copy button
- Responsive layout and the avatar library's reduced-motion support

## Run locally

Install [Node.js](https://nodejs.org/) 22.12 or newer, then run:

```sh
npm ci
npm run dev
```

Open the URL printed in your terminal.

## Build for hosting

```sh
npm run build
```

Upload the generated `dist/` folder to a static hosting service. For a host with a GitHub build integration, use `npm run build` as the build command and `dist` as the output directory.

To check the production build locally:

```sh
npm run preview
```

## Publish with GitHub Pages

The included `.github/workflows/deploy.yml` builds and publishes this app on pushes to `main`. `vite.config.js` uses relative asset URLs so repository subpaths work without renaming anything.

1. Upload this folder's contents to the root of a public GitHub repository. Include the hidden `.github` folder and `vite.config.js`.
2. Open your repository's **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **GitHub Actions**.
4. Open **Actions → Deploy playground to GitHub Pages → Run workflow** and select `main`. Future pushes to `main` deploy automatically.
5. When the workflow succeeds, open the published URL shown under **Settings → Pages** or the workflow's deployment result.

For a normal project repository the URL is `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.

If the default branch is not `main`, change `branches: [main]` in the workflow to match. On GitHub Free, use a public repository for Pages. No API keys are needed; GitHub supplies the workflow's deployment token.

If the site shows a 404, check that Pages is enabled with GitHub Actions as the source and that the workflow succeeded. If the build reports a missing `package.json`, move the app files to the repository root.

References: [GitHub Pages workflows](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages), [Vite deployment](https://vite.dev/guide/static-deploy.html#github-pages).

## Upload to GitHub

1. Create an empty GitHub repository.
2. Extract the ZIP and open its `bot-avatar-playground-github` folder.
3. Upload the contents of that folder to the repository root, including `src/`, `.github/`, `vite.config.js`, `index.html`, `package.json`, `package-lock.json`, `README.md`, `LICENSE`, and `.gitignore`.
4. Commit the files. Anyone can clone or download the repository and follow the local setup above.

Do not upload `node_modules/` or `dist/`. The `.gitignore` excludes them when using Git. This source bundle contains no private hosting configuration or credentials.

## Use an avatar in another React app

```sh
npm install bot-avatars
```

```jsx
import { BotAvatar } from 'bot-avatars';

export default function MyBot() {
  return <BotAvatar type="clover" state="working" size={160} />;
}
```

Use the playground's **Copy code** button for your customized component.

## Files

```text
src/main.jsx       React application and controls
src/style.css      Layout and styling
index.html         HTML entry point
vite.config.js     Asset paths for GitHub Pages
.github/workflows/deploy.yml  Automatic GitHub Pages deployment
package.json       Dependencies and scripts
package-lock.json  Locked dependency versions
.gitignore         Files Git should exclude
LICENSE            MIT license for this demo
```

## Credits and license

Demo source is available under the [MIT License](LICENSE).

Bot avatars is by [Jakub Antalik / Libraries.dev](https://github.com/Jakubantalik/Libraries.dev), installed as a dependency under its own MIT license. React, React DOM, and Vite retain their respective licenses. Styling loads DM Sans through Google Fonts and falls back to sans-serif when unavailable.
