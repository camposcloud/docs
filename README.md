# CamposCloud docs

Source of [docs.camposcloud.com](https://docs.camposcloud.com), built with [Mintlify](https://mintlify.com/docs).

## Structure

| Path | What it holds |
| --- | --- |
| `index.mdx`, `quickstart.mdx` | Welcome page and the first-request guide |
| `guides/` | Guides about how the platform behaves (for example, why an application stopped) |
| `api-reference/` | Introduction, authentication, limits and one page per endpoint |
| `api-reference/openapi.json` | The API schema. Endpoint pages point to it with `openapi: 'METHOD /path'` |
| `sdk/` | JavaScript SDK and Python usage |
| `docs.json` | Navigation, colors, logo and links |

## Preview locally

```bash
npm i -g mint
mint dev
```

Run it in the folder with `docs.json`. The preview opens at `http://localhost:3000`. If a page is a 404, check that you are in that folder; if it will not start, run `mint update`.

To find broken links before publishing:

```bash
mint broken-links
```

## Writing

- Pages are in English. Keep them short and use the HTTP status, not the error message, when describing errors.
- A new page must be added to `navigation` in `docs.json`, or it will not show in the menu.
- When an endpoint changes, update `openapi.json` and its page in `api-reference/endpoint/`, and the limits in `api-reference/api-limits.mdx` if they changed.
- Never put a real API Key in an example. Use `YOUR_API_KEY_HERE`.

## Publishing

Changes pushed to `main` are deployed automatically by the Mintlify GitHub app.
