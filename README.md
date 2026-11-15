# Sadhana to Seva

A mobile-first app that helps Art of Living practitioners keep a daily practice, practice together in a small Sangha circle, and grow from personal Sadhana into Seva (service).

- **Live demo:** https://sadhana-to-seva.lovable.app/
- **Standalone prototype:** [`sadhana_to_seva_prototype.html`](sadhana_to_seva_prototype.html), a single file with no sign-in and no backend. It is the reference for the full flow, including the Day 40 milestone.
- **Demo script:** [`DEMO_SCRIPT.md`](DEMO_SCRIPT.md)

## The problem

Daily practice is easy to drop when you practice alone. Volunteer coordinators, meanwhile, often match people to Seva by asking around or by phone, and many willing volunteers are never asked because nobody knows what they can do.

Sadhana to Seva connects the two. A steady personal practice with a small circle of fellow practitioners builds the habit and the relationships. The same app then shows coordinators who is ready to serve, and how.

**Intended users**
- **Practitioners** in a Sangha who want to keep a daily practice.
- **Volunteer coordinators and Volunteer Leads** who need to fill roles for Satsangs, courses and the ashram.

We have not run user research or measured outcomes, so we make no claims about results. The assumption to test is that practicing alongside a visible, supportive circle makes people more likely to keep practicing, and that a self-declared skills list makes it easier to invite them to serve.

## What it does

### Sadhana tab
- **Daily Pranayama:** play the guided practice (Short SKY Kriya, 20 minutes), or mark it complete if you practiced offline.
- **Sangha Circle:** a small circle where each person is a node that fills when they complete today's practice. It shows today's count, yesterday's count and the circles closed so far.
- **Recent Activity:** a swipeable strip showing who in your Sangha practiced and when.
- **Sangha code:** join or create a Sangha with a code (use `DEMO2026` for the demo circle), and disconnect if you want to practice on your own.
- **Blessings:** send a silent blessing to your Sangha once you have practiced.
- **40-Day SKY Lotus:** a 40-bead mala ring around a lotus that grows with your streak.
- **Phase 2 preview:** a locked line shows what comes at Day 40 (Padma Sadhana and Mantra).

### Seva & Profile tab
- **My Seva Skills:** pick how you would like to serve. Roles are grouped:
  - **Training:** VTP Graduate
  - **Satsang & Events:** Room Setup, Satsang Usher, Sound Tech, Zoom Host
  - **Music & Teaching:** Bhajan Singer, Musician, Yoga Teacher
  - **Ashram & Hospitality:** Cooking, Washroom Cleaner, Home Stay Host
  - **Transportation:** Transportation Provider, Transportation Coordinator
  - **Community:** Outreach Assistant, Book Study Organizer, Tree Planter
  - **Other:** free text
- **Seva Invites:** invites from a Volunteer Lead. If you have no skills selected, the app prompts you to add them so coordinators can find you.

### Also in the standalone prototype
The standalone prototype goes further on the first-run experience and the Day 40 milestone:
- **Join flow:** Sangha code, then name, email and optional phone, then a required Seva profile.
- **Day 40:** a one-off "ripple burst" animation turns the beads into a gold ring. A congratulations screen then links to the next course, [Sahaj Samadhi Meditation](https://www.artofliving.org/ca-en/courses/sahaj-samadhi-meditation#search-course).
- **Phase 2 unlock:** a 45-minute sequence: Padma (10 min), Kriya (20 min) and Mantra (15 min).
- **Coordinator preview and sample invites.**
- **Demo controls (footer):** "Test Day 39 → 40" and "Reset & Replay Join".

The live demo and the standalone prototype are close but not identical. Where they differ, the standalone prototype is the reference.

## Try it

**Live demo:** open https://sadhana-to-seva.lovable.app/ on a phone or in a phone-sized browser window. To join a Sangha circle, tap **Join / Create** in the Sangha Circle card and enter the code **`DEMO2026`**. This puts you in the shared demo Sangha, which has sample members.

**Standalone prototype:** download `sadhana_to_seva_prototype.html` and open it in a modern browser. It needs an internet connection, because Tailwind CSS and the Inter font load from CDNs. To host it, put it on any static host (GitHub Pages, Netlify, an internal web server). To use GitHub Pages, rename it to `index.html` and enable Pages for the repository.

See [`DEMO_SCRIPT.md`](DEMO_SCRIPT.md) for a 3 to 4 minute walkthrough.

## What is real and what is simulated

| Area | Live demo | Standalone prototype |
| --- | --- | --- |
| Screens, navigation, animations, role selection | Working | Working |
| Sign-in and accounts | Working | Not built |
| Sangha membership and daily completion shared between people | Working through the hosted backend | **Simulated.** Sample data, in memory only |
| Demo Sangha members and their completion times | **Sample data** | **Sample data** |
| Sending blessings | Works within the app | **Simulated.** The animation runs locally and nothing is sent |
| Guided pranayama audio | Opens an externally hosted audio file. If that host blocks it, log the practice with "Complete" | Streams from an external link, with the same fallback |
| Day 40 milestone, congratulations screen and Phase 2 sequence | Check the live build | Working with sample data |
| Coordinator view and Seva invites | **Simulated.** There is no coordinator-side app yet | **Simulated** |
| Notifications, real course data | **Not built** | **Not built** |

## Differences from the original brief

The original brief listed a leaderboard of Sangha streaks. We show the Sangha Circle (who has completed today, and who completed yesterday) instead of ranked streaks. This is on purpose, because ranking people by streak can discourage those who miss a day. Individual streaks appear only on your own lotus. A leaderboard could be added if Art of Living prefers it.

## Responsible use

- **No AI in the app.** The app does not use AI models, so there is no generated content to check.
- **Data in the live demo:** the live demo uses accounts and a hosted database so that people in a Sangha can see each other's practice today. Please use a display name and do not enter sensitive personal information.
- **Data in the standalone prototype:** it collects, stores and transmits nothing. Name, email and phone entered in its join flow are kept in memory only and lost on reload. All other names are sample data.
- **Privacy in a production version:** seeing who has practiced is personal information. A production version should use opt-in, show it only within a person's own Sangha, allow hiding and leaving, show email and phone only to volunteer coordinators, and never use practice data for anything outside the app's purpose.
- **Wisdom quotes:** quotes are attributed to Sri Sri Ravi Shankar. The quotes in the prototype should be reviewed and approved by Art of Living before any real use.
- **Seva invites:** invites are suggestions, never obligations. Declining is always one tap and carries no penalty. Roles are self-declared, so coordinators should confirm suitability for sensitive roles such as transportation and home stay hosting, for example by checking identity and references.
- **Errors:** if the audio stream is blocked, the app shows a message and lets the person log the practice offline. It does not block the daily flow.
- **Accessibility:** the layout is mobile-first with large tap targets. We have not yet done an accessibility audit, so screen-reader support, contrast and reduced-motion handling still need review.

## Ease of deployment

**Today:** the standalone prototype is one static HTML file with no build step, no server, no database and no secrets. The live demo is hosted on Lovable.

**Moving to production** would need:
1. **Accounts and Sangha management:** sign-in, course codes, and small Sangha groups filled in order.
2. **Backend and database:** daily completions, streaks, blessings, activity feed, and Seva roles and invites, with real-time updates.
3. **Hosted audio:** the guided practice file served from an Art of Living-controlled location.
4. **Coordinator tools:** a view for filtering volunteers by role and city, and sending invites.
5. **Privacy and consent:** consent, data retention and deletion policies, and review by Art of Living.

A sensible first step is a pilot with one Sangha.

## Hackathon scoring map

| Criterion | Where to look |
| --- | --- |
| Working product (30) | The full flow: join, practice, complete, bless, 40-day lotus, Seva skills and invites. Simulated parts are listed above |
| Problem and impact (25) | [The problem](#the-problem) |
| User experience and adoption (20) | A short daily flow, a small Sangha circle, and a milestone that celebrates progress and points to the next course |
| Responsible use (15) | [Responsible use](#responsible-use) |
| Ease of deployment (10) | [Ease of deployment](#ease-of-deployment) |
