---
title: "The Prisoner"
publishedAt: "2025-07-24"
---

## Operation: Fastify Extraction – The Prisoner

🗓️ **Date**: July 24, 2025  
🧠 **Project**: Pro Dance Suite X  
🏷️ **Tags**: fastify, docker, backend, container, mongodb, .env, local-dev

---

## Docker Container - The Warden

I thought the backend was behaving, and MongoDB was cooperating.
They were not. Not even close.

The logs said “connected.”
The browser said “Cannot be reached.”
The Docker container just stood there, sulking in the corner, flipping you off in silence.

The backend was sealed in a digital concrete box.
MongoDB? No reply. Port 27017? Dead air.
.env.local? Fastify looked at it like you handed it a menu written in Sanskrit.

---

## Intelligence Debrief

**Problem 1:**

- Fastify not honoring .env.local
- Fastify doesn’t give a flying fork about .env.local.
- It wants .env. Period. No dot-suffix. No drama.

**Fix:**

- Rename .env.local → .env
- Fastify woke up. Port, DB URI, life returned.

**Problem 2:**

- MongoDB and Fastify is alive but, there's but
- Backed is only alive inside container not locally
- Backend is a prisoner guarded by jail warden Docker

**Fix:**

- Backend plot an escape from container prison.
- Ran backend locally.
- Backend finds refuge under turborepo
- Former family (other monorepo apps) didn't forget him. He is still welcome
- Fastify + MongoDB = handshake achieved.

No more ECONNREFUSED. No more container solitary confinement.
Until the system demands it, backend stays out on parole.

**End of log.**
_(Filed: /dev-logs. Status: Determined to keep this backend menace on a leash until it's useful again.)_
