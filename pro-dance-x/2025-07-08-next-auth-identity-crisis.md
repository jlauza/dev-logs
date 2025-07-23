## Next-Auth Identity Crisis

🗓️ **Date Logged**: July 8, 2025  
🧠 **Project**: Pro Dance Suite X  
🏷️ **Tags**: next-auth, monorepo, ports, identity-crisis, misfire

---

## Incident Report

Rolled out the same shiny app shell across multiple ports — looked cool, felt smart.  
NextAuth disagreed.

It mistook every port as the same clone and kept blaming `3000` for _everything_.  
First time? Just a classic `.env` misconfig. Rookie mistake.  
Second time? Looked unrelated… but MongoDB + Mongoose weren’t installed on the other ports.

Without them, fetch calls inside the app shell couldn’t read anything — and NextAuth couldn’t identify anyone.  
**Same crisis, different root cause.**

---

## Intel Analysis

- Ports were innocent. Missing adapters made them look guilty — NextAuth couldn't tell who's who.
- NextAuth: "Wait... haven't I interrogated you before?"
- No MongoDB or Mongoose meant no identity fetch — auth was flying blind.
- The clone UI (shell) demanded backend adapter support.
- Custom port lacked its own adapter, so fallback logic kicked in — straight to `3000`, where the default adapter lived.
- When NextAuth can’t resolve a custom port’s adapter, it defaults to `3000` like a confused commander returning to base.

---

## Tactical Response

- Installed MongoDB + Mongoose on all affected apps.
- Configured `NEXTAUTH_URL` to reflect each port’s true identity.
- Verified session and callback URLs were pointing to the correct instances.

---

## Outcome

- Auth works.
- Ports are no longer clones.
- I can breathe again.
- MongoDB still needy — standard protocol.

---

**End of Log.**  
_(Filed in /dev-logs. Level: Tantrum Tier 2.)_
