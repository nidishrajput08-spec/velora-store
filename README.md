# VELORA Full Store

## What is included
- Next.js dark-luxury storefront
- Empty catalog (no fake products)
- SQLite + Prisma product database
- Private admin login using an email allowlist + signed HTTP-only cookie
- Admin add/edit/delete product CRUD
- Server-side Razorpay order creation
- Server-side Razorpay signature verification endpoint
- Responsive storefront

## Local setup
Install Node.js 20+.
1. `npm install`
2. Copy `.env.example` to `.env.local`
3. Set `ADMIN_EMAIL` to your email and create a long random `ADMIN_SESSION_SECRET`.
4. Keep Razorpay secret values private. Add your Razorpay credentials to `.env.local` only.
5. `npx prisma generate`
6. `npx prisma migrate dev --name init`
7. `npm run dev`
8. Open `http://localhost:3000`
9. Open `http://localhost:3000/admin`

## Important payment note
The included Razorpay API routes are the secure server-side foundation. A production checkout should also create an Order record before payment, verify the payment, update the Order to PAID, and use webhooks for reconciliation. Do not expose `RAZORPAY_KEY_SECRET` in browser code.

## Production
SQLite is fine for local development but use a hosted PostgreSQL database for production. Deploy on a Node-compatible host. Add all environment variables in the host dashboard, run Prisma migrations during deployment, and use HTTPS.
