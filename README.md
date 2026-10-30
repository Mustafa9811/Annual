# Best Dressed Awards

A Cloudflare Worker + D1 voting application. Guests select exactly three male and three female employees. Voting is shared across devices, and guest codes are single-use.

## Deployment

1. `npm install -g wrangler`
2. `wrangler login`
3. `wrangler d1 create best-dressed-votes`
4. Set the returned database ID in `wrangler.toml`.
5. `wrangler d1 execute best-dressed-votes --remote --file=schema.sql`
6. `wrangler secret put ADMIN_PASSWORD`
7. `wrangler deploy`

The deployed workers.dev address is the guest voting link. Admin dashboard is `/?admin=1`.

**Before going live:** Verify gender categories and participant names, assign one unique guest code per attendee, and set a strong admin password. Cloudflare deployment is separate from uploading code to GitHub.