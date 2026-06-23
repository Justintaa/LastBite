# LastBite - Food Marketplace Web Application

LastBite is a full-stack Django web application designed to help reduce food waste by allowing businesses to list discounted food items and customers to browse, bid on, add to cart, and purchase available listings.

This project was built as a team academic project and demonstrates full-stack web development using Django, PostgreSQL, Docker, user authentication, dynamic pricing, and payment checkout integration.

## Features

* Customer and business account registration/login
* Role-based user flows for customers and businesses
* Business dashboard for managing listings and products
* Product creation, editing, deletion, and public product pages
* Dynamic pricing based on listing/product timing
* Bidding system for eligible products
* Shopping cart functionality
* Stripe checkout integration
* Customer dashboard with nearby listings and businesses
* Order history and checkout success/cancel pages
* PostgreSQL database support through Docker Compose

## Tech Stack

**Backend:** Python, Django
**Database:** PostgreSQL
**Frontend:** HTML, CSS, JavaScript, Django Templates
**Payments:** Stripe API
**DevOps/Tools:** Docker, Docker Compose, Git
**Other:** Django authentication, Django ORM, environment variables

## Project Structure

```text
.
├── business/              # Business listings, products, bidding, vendor pages
├── dashboard/             # Customer dashboard, nearby listings, dashboard stats
├── landing/               # Landing page
├── market/                # Cart, checkout, orders, Stripe checkout flow
├── users/                 # Authentication, customer/business registration
├── config/                # Django project settings and URL routing
├── templates/             # Shared and app-level HTML templates
├── static/                # Static CSS/JavaScript files
├── compose.yaml           # Docker Compose configuration
├── Dockerfile             # Docker image setup
├── entrypoint.sh          # Database wait, migrations, static collection, server start
├── requirements.txt       # Python dependencies
└── .env.example           # Example environment variables
```

## Getting Started

### Prerequisites

Make sure you have the following installed:

* Docker
* Docker Compose
* Git

### Installation

1. Clone the repository:

```bash
git clone https://github.com/Justintaa/lastbite-django-marketplace.git
cd lastbite-django-marketplace
```

2. Create your environment file:

```bash
cp .env.example .env
```

3. Open `.env` and update the values if needed:

```env
POSTGRES_DB=lastbite
POSTGRES_USER=lastbite
POSTGRES_PASSWORD=change-me

DJANGO_DEBUG=1
DJANGO_SECRET_KEY=change-me
DJANGO_ALLOWED_HOSTS=localhost,127.0.0.1

STRIPE_PUBLISHABLE_KEY=your-stripe-publishable-key
STRIPE_SECRET_KEY=your-stripe-secret-key
```

4. Build and start the application:

```bash
docker compose up --build
```

5. Open the app in your browser:

```text
http://localhost:8000
```

The app automatically waits for PostgreSQL, runs migrations, collects static files, and starts the Django development server through `entrypoint.sh`.

## Main App Routes

```text
/                     Landing page
/users/               User login and registration
/dashboard/           Role-based dashboard router
/user-dashboard/      Customer dashboard
/biz/                 Business/vendor listing and product pages
/market/              Cart, checkout, and order flow
/admin/               Django admin
```

## Environment Variables

This project uses environment variables for configuration. Do not commit a real `.env` file.

| Variable                 | Description                                |
| ------------------------ | ------------------------------------------ |
| `POSTGRES_DB`            | PostgreSQL database name                   |
| `POSTGRES_USER`          | PostgreSQL database user                   |
| `POSTGRES_PASSWORD`      | PostgreSQL database password               |
| `DJANGO_DEBUG`           | Django debug setting for local development |
| `DJANGO_SECRET_KEY`      | Django secret key                          |
| `DJANGO_ALLOWED_HOSTS`   | Comma-separated list of allowed hosts      |
| `STRIPE_PUBLISHABLE_KEY` | Stripe publishable key                     |
| `STRIPE_SECRET_KEY`      | Stripe secret key                          |

## Screenshots

Add screenshots here after running the project locally.

```md
![Landing Page](screenshots/landing-page.png)
![Customer Dashboard](screenshots/customer-dashboard.png)
![Business Dashboard](screenshots/business-dashboard.png)
![Product Page](screenshots/product-page.png)
![Cart Page](screenshots/cart-page.png)
```

## What I Worked On

As part of the team, I contributed to the design and development of the application’s full-stack functionality, including Django views, templates, database-backed features, user-facing pages, and workflow improvements across the marketplace experience.

## Future Improvements

* Add automated tests for key workflows
* Improve production deployment configuration
* Add stronger form validation and error handling
* Improve mobile responsiveness
* Add search/filter functionality for listings
* Add clearer user notifications for checkout and bidding status

## Notes

This project was created for academic purposes and is intended as a portfolio demonstration of full-stack Django development. API keys, database passwords, and secret keys should be stored locally in `.env` and should not be committed to GitHub.
