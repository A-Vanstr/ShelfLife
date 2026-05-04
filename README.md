# ShelfLife Support Site

This repository contains the small static web presence for ShelfLife: the public
landing/support page, privacy policy, terms page, favicon, app icons, and web
manifest files.

It does **not** contain the ShelfLife app source code, backend, database schema,
build pipeline, or release tooling. Treat this repo as the public website/legal
asset bundle only.

The site is plain HTML and static assets hosted via Cloudflare Workers.

## Real App Stack

The ShelfLife app itself is built with React Native.

Its backend uses Supabase for authentication, user data, and an Edge Function
that calls an OpenAI image model. That model extracts the expiry date and item
name from a single product photo. Supabase also mirrors subscription status so
only subscribed users can call the Edge Function.

Transactional account emails, such as confirmation messages, are sent through
Resend as the SMTP provider. Paywalls and subscription status are handled with
Superwall.
