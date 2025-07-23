## Fastify's Silent Treatment

🗓️ **Date**: July 18, 2025  
🧠 **Project**: Pro Dance Suite X  
🏷️ **Tags**: fastify, backend, ts-node, hot-reload, monorepo, dev-env, tantrum

---

## The Silent Treatment

Fastify was alive... but dead inside.

You'd save `index.ts`, but Fastify just sat there.  
No reload. No response. Just... vibes.

Like a developer on Monday morning.

---

## What I Thought

"Maybe I'm doing something wrong."  
_Spoiler alert:_ I wasn’t.

Turns out `ts-node` runs your code, but doesn’t watch for changes.  
So when your TypeScript file updates, Fastify’s like:

> _"Cool story bro."_  
> And does absolutely nothing.

---

## The Fix: Get a Babysitter

Installed a new dev nanny:

```bash
npm install --save-dev ts-node-dev
"dev": "ts-node-dev --respawn --transpile-only index.ts"
```

## The Result

- Changes now taking effect. After a manual reload, at least. ✅
- Fastify now restarts like a trained dog. ✅
- Sanity restored. ✅

Still watching for betrayal. ✅

---

**End of Log.**
_(Filed under /dev-logs. Morale: shaken but standing.)_
