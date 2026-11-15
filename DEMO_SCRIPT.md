# Demo script (about 3 to 4 minutes)

Two versions are available:
- **Live demo:** https://sadhana-to-seva.lovable.app/ (shared Sangha, code `DEMO2026`)
- **Standalone prototype:** `sadhana_to_seva_prototype.html` (adds the join flow and the Day 40 milestone)

Use the live demo for points 1 to 7 and the standalone prototype for point 6 if the live build can't show Day 40. Keep both open in separate tabs.

1. **Problem and impact (25).** "Practicing alone is hard to keep up, and volunteer coordinators often don't know who is ready to serve. Sadhana to Seva links the two: a daily practice with a small circle builds the habit, then Seva puts it into action. We haven't measured results yet. The idea to test is that practicing alongside others helps people stick with it."

2. **Easy to join (User experience, 20).** "I sign in and join my Sangha with a code." *(Live: tap Join / Create and enter the code DEMO2026 to join the Sangha circle. Standalone: type WPCI, then name and email, phone optional.)* "It takes about 30 seconds."

3. **Seva Profile.** "I choose how I'd like to serve: Satsang Usher, Home Stay Host, Transportation, Outreach and more. Coordinators can find me by these roles." *(Pick two or three roles. In the standalone prototype this step is required to finish joining.)*

4. **Daily practice with others (User experience).** "I play my guided Pranayama, or log it if I practiced offline. My circle shows who in my Sangha has practiced today. There is no ranking, so nobody feels behind."

5. **Complete a day (Working product, 30).** *(Tap Complete.)* "I log my practice and send blessings to my Sangha."

6. **40 days and the next step.** *(Standalone: tap "Test Day 39 → 40" in the footer, then Complete.)* "Every day adds a bead to the lotus. On Day 40 the beads become a full ring, Phase 2 unlocks, and the app congratulates me and links to the next course, Sahaj Samadhi Meditation. The flow is complete from first day to next course."

7. **From practice to Seva (Problem and impact).** "Coordinators see who can do what, so they don't have to ask around. Volunteers get invites for roles they chose, and can accept or decline." *(Standalone: Seva tab, "+ Test Invite", accept.)*

8. **Working product and what's simulated (Working product, 30).** "The flow works end to end. The demo Sangha members, invites and the coordinator view are sample data, and the README lists every simulated part."

9. **Responsible use (15).** "There's no AI in the app, so there's no generated content to check. Practice and contact details would be opt-in and visible only within your own Sangha, and only coordinators see email and phone. Declining an invite carries no penalty. The wisdom quotes would be approved by Art of Living, and coordinators would verify people before sensitive roles like transport or home stay. If the audio fails, the app shows a message and lets you log offline, so the day isn't blocked."

10. **Ease of deployment (10), and close.** "The standalone prototype is one HTML file with no build step, and the live demo is hosted. The README has the instructions. To go live, Art of Living would need accounts, a small backend for Sanghas and streaks, hosted audio and a coordinator view. We'd start with a pilot of one Sangha, then grow."

## Notes
- Don't claim the app is accessible. It's mobile-first with large tap targets, but no audit has been done.
- Say "the idea to test" about impact. There is no data yet.
- If the practice audio doesn't play, say "the audio streams from an external link" and tap Complete.
- Between runs of the standalone prototype, "Reset & Replay Join" in the footer returns to the first screen.
