# Sadhana to Seva

A mobile-first prototype that helps Art of Living practitioners keep a daily practice, practice together in a small Sangha circle, and grow from personal Sadhana into Seva (service).

**Prototype file:** [`sadhana_to_seva_prototype.html`](sadhana_to_seva_prototype.html). It is a single self-contained page. All screens and behavior live in that file.

> **Status: front-end prototype.** There is no backend, no accounts and no stored data. Everything marked "simulated" below is simulated on purpose. See [What is real and what is simulated](#what-is-real-and-what-is-simulated).

## The problem

Daily practice is easy to drop when you practice alone. Volunteer coordinators, meanwhile, often match people to Seva by asking around or by phone, and many willing volunteers are never asked because nobody knows what they can do.

Sadhana to Seva connects the two. A steady personal practice with a small circle of fellow practitioners builds the habit and the relationships. The same app then shows coordinators who is ready to serve, and how.

**Intended users**
- **Practitioners** in a course Sangha who want to keep a daily practice.
- **Volunteer coordinators and Volunteer Leads** who need to fill roles for Satsangs, courses and the ashram.

We have not run user research or measured outcomes, so we make no claims about results. The assumption to test is that practicing alongside a visible, supportive circle makes people more likely to keep practicing, and that a self-declared skills list makes it easier to invite them to serve.

## What the prototype does

### Sadhana tab
- **Daily Pranayama:** play a guided practice, with a timer and a scrubber, or mark it complete if you practiced offline. After completing, you can undo.
- **40-Day SKY Lotus:** a 40-bead mala ring around a lotus that grows as your streak grows. On Day 40 the beads become a gold ring and the lotus fully opens.
- **Day 39 to 40 moment:** completing Day 40 plays a one-off "ripple burst" animation in the Wisdom popup to mark the milestone.
- **Phase 2 (Day 40):** unlocks a 45-minute Sahaj sequence: Padma (10 min), Kriya (20 min) and Mantra (15 min). Until then, a locked preview line shows what is coming.
- **Sangha Circle:** a circle of 7 people. Each person is a node that fills when they complete today's practice. The center shows today's count (for example 5/7) and a closed-circle count. A tappable "Yesterday" badge lists who completed the day before.
- **Recent Activity:** a swipeable strip showing who in your Sangha practiced most recently.
- **Send Blessings:** after you complete your practice, a short popup lets you send a silent wave of blessings to your Sangha. It closes itself after 5 seconds.
- **Daily Wisdom:** a quote popup follows the blessings step. Dismiss it with "Gurudev".

### Seva & Profile tab
- **Seva Skills:** pick the ways you would like to serve. Roles are grouped:
  - **Training:** VTP Graduate
  - **Satsang & Events:** Room Setup, Satsang Usher, Sound Tech, Zoom Host
  - **Music & Teaching:** Bhajan Singer, Musician, Yoga Teacher
  - **Ashram & Hospitality:** Cooking, Washroom Cleaner, Home Stay Host
  - **Transportation:** Transportation Provider, Transportation Coordinator
  - **Community:** Outreach Assistant, Book Study Organizer, Tree Planter
  - **Other:** free text
- **Seva Invites:** invites from a Volunteer Lead. You can accept, decline, or change your mind.
- **Coordinator preview:** shows how your selected roles appear to a coordinator.

## Try it

**Option 1: open the file.** Download `sadhana_to_seva_prototype.html` and open it in a modern browser. It works best in a phone-sized window or with browser device emulation. It needs an internet connection, because Tailwind CSS and the Inter font load from CDNs.

**Option 2: host it.** Any static host works (GitHub Pages, Netlify, an internal web server). To use GitHub Pages, rename the file to `index.html` and enable Pages for the repository.

### Demo controls (page footer)
- **Test Day 39 → 40:** jumps to Day 39. Tap Complete to see the Day 40 transition and the Phase 2 unlock.
- **Reset Demo:** restores the starting state.
- **+ Test Invite** (Seva tab): adds a sample invite.

### Suggested 3-minute walkthrough
1. On the Sadhana tab, look at the Sangha circle (5 of 7 done today) and the Recent Activity strip.
2. Tap Complete. Send blessings, then read the Wisdom quote and tap "Gurudev".
3. Tap "Test Day 39 → 40" in the footer, then Complete again, to see the Day 40 milestone and Phase 2 unlock.
4. Open the Seva & Profile tab. Select roles, tap "+ Test Invite" and accept it.

## What is real and what is simulated

| Area | Status |
| --- | --- |
| Screens, navigation, animations, timers, role selection, invite accept/decline | Working in the page |
| Sangha members, their completion times, "12 circles closed", the sample invite | **Simulated** sample data |
| Streak and Sangha state | **Simulated.** Kept in memory only, and lost on reload |
| Sending blessings | **Simulated.** The animation runs locally and nothing is sent to anyone |
| Guided pranayama audio | Streams from an external hosted link. If that host blocks the stream, use "Complete" to log an offline practice |
| "Live" activity from other people | **Simulated.** A real version needs a backend |
| Coordinator view and invites | **Simulated.** There is no coordinator-side app yet |
| Accounts, login, notifications | **Not built** |

## Differences from the original brief

The original brief listed a leaderboard of Sangha streaks. The prototype shows the Sangha Circle (who has completed today, and who completed yesterday) instead of ranked streaks. We chose this on purpose, because ranking people by streak can discourage those who miss a day. Individual streaks appear only on your own lotus. A leaderboard could be added if Art of Living prefers it.

## Responsible use

- **No AI in the app.** The prototype does not use AI models. There is no generated content to check.
- **Data:** the prototype collects, stores and transmits no personal data. All names are sample data.
- **Privacy in a real version:** seeing who has practiced is personal information. A production version should use opt-in, show it only within a person's own Sangha, allow hiding and leaving, and never use practice data for anything outside the app's purpose.
- **Wisdom quotes:** quotes are attributed to Sri Sri Ravi Shankar. The quotes in the prototype should be reviewed and approved by Art of Living before any real use.
- **Seva invites:** invites are suggestions, never obligations. Declining is always one tap and carries no penalty. Roles are self-declared, so coordinators should confirm suitability for sensitive roles such as transportation and home stay hosting, for example by checking identity and references.
- **Errors:** if the audio stream is blocked, the app shows a message and lets the person log the practice offline. It does not block the daily flow.
- **Accessibility:** the layout is mobile-first with large tap targets. We have not yet done an accessibility audit, so screen-reader support, contrast and reduced-motion handling still need review.

## Ease of deployment

**Prototype:** one static HTML file. No build step, no server, no database, no secrets. Open it or host it anywhere.

**Moving to production** would need:
1. **Accounts and Sangha management:** sign-in, course codes, and Sangha groups of 7 filled in order.
2. **Backend and database:** daily completions, streaks, blessings, activity feed and Seva roles and invites, with real-time updates.
3. **Hosted audio:** the guided practice file served from an Art of Living-controlled location.
4. **Coordinator tools:** a view for filtering volunteers by role and city, and sending invites.
5. **Privacy and consent:** consent, data retention and deletion policies, and review by Art of Living.

## Hackathon scoring map

| Criterion | Where to look |
| --- | --- |
| Working product (30) | The full flow: practice, complete, bless, wisdom, Day 40 milestone, and the Seva tab. Simulated parts are listed above |
| Problem and impact (25) | [The problem](#the-problem) |
| User experience and adoption (20) | A single-screen daily flow, a small Sangha of 7, and a milestone that celebrates progress |
| Responsible use (15) | [Responsible use](#responsible-use) |
| Ease of deployment (10) | [Ease of deployment](#ease-of-deployment) |
