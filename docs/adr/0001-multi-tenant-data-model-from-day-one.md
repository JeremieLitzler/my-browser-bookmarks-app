# Multi-tenant data model from day one

Status: accepted

Bookmarks and Folders are scoped to an owning User from the first schema, even though only one User account exists at launch. We considered starting single-owner and migrating to multi-tenant later if the app ever opened up to others, but retrofitting ownership onto existing data would mean a real migration — backfilling a user id on every row, rewriting every query and row-level security policy. Scoping by owner from day one costs nothing extra now and avoids that migration entirely later. Because sign-up is also open immediately (see feature list), this decision is live in production from day one, not a deferred concern.
