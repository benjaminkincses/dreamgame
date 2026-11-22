# DreamGame

Describe a game, get a playable game. Type an idea ("a snake game but you are a dragon eating knights"), hit generate, and a Pollinations text model writes a complete single-file HTML5 game that runs right on the page.

Live: https://benjaminkincses.github.io/dreamgame/

## How it works

- Static site, no backend. `index.html` is the whole app.
- Sign in with Pollinations via the `<polli-connect>` drop-in (Bring Your Own Pollen). Generation calls `https://gen.pollinations.ai/v1/chat/completions` with the visitor's own key and balance. No key is ever stored or proxied by this site.
- The model is prompted to return one self-contained HTML file (canvas, inline JS/CSS, no external assets). The reply is cleaned up and loaded into a sandboxed iframe (`sandbox="allow-scripts"`, no same-origin access).
- Share links carry the game itself: the HTML is gzipped, base64url-encoded and put in the URL hash, so a link plays the exact same game with no server involved.
- Demo mode: without sign-in, the built-in example game (`example-game.html`, pre-generated with `z-ai/glm-5.3-flash`) loads so the page is never empty.

## Models offered

GLM 5.3 Flash (default), DeepSeek V4.1 Flash, GPT 5.3 Codex, Kimi K2.7 Code, Qwen3 Coder Next. Any Pollinations text model id works the same way.

## Files

- `index.html` - the app
- `example-game.html` - pre-generated example game (Dragon Snake)
- `screenshot.png` - the app running the example game

Submitted to the Pollinations app catalog for quest #20021.
