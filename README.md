# Daily Club
A Vercel-ready Next.js app for private daily-game score sharing. Seven games, email magic-link authentication, multiple clubs with invite codes, dated score entry/editing, and tied per-game leaderboards backed by Supabase row-level security.

## Run
1. Install Node.js 20.9+ and run `npm install`.
2. Create a Supabase project. Run `supabase/schema.sql` in its SQL editor once.
3. Copy `.env.example` to `.env.local`; fill in the project URL and public anon key. Never use a service-role key in the browser.
4. In Supabase Authentication URL configuration, set Site URL and allowed redirect URLs for `http://localhost:3000` and your production domain.
5. Run `npm run dev`. Sign in by email, create a club, and share the invite code.

## Vercel and collaboration
Create a GitHub repository and push this repository. Invite your friend as a collaborator. Import it in Vercel (Next.js preset), add both environment variables, and deploy. Configure Supabase redirects for the resulting domain. No Vercel or Supabase account was provisioned by this setup.
Use feature branches and pull requests. Commit the lockfile. Run `npm test` and `npm run build` before merging.

## Scoring and limits
Manual honor-system submission, one editable result per user/game/date/club. Rankings are separate per game; equal scores share rank. Fermi multiplier is lower-is-better; Worldle and Statele use guesses (7 for a loss). Others use higher-is-better points. Confirm these conventions with your group; game sites and modes can change. No automatic scraping, score verification, or import parser. Share text is stored for future reference, not displayed or parsed yet. Date defaults to the viewer's local date; select the puzzle's date explicitly near reset times. Refresh retrieves friends' latest results; no realtime subscription. Invite codes grant membership; keep them private. Club deletion, code rotation, membership removal, aggregate rankings and rate limits are future work.

Game links are maintained in app/page.js. Krillion and Noillirk currently link to PlayDaily; confirm these are the versions your group plays. Third-party game services are independent and not affiliated.
