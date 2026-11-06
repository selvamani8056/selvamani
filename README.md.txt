# R. Kutiannan Fireworks — premium catalog website

A responsive public product catalog plus a server-backed administrator dashboard.

## Included
- Premium black / gold / red responsive storefront.
- Product catalog with search, category filters, images, descriptions, optional published prices and availability labels.
- Admin login, product CRUD, image uploads, category management and editable business information.
- SQLite persistence; session cookies are HTTP-only, SameSite=Strict, and Secure in production.
- Password hashing, login rate limiting, CSRF token checks, Helmet security headers, upload size/type limits.
- No checkout, payments, shipping or online order placement.
- Safety notice and price/availability verification disclaimer.

## Run locally
Requires Node.js 20 or newer.

1. Extract this folder.
2. In this folder run `npm install`.
3. Copy `.env.example` to `.env`.
4. Set a long random `SESSION_SECRET` (32+ characters) and a strong unique `ADMIN_PASSWORD`. Set the correct `ADMIN_USERNAME`.
5. Add the verified business phone, email, exact public address, opening hours and Google Maps URL when available.
6. Run `npm start`.
7. Open `http://localhost:3000`. Admin: `http://localhost:3000/admin.html`.

## Before public launch
- Deploy behind HTTPS. Set `NODE_ENV=production`.
- Use a strong unique admin password and secret; never commit `.env`.
- Configure regular encrypted backups of `data/catalog.sqlite` and `public/uploads/`.
- Restrict server and database file permissions. Keep Node.js and dependencies updated.
- Add verified business registration/licence and other legally required disclosures after review by the business and local counsel/authorities.
- Obtain product images and product/category/price details that the business is authorized to publish. Do not assume a product, price or availability is legal or current.
- Replace the default category names as needed in the admin dashboard.
- For production use, consider managed database/object storage, monitoring, automated backups, and a stronger admin identity provider / MFA.

## Security note
This is a functional starter implementation, not a security audit or legal certification. Admin routes are protected server-side; do not deploy without HTTPS, strong secrets, secure hosting, backups, and operational review. The initial admin credentials come from environment variables and are not stored in source code.
