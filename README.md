# Real-Time Preview

Can you fix it so that you can see website changes in real time instead of having to refresh

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/d292850a-831d-4758-8fb6-49d9c74de9dd).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```


## Alpha networking note

The current Echo Chamber alpha stores users, servers, and messages in browser `localStorage`.
BroadcastChannel/storage events provide live synchronization between tabs/windows in the same
browser profile, with a lightweight periodic reconciliation fallback. They do **not** create a
shared internet-wide database. Cross-device/cross-browser public accounts, servers, presence,
and messaging require a real server/database plus authenticated API or realtime transport.

## Shared backend

The alpha now includes a `server/` Bun HTTP/WebSocket scaffold and `src/echo/lib/api.ts`.
Set `VITE_API_BASE_URL` to the deployed backend URL to begin moving public directory and
message traffic off browser-local storage. The server currently uses an in-memory repository
for development; production requires a durable database and secure session authentication.
