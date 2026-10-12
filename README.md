# RCCG Region 64 — Open Door Website

A mobile-responsive church profile website with a Node.js + Express backend. The same Express server serves the frontend and API, so it can be deployed as one web service on Render.

## Included
- Responsive home page and mobile navigation
- About, ministries, events, sermons/media, gallery, visit and contact sections
- Search/filter for events and sermons
- Prayer request and contact forms connected to backend endpoints
- Basic content API for church settings, events, ministries and sermons
- Secure HTTP headers, basic request validation and API health check
- Render deployment blueprint

## Run locally
1. Install Node.js 20 or newer.
2. In this folder run:
   ```bash
   npm install
   cp .env.example .env
   npm run dev
   ```
3. Open `http://localhost:10000` (or the PORT shown in your terminal).

## Deploy to Render
1. Upload this project to a GitHub repository.
2. In Render, choose **New + → Blueprint** and select the repository containing `render.yaml`, or create a **Web Service**.
3. Use:
   - Build command: `npm install`
   - Start command: `npm start`
4. Deploy. Render provides the public URL.

## Before publishing
- Confirm the church's official public name and whether the site represents the parish, region, or Teens Church.
- Replace placeholder copy, service times, address, contact details, leadership and ministry details with approved information.
- Add the official logo and authorised photos in `public/images/`.
- Add official YouTube/social links in `public/js/site.js`.
- Obtain permission before publishing leader profiles, testimonies or identifiable photos, especially children's photos.

## Data persistence note
The current forms validate submissions and accept them at the API. They are **not yet connected to a persistent database or email delivery service**. Render's local filesystem is ephemeral, so do not rely on local files or server memory for permanent prayer requests. Before collecting real/sensitive submissions, connect a database such as Supabase/Postgres, restrict staff access, set retention rules, and configure an email notification provider. Prayer submissions are not displayed publicly.

## Admin note
This starter does not expose an insecure public admin panel. A production content dashboard should be added only with authenticated accounts, role-based permissions and database policies.

## API endpoints
- `GET /api/health`
- `GET /api/site`
- `GET /api/events`
- `GET /api/ministries`
- `GET /api/sermons`
- `POST /api/contact`
- `POST /api/prayer-requests`

## Structure
```text
public/
  index.html
  styles.css
  js/site.js
  images/
server.js
render.yaml
.env.example
```
