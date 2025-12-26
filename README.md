New
+41
-0

# ShardSmith

Procedural D&D content generator built with Next.js, Supabase, and Stripe.

## Local development

```bash
npm install
npm run dev
```

## Environment variables

```bash
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=
STRIPE_SECRET_KEY=
STRIPE_WEBHOOK_SECRET=
NEXT_PUBLIC_APP_URL=
STRIPE_PRICE_ID_MONTHLY=
UPSTASH_REDIS_REST_URL=
UPSTASH_REDIS_REST_TOKEN=
```

## Supabase setup

Run the SQL in `supabase/schema.sql` to create tables and policies.

## Stripe setup

- Create a monthly subscription price and copy its ID into `STRIPE_PRICE_ID_MONTHLY`.
- Add a webhook endpoint pointing to `/api/stripe/webhook`.
- Subscribe to `checkout.session.completed`, `customer.subscription.updated`, and `customer.subscription.deleted`.

## Vercel deployment

1. Import the repo into Vercel.
2. Add the environment variables above.
3. Set the Stripe webhook URL to `${NEXT_PUBLIC_APP_URL}/api/stripe/webhook`.
4. Deploy.