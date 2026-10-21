# 🕹️ Transcendence

Real-time multiplayer **Pong** web app, built as the final common-core project
of 42 Paris by a team of 3: [Eric](https://github.com/erdelp),
[Matthieu](https://github.com/matthieugalvez) and myself.

![demo](/demo/42pong.gif)

## ✨ Features

- **Online matches in real time** over WebSockets, with the game state computed on the server
- **Tournament mode** and game invitations between friends
- **Accounts and security**: email/password (bcrypt), Google sign-in (OAuth 2.0),
  two-factor authentication (TOTP + QR code), JWT access and refresh tokens in cookies
- **Social**: friends list, private chat, user profiles and avatars
- **Statistics dashboard** with interactive charts (Chart.js)
- **3 languages**: English, French, Spanish
- **Hardening**: input validation with Zod, Helmet security headers, protection
  against XSS and SQL injection, HTTPS through Nginx

## ⚙️ Tech stack

| | |
|---|---|
| **Front-end** | TypeScript single-page app (no framework, custom router), Vite, Tailwind CSS |
| **Back-end** | Node.js, Fastify, WebSockets |
| **Database** | SQLite with Prisma ORM |
| **Infrastructure** | Docker Compose, Nginx (reverse proxy, TLS) |

## 👩‍💻 My role

- **Game**: game logic, canvas rendering, real-time sync over WebSockets, tournament mode
- **Back-end**: API routes and their protection, server-side game logic, socket management
- **Front-end**: interface design and integration, UI components, single-page app navigation

## 📝 What I learned

- Designing a full stack architecture from scratch, without a front-end framework
- Keeping a real-time game in sync between players with an authoritative server
- Securing an API end to end: authentication, tokens, 2FA, input validation
- Working as a team on a long project: Git workflow, code reviews, planning

## 📸 Screenshots

![index page](/demo/indexpage.png)
![home page](/demo/homepage.png)

## 🚀 Run it locally

Requirements: Docker, and Node.js 18+ for the development mode.

```sh
cp .env.example .env     # then fill in the secrets
npm run generate:jwt     # generates AUTH_SECRET and AUTH_REFRESH_SECRET
make build-dev           # starts the app
```

Then open `http://localhost:5173` in Firefox or Chrome.
`make clean-docker` stops everything and cleans up.
