# Lab3 — Express.js Web Application

Server-side rendered Express.js application with EJS templating. Implements a basic multi-page site with authentication forms and dashboard.

## Pages

| Route | Page | Description |
|-------|------|-------------|
| `/` | Home | Landing page |
| `/login` | Login | Email/password login form |
| `/register` | Register | Registration form with validation |
| `/me` | Dashboard | User dashboard (requires login) |

## Tech Stack

- Node.js + Express.js v5
- EJS (templating engine)
- Joi (form validation)
- Bootstrap 4 (CDN)

## Setup

```bash
npm install
```

## Run

```bash
node app.js
# Open http://localhost:3000
```

## Project Structure

```
├── app.js                  # Express server + routes
├── routes/
│   ├── index.js            # Home page
│   ├── login.js            # Login form + validation
│   ├── register.js         # Registration form + validation
│   └── dashboard.js        # Dashboard + logout
├── validator/
│   ├── users.js            # Login Joi schema
│   └── register.js         # Register Joi schema
└── views/
    ├── partials/
    │   ├── head.ejs        # HTML head (Bootstrap CDN)
    │   ├── header.ejs      # Page header
    │   ├── nav.ejs         # Navigation bar
    │   └── footer.ejs      # Page footer
    └── pages/
        ├── index.ejs       # Home page
        ├── login.ejs       # Login form
        ├── register.ejs    # Register form
        ├── dashboard.ejs   # Dashboard
        └── error.ejs       # Error page
```

## Validation Rules

**Register:**
- Name: 3-30 characters
- Email: valid format
- Password: 6-15 characters
- Confirm password: must match

**Login:**
- Email + password required

## Notes

- Uses custom EJS delimiter (`?` instead of `<%`)
- No database — forms validate and redirect only
- Error handling middleware for 404/500 responses
