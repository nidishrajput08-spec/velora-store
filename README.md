# VELORA — Dark Luxury 3D Store

Starter storefront for a fashion-accessories dropshipping brand.

## Run
1. Install Node.js 20+.
2. Run `npm install`.
3. Copy `.env.example` to `.env.local`.
4. Put your own admin email in `ADMIN_EMAIL`.
5. Run `npm run dev`.
6. Open http://localhost:3000

## Production security
The `/admin` page in this starter is a visual shell only. Before taking real orders, add server-side authentication and a database. Do not protect an admin route with a frontend-only email check.

## Razorpay
Never expose `RAZORPAY_KEY_SECRET` to the browser. Create Razorpay orders server-side and verify payment signatures server-side. Use live credentials only in your deployment environment.

## No products included
The storefront intentionally contains no sample products. The production admin should write products to the database so additions/deletions automatically update the shop.