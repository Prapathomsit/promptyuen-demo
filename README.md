# Prakan (พร้อมยื่น)

A prototype that helps car and home insurance customers report an incident. The user describes what happened, and an AI model running in the browser drafts the report, checks the required documents and suggests the nearest police station in Bangkok.

Built by team “ส่งใจในแอร์ดรอป” for CU-TU Biztania Camp 2026 (Engineering Track, finalist).

**Live demo:** https://prapathomsit.github.io/promptyuen-demo/

## Key points

- The AI (Qwen2.5-3B via WebLLM) runs in the browser, so no API key is needed and personal data stays on the device. It requires a browser with WebGPU.
- The nearest station is chosen offline from 88 Bangkok police stations (Bangkok open data).
- The user reviews and confirms every AI draft before it is used.
- This is a demo. Nothing is sent to the police or to an insurer.

## Tests

```bash
node --test tests/*.test.mjs
```

80 tests with no dependencies. Most are negative cases: invalid or made-up AI output, prompt injection, spoofed photos, duplicate submissions and invalid coordinates.

## Run locally

```bash
python3 -m http.server 4187 --bind 127.0.0.1
```

Then open http://127.0.0.1:4187. The insurance workbench runs separately with `node insurance/server.mjs` (see [insurance/README.md](insurance/README.md)).
