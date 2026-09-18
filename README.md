# My3DWorld — complete development build

## Included
- Playable 3D browser room
- Female avatar with outfit/hair wardrobe
- Shop with coins/gems
- Furniture drag-and-drop
- Profile + bio
- Friends and invite UI
- Room chat
- Real-time Socket.IO multiplayer backend
- PostgreSQL/Prisma persistence
- JWT authentication
- Friend requests/acceptance
- Room invitations

## Quick visual demo
Open `client/index.html` in a modern browser. The client has a local demo mode.

## Real multiplayer
Install Node.js 20+ and PostgreSQL.

```bash
cd server
cp .env.example .env
# edit DATABASE_URL, JWT_SECRET and CLIENT_ORIGIN
npm install
npx prisma generate
npx prisma migrate dev --name init
npm run dev
```

Serve `client/` over HTTP (for example with a static server/Vite) and use the same origin in `CLIENT_ORIGIN`.

## Public website
This package is deployment-ready source, but a public URL still requires a hosting account/domain. The chat environment cannot create or control an external hosting account on your behalf.

For production add HTTPS/WSS, refresh-token rotation, rate limits, moderation/reporting, secure headers, Redis for multiple Socket.IO instances, CDN/object storage for real GLB assets, server-authoritative gameplay, backups and monitoring.
