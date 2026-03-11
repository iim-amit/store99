# 🛒 Store 99 - E-Commerce Platform

[![Next.js](https://img.shields.io/badge/Next.js-16.0.1-black)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.1.1-blue)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.7.3-blue)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.1.16-38bdf8)](https://tailwindcss.com/)

A modern, feature-rich e-commerce application built with Next.js 16, TypeScript, Sanity CMS, Clerk Authentication, Stripe payments, and Firebase. Fully created and maintained by me.

![Store 99 Preview]

## ✨ Features

- 🛍️ **Product Management** - Complete catalog with categories, brands, and search
- 🛒 **Shopping Cart** - Persistent cart with real-time updates
- 💝 **Wishlist** - Save favorite products
- 👤 **User Authentication** - Secure login via Clerk
- 📦 **Order Management** - Track orders and history
- 💳 **Multiple Payment Methods** - Stripe, Clerk Checkout & Cash on Delivery
- 📱 **Fully Responsive** - Mobile-first design
- 🎨 **Modern UI/UX** - Tailwind CSS + Framer Motion animations
- 🔍 **Advanced Search & Filters** - By category, brand, price, etc.
- ⭐ **Product Reviews** - Ratings and customer feedback
- 📧 **Email Notifications** - Order updates via Nodemailer
- 📊 **Analytics Dashboard** - Business insights and reports
- 👥 **Employee Management** - Multi-role admin/employee portal
- 📝 **Review Moderation** - Manage customer reviews
- 📬 **Newsletter & Subscriptions** - Email campaign tools
- 📈 **Customer Reports** - Detailed analytics
- 📥 **Export to Excel/CSV** - Full data export
- 🎨 **Custom Branding** - Easy customization

---

## 🚀 Quick Start Guide

### Prerequisites

- **Node.js** 18+ [](https://nodejs.org/)
- **npm**, **yarn**, or **pnpm**
- **Git**

---

## 📋 Step-by-Step Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/iim-amit/store99.git
cd store99
2️⃣ Install Dependencies
Bash# npm
npm install

# yarn
yarn install

# pnpm (recommended)
pnpm install
3️⃣ Environment Variables
Create .env in the root and add:
BashNEXT_PUBLIC_BASE_URL=http://localhost:3000

# Sanity CMS
NEXT_PUBLIC_SANITY_PROJECT_ID=your_sanity_project_id
NEXT_PUBLIC_SANITY_DATASET=production
NEXT_PUBLIC_SANITY_API_VERSION=2024-11-09
SANITY_API_TOKEN=your_sanity_api_token
SANITY_API_READ_TOKEN=your_sanity_read_token

# Clerk
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

# Stripe
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret

# Firebase
NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_firebase_auth_domain
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_firebase_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_firebase_storage_bucket
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_firebase_messaging_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_firebase_app_id
NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=your_firebase_measurement_id

# Email (Nodemailer)
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_app_password

# Admin
NEXT_PUBLIC_ADMIN_EMAIL=admin@yourdomain.com

🔑 Where to Get Credentials
Sanity CMS
→ Sanity.io → Create project → Copy Project ID & create Editor/Viewer tokens.
Clerk
→ Clerk.com → Create app → Copy keys and set redirect URLs.
Stripe
→ Stripe.com → Get API keys + create webhook for checkout.session.completed.
Firebase
→ Firebase Console → Add web app + enable Firestore.
Gmail (Nodemailer)
→ Enable 2-Step Verification → Generate 16-character App Password.

🏃‍♂️ Running the App
Bash# Development (with Turbopack)
npm run dev
# or
yarn dev
# or
pnpm dev
Open http://localhost:3000
Sanity Studio: http://localhost:3000/studio
Production:
Bashnpm run build
npm start

📁 Project Structure
## 📁 Project Structure

```
store99/
├── app/                           # Next.js 16 App Router
│   ├── (admin)/                  # Admin Panel Routes
│   │   └── admin/
│   │       ├── page.tsx          # Admin Dashboard 
│   │       ├── layout.tsx        # Admin layout with navigation
│   │       ├── analytics/        # Analytics Dashboard 
│   │       ├── reviews/          # Review Management 
│   │       ├── subscriptions/    # Subscription Management 
│   │       ├── employees/        # Employee Management
│   │       ├── products/         # Product Management
│   │       ├── orders/           # Order Management
│   │       ├── users/            # User Management
│   │       ├── account-requests/ # Account Requests
│   │       ├── notifications/    # Notification Center
│   │       └── access-denied/    # Access Denied Page
│   │
│   ├── (auth)/                   # Authentication Routes
│   │   ├── sign-in/
│   │   │   └── [[...sign-in]]/  # Clerk Sign In
│   │   └── sign-up/
│   │       └── [[...sign-up]]/  # Clerk Sign Up
│   │
│   ├── (client)/                 # Client-Facing Routes
│   │   ├── page.tsx             # Home Page
│   │   ├── layout.tsx           # Client layout with header/footer
│   │   ├── shop/                # Shop All Products
│   │   ├── category/
│   │   │   ├── page.tsx         # All Categories
│   │   │   └── [slug]/          # Category Detail Page
│   │   ├── product/
│   │   │   ├── page.tsx         # All Products
│   │   │   └── [slug]/          # Product Detail Page
│   │   ├── brands/
│   │   │   ├── page.tsx         # All Brands
│   │   │   └── [slug]/          # Brand Detail Page
│   │   ├── blog/
│   │   │   ├── page.tsx         # All Blog Posts
│   │   │   └── [slug]/          # Blog Post Detail
│   │   ├── deal/                # Special Deals
│   │   ├── orders/              # Order Tracking
│   │   ├── dashboard/           # User Dashboard
│   │   │
│   │   ├── (public)/            # Public Pages
│   │   │   ├── about/           # About Us
│   │   │   ├── contact/         # Contact Us
│   │   │   ├── privacy/         # Privacy Policy
│   │   │   ├── terms/           # Terms & Conditions
│   │   │   ├── faq/             # FAQ Page
│   │   │   ├── faqs/            # FAQs Alternative
│   │   │   └── help/            # Help Center
│   │   │
│   │   └── (user)/              # Protected User Routes
│   │       ├── cart/            # Shopping Cart
│   │       ├── checkout/        # Checkout Process
│   │       ├── wishlist/        # Wishlist
│   │       ├── success/         # Payment Success
│   │       ├── clerk-payment/   # Clerk Payment Page
│   │       └── user/
│   │           ├── page.tsx                    # User Profile
│   │           ├── dashboard/                  # User Dashboard
│   │           ├── profile/                    # Edit Profile
│   │           ├── orders/                     # Order History
│   │           │   └── [id]/                   # Order Details
│   │           ├── notifications/              # User Notifications
│   │           ├── settings/                   # Account Settings
│   │           └── admin/                      # User Admin Tools
│   │               ├── manage-users/           # Manage Users
│   │               ├── business-accounts/      # Business Accounts
│   │               └── premium-accounts/       # Premium Accounts
│   │
│   ├── (employee)/               # Employee Portal (Premium) ⭐
│   │   └── employee/
│   │       ├── page.tsx         # Shows Premium Upgrade Message
│   │       └── layout.tsx       # Employee layout (gated)
│   │
│   ├── api/                      # API Routes
│   │   ├── checkout/
│   │   │   ├── stripe/          # Stripe Checkout API
│   │   │   │   └── complete/    # Stripe Payment Completion
│   │   │   └── clerk/           # Clerk Checkout API
│   │   │       └── complete/    # Clerk Payment Completion
│   │   ├── webhooks/
│   │   │   └── stripe/          # Stripe Webhook Handler
│   │   ├── orders/              # Order Management APIs
│   │   ├── products/            # Product APIs
│   │   ├── user/                # User APIs
│   │   ├── cart/                # Cart APIs
│   │   ├── wishlist/            # Wishlist APIs
│   │   ├── reviews/             # Review APIs
│   │   ├── email/               # Email Service APIs
│   │   └── notifications/       # Notification APIs
│   │
│   ├── studio/                   # Sanity CMS Studio
│   │   └── [[...tool]]/
│   │       └── page.tsx         # Sanity Studio Editor
│   │
│   ├── layout.tsx               # Root Layout
│   ├── globals.css              # Global Styles
│   ├── not-found.tsx            # 404 Page
│   ├── robots.ts                # Robots.txt Generator
│   └── sitemap.ts               # Sitemap Generator
│
├── components/                   # React Components
│   ├── admin/                   # Admin Components
│   │   ├── AdminDashboardOverview.tsx
│   │   ├── AdminPremiumFeature.tsx    # Premium Message Component
│   │   ├── AdminTopNavigation.tsx
│   │   ├── AnalyticsDashboard.tsx
│   │   ├── AdminReviews.tsx
│   │   ├── AdminSubscriptions.tsx
│   │   ├── EmployeeManagement.tsx
│   │   ├── EmployeeOrderManagement.tsx
│   │   └── ...
│   │
│   ├── cart/                    # Cart Components
│   │   ├── CartItem.tsx
│   │   ├── CartSummary.tsx
│   │   └── ...
│   │
│   ├── checkout/                # Checkout Components
│   │   ├── CheckoutContent.tsx
│   │   ├── PaymentModal.tsx
│   │   ├── DirectPaymentModal.tsx
│   │   └── ...
│   │
│   ├── employee/                # Employee Components (Premium)
│   │   └── PaidFeatureMessage.tsx   # Premium Upgrade Message
│   │
│   ├── product/                 # Product Components
│   │   ├── ProductCard.tsx
│   │   ├── ProductGrid.tsx
│   │   ├── ProductDetails.tsx
│   │   ├── ProductReviews.tsx
│   │   └── ...
│   │
│   ├── profile/                 # User Profile Components
│   │   ├── ProfileForm.tsx
│   │   ├── OrderHistory.tsx
│   │   └── ...
│   │
│   ├── ui/                      # UI Components (shadcn/ui)
│   │   ├── button.tsx
│   │   ├── dialog.tsx
│   │   ├── input.tsx
│   │   ├── select.tsx
│   │   └── ...
│   │
│   ├── PremiumFloatingButton.tsx    # Premium Upgrade Button
│   ├── Header.tsx
│   ├── Footer.tsx
│   ├── Container.tsx
│   └── ...
│
├── actions/                     # Server Actions
│   ├── userActions.ts          # User-related actions
│   ├── orderActions.ts         # Order-related actions
│   ├── employeeActions.ts      # Employee actions (for admin)
│   ├── orderEmployeeActions.ts # Order employee actions
│   ├── reviewActions.ts        # Review actions
│   ├── wishlistActions.ts      # Wishlist actions
│   ├── walletActions.ts        # Wallet actions
│   ├── emailUserActions.ts     # Email actions
│   └── ...
│
├── lib/                         # Utility Functions
│   ├── sanityClient.ts         # Sanity client setup
│   ├── adminUtils.ts           # Admin utility functions
│   ├── orderStatus.ts          # Order status management
│   ├── emailImageUtils.ts      # Email utilities
│   ├── notificationService.ts  # Notification service
│   ├── firebase.ts             # Firebase configuration
│   └── ...
│
├── sanity/                      # Sanity CMS Configuration
│   ├── schemaTypes/            # Content schemas
│   │   ├── productType.ts
│   │   ├── categoryType.ts
│   │   ├── orderType.ts
│   │   ├── reviewType.ts
│   │   └── ...
│   ├── lib/
│   │   ├── client.ts           # Sanity client
│   │   └── image.ts            # Image utilities
│   └── env.ts                  # Sanity environment config
│
├── types/                       # TypeScript Definitions
│   ├── product.ts
│   ├── order.ts
│   ├── user.ts
│   ├── employee.ts
│   └── ...
│
├── hooks/                       # Custom React Hooks
│   ├── useCart.ts
│   ├── useWishlist.ts
│   ├── useOrderPlacement.ts
│   └── ...
│
├── config/                      # Configuration Files
│   └── contact.ts              # Contact information config
│
├── constants/                   # Constants
│   └── index.ts
│
├── public/                      # Static Assets
│   ├── preview.png             # App preview image
│   └── ...
│
├── .env                         # Environment Variables (git-ignored)
├── next.config.ts              # Next.js Configuration
├── tailwind.config.ts          # Tailwind CSS Configuration
├── tsconfig.json               # TypeScript Configuration
├── sanity.config.ts            # Sanity Studio Configuration
└── package.json                # Dependencies & Scripts

🎨 Quick Access

Frontend: http://localhost:3000
Admin Panel: http://localhost:3000/admin
Sanity Studio: http://localhost:3000/studio
Employee Portal: http://localhost:3000/employee


🛠️ Scripts
Bashnpm run dev      # Start dev server
npm run build    # Production build
npm run start    # Start production server
npm run lint     # ESLint
npm run typegen  # Generate Sanity types

🔧 Configuration
Set your admin email in .env:
BashNEXT_PUBLIC_ADMIN_EMAIL=youremail@example.com

📦 Sample Data (Optional)
Bashnpx sanity@latest dataset import seed.tar.gz


## 🎯 Key Technologies

| Technology        | Version  | Purpose          | Documentation                                |
| ----------------- | -------- | ---------------- | -------------------------------------------- |
| **Next.js**       | 16.0.1   | React framework  | [Docs](https://nextjs.org/docs)              |
| **React**         | 19.1.1   | UI library       | [Docs](https://react.dev/)                   |
| **TypeScript**    | 5.7.3    | Type safety      | [Docs](https://www.typescriptlang.org/docs/) |
| **Tailwind CSS**  | 4.1.16   | Styling          | [Docs](https://tailwindcss.com/docs)         |
| **Sanity**        | 4.12.0   | CMS              | [Docs](https://www.sanity.io/docs)           |
| **Clerk**         | 6.34.1   | Authentication   | [Docs](https://clerk.com/docs)               |
| **Stripe**        | 19.2.0   | Payments         | [Docs](https://stripe.com/docs)              |
| **Framer Motion** | 12.23.19 | Animations       | [Docs](https://www.framer.com/motion/)       |
| **Zustand**       | 5.0.8    | State management | [Docs](https://zustand-demo.pmnd.rs/)        |
| **Firebase**      | 12.5.0   | Notifications    | [Docs](https://firebase.google.com/docs)     |
| **Nodemailer**    | 7.0.10   | Email service    | [Docs](https://nodemailer.com/)              |


TechVersionPurposeNext.js16.0.1FrameworkReact19.1.1UI LibraryTypeScript5.7.3Type SafetyTailwind CSS4.1.16StylingSanity4.12.0Headless CMSClerk6.34.1AuthenticationStripe19.2.0PaymentsFramer Motion12.23.19AnimationsZustand5.0.8State ManagementFirebase12.5.0NotificationsNodemailer7.0.10Emails

🐛 Troubleshooting

Sanity Studio not loading → npm run typegen
Stripe webhooks → Run stripe listen --forward-to localhost:3000/api/webhooks/stripe
Env variables not loading → Restart server after editing .env
Build issues → rm -rf .next && npm run build


🚀 Deployment (Vercel Recommended)

Push to GitHub
Import on Vercel
Add all .env variables
Update Clerk & Stripe URLs for production


📄 License
MIT License
Created and maintained by Amit
GitHub: https://github.com/iim-amit/store99