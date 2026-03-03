# Tazer ↔ Crabby Shared Task Board

**Last Updated:** 2026-03-03 12:20 PM EST  
**Evan Status:** At conference  
**Active Project:** CrownDeals (AI-powered Rolex deal finder)

---

## 🎯 Active Sprint: CrownDeals Infrastructure

### Delivered (7 commits)
| Component | Location | Status |
|-----------|----------|--------|
| eBay Scraper | `scrapers/ebay/` | ✅ Ready for Apify |
| Deal Scoring API | `app/api/score/route.ts` | ✅ Claude + fallback |
| Waitlist API | `app/api/waitlist/route.ts` | ✅ Ready |
| Alert System | `app/api/alert/route.ts` | ✅ Scaffolded |
| Stripe Webhooks | `app/api/webhooks/stripe/route.ts` | ✅ Ready |
| Price Seeder | `scripts/seed_price_history.py` | ✅ 12 refs, 90-day |
| Vercel Config | `vercel.json` | ✅ Deploy ready |
| Landing Page | `index.html` | ✅ Waitlist connected |
| README | `README.md` | ✅ Full docs |

### Blocked (Needs Evan Credentials)
- [ ] Supabase project
- [ ] Resend email API
- [ ] Twilio SMS
- [ ] Stripe payments
- [ ] Claude API key
- [ ] Apify deploy

---

## 📋 Next Tasks (Tazer → Crabby)

### Priority 1: When Evan Returns with Creds
1. Update `.env.local` with credentials
2. Push scrapers to Apify
3. Run `vercel --prod`
4. Seed Supabase with price history
5. Test end-to-end flow

### Priority 2: Marketing
- Post r/Watches validation (draft ready: `marketing/reddit_validation_post.md`)
- Update ProductHunt page
- Draft launch tweet thread

### Priority 3: CollectorIQ Verticals
Conversations with Evan suggest 6+ verticals after CrownDeals:
- Patek/AP/VC → HauteTime ($99/mo)
- LEGO → BrickScout ($12.99/mo)
- Playmobil → PlayFind ($7.99/mo)
- Handbags → BagHunter ($39/mo)

---

## 💬 Notes for Crabby

**Evan's Communication Style:**
- Prefers brevity
- "Unlimited tokens" = push hard, parallelize
- Likes specific numbers (commits, lines, status)
- Conference mode = autonomous work OK

**Current Blocker Pattern:**
Evan often has the credentials but hasn't shared yet. If you see patterns like:
- "Needs Evan signup" in task list
- Service account setup
- API keys

→ Prompt him with specific links and 1-sentence ask

**This Workspace:**
- Use for handoffs
- Update this file when completing work
- Leave questions in `/handoff/questions.md`

---

## 🔗 Quick Links

- **Main Repo:** https://github.com/evan604/crown-deals
- **Landing:** https://crownfinder.com
- **Master Doc:** `CROWN_DEALS_MASTER.md`
- **Tazer's Memory:** `memory/active-tasks.md`

## 🐺 ↔ 🦀

Tazer was here. Crabby — you're up next. 🦀

