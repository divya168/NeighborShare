# 🏘️ NeighborShare

> **Hyper-local sharing economy platform for Indian neighborhoods**
> Borrow tools, lend appliances, offer skills — all within your colony, apartment, or campus.

![NeighborShare Banner](https://img.shields.io/badge/NeighborShare-Circular%20Economy-00FF88?style=for-the-badge&logo=leaflet&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-16.1.6-black?style=for-the-badge&logo=next.js)
![Firebase](https://img.shields.io/badge/Firebase-Firestore%20%2B%20Auth-orange?style=for-the-badge&logo=firebase)
![Razorpay](https://img.shields.io/badge/Razorpay-Payments-blue?style=for-the-badge&logo=razorpay)
![Gemini](https://img.shields.io/badge/Gemini-AI%20Powered-purple?style=for-the-badge&logo=google)

---

## 📖 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Project Structure](#-project-structure)
- [API Routes](#-api-routes)
- [Database Schema](#-database-schema)
- [Screenshots](#-screenshots)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌱 About

NeighborShare is a **Micro-SaaS platform** built for local circular economies in India. Instead of every household buying items they'll use only a few times, neighbors can borrow, lend, and trade within a verified 2km radius.

**The Problem:** The average Indian urban household spends ₹18,000/year on items used less than 5 times. Meanwhile, the same items sit idle in nearby homes.

**The Solution:** A trust-based, AI-powered, hyper-local sharing platform where your colony becomes a self-sustaining resource network.

### Real-world example:
| Item | Owner | Borrow Price |
|------|-------|-------------|
| Drill machine | Raj | ₹20/hour |
| Ladder | Neha | ₹30/day |
| Pressure washer | Amit | ₹50/day |
| Cake baking tools | Riya | Free |

---

## ✨ Features

### Core Features
- 🔐 **Authentication** — Google Sign-In + Phone OTP via Firebase Auth
- 📍 **Neighborhood Verification** — GPS-locked, 2km radius scoping
- 📦 **Item Marketplace** — List, browse, and borrow items with photos
- 🎓 **Skill Exchange** — Offer and book services like tutoring, plumbing, music lessons
- 💬 **Real-time Chat** — In-app messaging with Google Maps location sharing
- 💳 **Secure Payments** — Razorpay with deposit escrow system
- ⭐ **Trust Score** — Bronze → Silver → Gold → Platinum badges
- 🔔 **Push Notifications** — Firebase Cloud Messaging

### AI-Powered Features (Gemini API)
- 🤖 **Smart Search** — Natural language search ("something to hang a picture")
- ✍️ **Description Generator** — AI writes compelling listing descriptions
- 💰 **Price Suggester** — AI recommends fair prices based on category & condition
- 🛡️ **Safety Checker** — Flags potential safety concerns for borrowed items
- 📰 **Community Digest** — Weekly AI-generated neighborhood summary

### Maps Features (Google Maps API)
- 🗺️ **Live Item Map** — Interactive map showing nearby items with distance badges
- 📏 **Distance Calculation** — "200m away" shown on every item card
- 🧭 **Directions** — One-tap Google Maps navigation to pickup location
- 🌐 **Geofencing** — Auto-restrict listings to verified neighborhood radius

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | Next.js 14 (App Router), React.js, Tailwind CSS |
| **Backend** | Node.js, Next.js API Routes |
| **Database** | Firebase Firestore |
| **Auth** | Firebase Authentication |
| **Storage** | Firebase Storage |
| **Notifications** | Firebase Cloud Messaging (FCM) |
| **Maps** | Google Maps JavaScript API, Geocoding API, Places API |
| **AI** | Google Gemini API |
| **Payments** | Razorpay (Payments + Payouts + Webhooks) |
| **Deployment** | Vercel |

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn
- Firebase project
- Google Cloud project (Maps API)
- Razorpay account
- Google AI Studio account (Gemini API)

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/neighborshare.git

# Navigate into the project
cd neighborshare

# Install dependencies
npm install

# Copy environment variables template
cp .env.example .env.local

# Fill in your API keys (see Environment Variables section)
# Then start the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🔑 Environment Variables

Create a `.env.local` file in the root directory with the following variables:

```env
# ─── Firebase (Client) ───────────────────────────────────────
NEXT_PUBLIC_FIREBASE_API_KEY=AIzaSy...
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=neighborshare-xxxxx.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=neighborshare-xxxxx
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=neighborshare-xxxxx.appspot.com
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=123456789
NEXT_PUBLIC_FIREBASE_APP_ID=1:123456789:web:abc123

# ─── Google Maps ─────────────────────────────────────────────
NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=AIzaSyB-...

# ─── Razorpay (Client) ───────────────────────────────────────
NEXT_PUBLIC_RAZORPAY_KEY_ID=rzp_test_...

# ─── Gemini AI (Server-side only) ────────────────────────────
GEMINI_API_KEY=AIzaSyD-...

# ─── Razorpay (Server-side only) ─────────────────────────────
RAZORPAY_KEY_ID=rzp_test_...
RAZORPAY_KEY_SECRET=...

# ─── Firebase Admin SDK (Server-side only) ───────────────────
FIREBASE_ADMIN_SDK_JSON={"type":"service_account","project_id":"..."}
```

> ⚠️ **Security Note:** Variables prefixed with `NEXT_PUBLIC_` are exposed to the browser. Never put secrets there. `GEMINI_API_KEY`, `RAZORPAY_KEY_SECRET`, and `FIREBASE_ADMIN_SDK_JSON` must stay server-side only.

### How to Get Each Key

| Key | Source |
|-----|--------|
| Firebase keys | [console.firebase.google.com](https://console.firebase.google.com) → Project Settings → Your Apps |
| Google Maps key | [console.cloud.google.com](https://console.cloud.google.com) → APIs & Services → Credentials |
| Gemini key | [aistudio.google.com](https://aistudio.google.com) → Get API Key |
| Razorpay keys | [dashboard.razorpay.com](https://dashboard.razorpay.com) → Settings → API Keys |
| Firebase Admin SDK | Firebase Console → Project Settings → Service Accounts → Generate Key |

---

## 📁 Project Structure

```
neighborshare/
├── app/                          # Next.js App Router
│   ├── (auth)/
│   │   └── auth/                 # Login / Signup page
│   ├── onboarding/               # Neighborhood verification
│   ├── dashboard/                # Main feed (protected)
│   ├── browse/                   # Browse all items
│   ├── map/                      # Full-screen map view
│   ├── items/
│   │   ├── [id]/                 # Item detail page
│   │   └── new/                  # Create listing
│   ├── skills/                   # Skill exchange listings
│   ├── requests/                 # Borrow requests
│   ├── chat/
│   │   └── [conversationId]/     # Real-time chat
│   ├── transactions/             # Payment history
│   ├── profile/
│   │   └── [userId]/             # Public profile
│   ├── settings/                 # Account settings
│   ├── admin/                    # Admin dashboard (protected)
│   └── api/
│       ├── gemini/               # Gemini AI endpoint
│       ├── razorpay/
│       │   ├── create-order/     # Create payment order
│       │   └── webhook/          # Razorpay webhook handler
│       └── notifications/        # FCM notification sender
│
├── components/
│   ├── ui/                       # Reusable UI components
│   ├── Navbar.tsx                # Navigation with auth state
│   ├── MapView.tsx               # Google Maps component
│   ├── ItemCard.tsx              # Item listing card
│   ├── TrustBadge.tsx            # Trust score badge
│   ├── ChatWindow.tsx            # Real-time chat UI
│   └── PaymentModal.tsx          # Razorpay payment flow
│
├── lib/
│   ├── firebase.ts               # Firebase initialization
│   ├── firebaseAdmin.ts          # Firebase Admin SDK
│   ├── gemini.ts                 # Gemini API client
│   └── razorpay.ts               # Razorpay client
│
├── hooks/
│   ├── useAuth.ts                # Auth state hook
│   ├── useNearbyItems.ts         # Firestore items query
│   └── useChat.ts                # Real-time chat hook
│
├── types/
│   └── index.ts                  # TypeScript type definitions
│
├── firestore.rules               # Firestore security rules
├── .env.local                    # Environment variables (git-ignored)
├── .env.example                  # Environment variables template
└── next.config.js                # Next.js configuration
```

---

## 🔌 API Routes

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/gemini` | Generate AI content (description, search, price) |
| `POST` | `/api/razorpay/create-order` | Create a new Razorpay payment order |
| `POST` | `/api/razorpay/webhook` | Handle Razorpay payment webhooks |
| `POST` | `/api/notifications/send` | Send FCM push notification |

---

## 🗄️ Database Schema

### users/{userId}
```typescript
{
  uid: string
  name: string
  email: string
  photoURL: string
  neighborhood: { name: string, lat: number, lng: number, radius: number }
  trustScore: number          // 0-100
  totalBorrows: number
  totalLends: number
  upiId: string
  role: 'user' | 'admin'
  createdAt: Timestamp
}
```

### listings/{listingId}
```typescript
{
  ownerId: string
  title: string
  description: string
  category: 'tools' | 'household' | 'electronics' | 'skills' | 'other'
  pricePerHour: number
  pricePerDay: number
  isFree: boolean
  depositAmount: number
  condition: 'new' | 'good' | 'fair'
  photos: string[]            // Firebase Storage URLs
  location: { lat: number, lng: number, address: string }
  availability: object[]
  isActive: boolean
  borrowCount: number
  rating: number
  type: 'item' | 'skill'
  createdAt: Timestamp
}
```

### requests/{requestId}
```typescript
{
  borrowerId: string
  lenderId: string
  listingId: string
  startTime: Timestamp
  endTime: Timestamp
  status: 'pending' | 'accepted' | 'declined' | 'active' | 'completed' | 'disputed'
  totalAmount: number
  depositAmount: number
  razorpayOrderId: string
  razorpayPaymentId: string
}
```

---

## 📱 Screenshots

| Landing Page | Browse | Item Detail |
|-------------|--------|-------------|
| Dark neon themed hero | Map + list toggle | Full listing details |

| Chat | Payment | Admin |
|------|---------|-------|
| Real-time messaging | Razorpay escrow flow | Dispute management |

---

## 🗺️ Roadmap

### Phase 1 — MVP ✅ (Current)
- [x] Firebase Auth (Google + Phone OTP)
- [x] Item listing marketplace
- [x] Google Maps neighborhood scoping
- [x] Razorpay payments + deposit escrow
- [x] Real-time chat
- [x] Trust score + rating system

### Phase 2 — AI & Growth (Q3 2026)
- [ ] Gemini AI smart search
- [ ] Skill exchange module
- [ ] Society & RWA admin portal
- [ ] College campus expansion
- [ ] Premium lender subscriptions (₹99/month)

### Phase 3 — Scale (2027)
- [ ] Pan-India expansion (50 cities)
- [ ] WhatsApp bot integration
- [ ] Insurance partnerships for deposits
- [ ] Carbon footprint tracking
- [ ] Mobile app (React Native)

---

## 🔒 Firestore Security Rules

Deploy security rules to Firebase:

```bash
firebase deploy --only firestore:rules
```

Rules are defined in `firestore.rules` — users can only read/write their own data, listings are scoped to authenticated users, and chat messages are restricted to conversation participants.

---

## 🧪 Testing the Payment Flow

Razorpay test mode cards:

| Card Number | Expiry | CVV | Result |
|------------|--------|-----|--------|
| 4111 1111 1111 1111 | Any future | Any | Success |
| 5267 3181 8797 5449 | Any future | Any | Success |
| 4000 0000 0000 0002 | Any future | Any | Failure |

Test UPI ID: `success@razorpay`

---

## 👑 Setting Up Admin Access

1. Sign in to the app with your Google account
2. Go to [Firebase Console](https://console.firebase.google.com) → Firestore Database
3. Find your user document in the `users` collection
4. Add field: `role` → `string` → `admin`
5. Refresh the app → navigate to `/admin`

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

---

## 👩‍💻 Built By

**Divya Singh** 

Built with ❤️ for Indian neighborhoods. Every colony deserves a sharing economy.

## 🙏 Acknowledgements

- [Firebase](https://firebase.google.com) — Auth, Database & Storage
- [Google Maps Platform](https://developers.google.com/maps) — Location & Maps
- [Google Gemini](https://ai.google.dev) — AI Features
- [Razorpay](https://razorpay.com) — Payment Infrastructure
- [Next.js](https://nextjs.org) — React Framework
- [Tailwind CSS](https://tailwindcss.com) — Styling


