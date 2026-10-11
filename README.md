# GitGarden 🌱
Your repositories, a little more alive. A small, dependency-free web app that turns public GitHub repositories into an animated garden.

## Run locally
Requires Python 3 for the server; Node.js 18+ for tests. No npm installation needed.

```sh
npm start
```
Open http://localhost:8000. Or run `python3 -m http.server 8000 --directory dist` directly.

```sh
npm test
```

## Features
- Public GitHub username lookup with pagination (up to 300 repositories)
- Instant demo garden with imaginary repositories
- SVG plants, age-based growth stages, language colours, star blossoms
- Repository details and links; forks/originals filters; sorting and rearranging
- Night mode, mobile layout, keyboard controls, reduced-motion support
- Shareable profile URLs: `?user=YOUR_USERNAME`

## Data and limitations
The browser calls GitHub's public REST API. No credentials or private repositories. GitHub applies unauthenticated rate limits. Repository age indicates growth; stars indicate blossoms. Neither measures code quality. GitHub's open_issues_count includes pull requests. Commit activity, tests and merged PRs are not integrated yet. API failures preserve the current garden and show an error. Google Fonts are optional; system font fallbacks work offline. Live GitHub lookup requires an internet connection.

## Project structure
`dist/index.html`: UI · `dist/styles.css`: styling · `dist/app.js`: interactions and API · `dist/garden.js`: plant rendering and pure helpers · `tests/`: unit tests.

## Publish on GitHub
Create an empty repository named `gitgarden`, then upload this project's files, or use git. For GitHub Pages, use a workflow that uploads `dist/` with `actions/upload-pages-artifact` and deploys with `actions/deploy-pages`, enabling Pages from Actions in repository settings. Any static host can serve `dist/` directly.

## Next contributions
- Add verified commit activity rather than using age as the growth proxy
- Add optional GitHub authentication without exposing tokens
- Add automated browser tests for API failures and mobile interactions
- Add more hand-drawn plant varieties

## License
MIT. Contributions welcome. Plant something small.
