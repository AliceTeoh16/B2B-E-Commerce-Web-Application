# Organic Seeds - E-commerce Grocery Platform

## Live Website

**Live URL:** [https://organicseeds.com.my/](https://organicseeds.com.my/)

## Project Background

Organic Seeds is a full-stack grocery e-commerce platform for a community-focused organic grocery store in SS2, Petaling Jaya. The platform enables customers to browse organic products, place and track orders, manage delivery details, make payments, request refunds and cancellations, and communicate with store staff.

The system also provides administrators with tools to manage the product catalogue, categories, customer accounts, orders, payments, vouchers, home-page content, blogs, refunds and reviews.

## Business Pain Points Addressed

- Customers previously needed to visit the store or use separate messaging channels to find products and place orders.
- Manual shopping made it difficult to search, compare, filter and sort grocery items.
- Delivery distance and shipping fees were unclear during the ordering process.
- Customers lacked a central place to track orders, payments, refunds and cancellations.
- Store administrators needed a structured way to maintain products, stock, vouchers and customer orders.
- The business needed consistent product, promotion and service information across a responsive online experience.
- Repeated customer questions required a better self-service experience for order tracking and account management.

## Modules Responsible

The main modules developed for this project include:

### Customer-Facing Modules

- Responsive home page with promotional banners, featured products and product collections
- Product catalogue with search, category filtering, sorting, product details and special deals
- Shopping cart and wish-list functionality
- Checkout flow with address selection and payment processing
- User registration, email verification, login and password recovery
- Customer account dashboard for profile, password, addresses and saved payment cards
- Order history, order details, cancellations and payment records
- Voucher and promotion management
- Refund requests and refund status tracking
- Product reviews and customer notifications
- About, blog, contact, terms and privacy pages

### Administration Modules

- Admin authentication and protected dashboard routes
- Product and category management
- Order, payment, user and refund administration
- Voucher and promotion management
- Homepage hero and banner configuration
- Customer notification management
- Blog, review and store profile management

### API and Integration Modules

- Laravel REST APIs for products, categories, users, orders and administration
- Stripe payment integration
- Cloudinary image handling
- EasyParcel shipping, tracking and OAuth integration
- Google reCAPTCHA verification
- MySQL/SQLite database access and Laravel migrations
- Customer and administrative authentication

## Tech Stack

| Area | Technology |
|---|---|
| Frontend structure | HTML |
| Styling | CSS, Tailwind CSS |
| Client-side logic | JavaScript |
| Frontend framework | React |
| Frontend build tool | Vite |
| Routing | React Router |
| Backend framework | Laravel (PHP) |
| API style | REST API |
| Database | MySQL for deployed environments; SQLite for local development |
| Authentication | Laravel authentication and protected React routes |
| Payment | Stripe |
| Shipping | EasyParcel |
| Media storage | Cloudinary |
| Security | Google reCAPTCHA |

## Project Structure

```text
src/             React pages, components and frontend state
server/          Frontend/server integration code
ekomart-api/     Laravel API, routes, controllers and database migrations
public/          Static frontend assets
screenshots/     Interface screenshots for documentation
```

## Local Setup

### Frontend

Requirements:

- Node.js 20 or newer
- npm

```powershell
npm install
npm run dev
```

The frontend runs at `http://localhost:3000`.

### Laravel API

Requirements:

- PHP 8.2 or newer
- Composer
- SQLite for local development

```powershell
cd ekomart-api
composer install
Copy-Item .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

The API runs at `http://127.0.0.1:8000`.

## Environment Configuration

Keep secrets in ignored `.env` files. Use local values for development:

```text
APP_ENV=local
APP_URL=http://localhost:8000
FRONTEND_URL=http://localhost:3000
EASYPARCEL_ENVIRONMENT=sandbox
```

Required provider credentials should be supplied only through local environment variables:

- Stripe test publishable and secret keys
- Cloudinary cloud name, API key and API secret
- EasyParcel API or OAuth credentials
- Google reCAPTCHA site and secret keys
- AWS credentials only if S3 storage is enabled

Do not commit real secrets, personal customer data, exported databases or `.env` files.

## Available Commands

### Frontend

```text
npm run dev       Start the Vite development server
npm run server    Start the Node integration server
npm run dev:all   Import data and start development services
npm run build     Create a production build
npm run lint      Run TypeScript checks
npm run preview   Preview the production build
```

### Laravel API

```text
php artisan serve       Start the API server
php artisan migrate     Run database migrations
php artisan test        Run tests
php artisan config:clear Clear cached Laravel configuration
```

## Security and GitHub Checklist

- `.env`, `.env.local`, `.env.production` and database backups must remain ignored.
- Use test/sandbox provider credentials locally.
- Never put private API secrets in React or Vite variables.
- Revoke credentials that may already have been exposed.
- Redact customer names, addresses, phone numbers, emails and order/payment identifiers from screenshots.
- Review `git status --ignored` and staged files before pushing.
