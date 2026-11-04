# ConnectKit

ConnectKit is a lightweight, responsive directory of practical OAuth setup guides. It helps developers and agent builders estimate the effort behind a provider integration, understand common approval and launch requirements, and identify the steps that need a human to complete.

The project is a static web app built with HTML, CSS, and vanilla JavaScript. It has no build step, runtime dependencies, or server-side component.

## Features

- Search and filter guides for Google, Slack, Notion, GitHub, Linear, and Spotify.
- Review setup steps, effort estimates, approval caveats, and links to provider documentation.
- Copy a guide as Markdown for sharing with a teammate.
- Enter an app name or website to create an initial research checklist for an app outside the directory.
- Responsive layout, keyboard shortcut (`Ctrl/Cmd + K`) for search, and mobile navigation.

## Run locally

Open `index.html` in a browser. For a local HTTP server, use Python:

```bash
python -m http.server 8080
```

Then visit <http://localhost:8080>.

## Run with Docker

Build the image from the repository root:

```bash
docker build -t connectkit .
```

Start the container:

```bash
docker run --rm -p 8080:80 connectkit
```

Then visit <http://localhost:8080>.

## Guide quality and scope

The directory contains six representative provider guides. Effort and review timing are planning estimates, not service-level guarantees. Provider requirements can change and can depend on requested scopes, app distribution, account type, and intended use. Follow the linked provider documentation and verify requirements for the exact integration before launch.

For apps outside the directory, the current generator provides an initial research plan and a search link. It does not browse or verify provider documentation, create an OAuth app, access provider accounts, generate credentials, or submit an approval request. Its output explicitly marks provider-specific requirements and timelines as unverified. A production research agent should retrieve and cite primary provider sources, record when they were checked, and distinguish observed facts from estimates.

## Project files

```text
.
├── app.js       # Guide data, search/filter behavior, and shareable guide flow
├── index.html   # Page structure and accessible interaction entry points
├── styles.css   # Responsive visual styles
├── Dockerfile   # Nginx static-site container
└── README.md
```

## Configuration

There are no required environment variables. To add a directory guide, add its data to the `guides` array in `app.js`. Include a direct official documentation URL, setup steps, and caveats that distinguish known provider requirements from estimates. The app is static, so changes to the guide data are included in the image at build time.

## License

No license has been specified for this take-home project.
