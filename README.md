# url-shortener

A tiny URL shortener service — POST a long URL, get back a short ID, visit `/r/:id` to redirect.

## Quick Start

### Prerequisites

- Node.js >= 20
- npm

### Setup

```bash
git clone https://github.com/ShanmugaSundar27/url-shortener.git
cd url-shortener
npm install
```

### Run

```bash
npm start
```

The app will be available at http://localhost:3000

### Run tests

```bash
npm test
```

## Usage

**Shorten a URL**

```bash
curl -X POST http://localhost:3000/shorten \
  -H "Content-Type: application/json" \
  -d '{"url": "https://example.com/some/long/path"}'
```

Response:

```json
{ "id": "abc1234", "shortUrl": "http://localhost:3000/r/abc1234" }
```

**Redirect**

Visit `http://localhost:3000/r/abc1234` in your browser — it will redirect to the original URL.
