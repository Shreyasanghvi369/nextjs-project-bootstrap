# Revika Website Enhancement Plan

## Overview
Transform the Revika healing website with images, interactivity, full shopping cart system, enhanced payment gateway, and new pages.

## Priority Order Implementation
1. **Payment & Cart System** (Highest Priority)
2. **Interactivity Features** 
3. **Images & Visual Enhancements**
4. **New Pages (Home & About Founder)**

## Detailed Implementation Plan

### Phase 1: Payment & Cart System Enhancement

#### 1.1 Shopping Cart Infrastructure
- **Cart Context & State Management**
  - Create `src/contexts/CartContext.tsx` - Global cart state
  - Cart items storage with localStorage persistence
  - Add/remove/update quantity functions
  - Cart total calculations

- **Cart Components**
  - `src/components/Cart/CartDrawer.tsx` - Sliding cart panel
  - `src/components/Cart/CartItem.tsx` - Individual cart item
  - `src/components/Cart/CartSummary.tsx` - Order summary
  - `src/components/Cart/AddToCartButton.tsx` - Enhanced add to cart

#### 1.2 Enhanced Stripe Integration
- **Stripe Setup**
  - Install `@stripe/stripe-js` and `stripe` packages
  - Create `src/lib/stripe.ts` - Stripe configuration
  - Environment variables setup (.env.local)

- **Payment Components**
  - `src/components/Payment/CheckoutForm.tsx` - Multi-item checkout
  - `src/components/Payment/PaymentMethods.tsx` - Payment options
  - `src/components/Payment/SubscriptionManager.tsx` - Membership billing

- **API Routes**
  - `src/app/api/create-checkout-session/route.ts` - Checkout sessions
  - `src/app/api/webhooks/stripe/route.ts` - Webhook handling
  - `src/app/api/subscriptions/route.ts` - Subscription management

#### 1.3 Order Management
- **Order System**
  - `src/components/Orders/OrderHistory.tsx` - User order history
  - `src/components/Orders/OrderConfirmation.tsx` - Success page
  - Order tracking and status updates

### Phase 2: Interactivity Features

#### 2.1 Animations & Transitions
- **Framer Motion Integration**
  - Install `framer-motion` package
  - Page transitions and scroll animations
  - Hover effects and micro-interactions
  - Loading states and skeleton screens

- **Interactive Components**
  - `src/components/Interactive/AnimatedCounter.tsx` - Stats counters
  - `src/components/Interactive/ScrollReveal.tsx` - Scroll animations
  - `src/components/Interactive/HoverCards.tsx` - Enhanced service cards

#### 2.2 Interactive Forms
- **Enhanced Forms**
  - `src/components/Forms/ContactForm.tsx` - Contact inquiries
  - `src/components/Forms/AssessmentForm.tsx` - Healing assessment
  - `src/components/Forms/NewsletterSignup.tsx` - Email subscription
  - Form validation with react-hook-form + zod

#### 2.3 Image Galleries
- **Gallery Components**
  - `src/components/Gallery/ImageGallery.tsx` - Service images
  - `src/components/Gallery/TestimonialGallery.tsx` - Client testimonials
  - `src/components/Gallery/RetreatGallery.tsx` - Retreat photos
  - Lightbox functionality for image viewing

### Phase 3: Images & Visual Enhancements

#### 3.1 Image Integration
- **Image Assets**
  - `public/images/services/` - Service illustrations
  - `public/images/testimonials/` - Client photos
  - `public/images/healing/` - Healing-themed visuals
  - `public/images/founder/` - Founder photos

- **Image Components**
  - `src/components/Images/OptimizedImage.tsx` - Next.js Image wrapper
  - `src/components/Images/ImageWithFallback.tsx` - Error handling
  - `src/components/Images/LazyImage.tsx` - Lazy loading

#### 3.2 Visual Enhancements
- **UI Improvements**
  - Enhanced gradients and backgrounds
  - Better typography hierarchy
  - Improved spacing and layout
  - Mobile-responsive image handling

### Phase 4: New Pages

#### 4.1 Enhanced Home Page
- **New Home Structure**
  - `src/app/home/page.tsx` - Dedicated home page
  - Hero section with founder image
  - Featured services showcase
  - Client testimonials section
  - Quick booking CTA

#### 4.2 About Founder Page
- **Founder Page**
  - `src/app/about/page.tsx` - About founder
  - Founder story and background
  - Credentials and certifications
  - Personal healing journey
  - Professional photos and testimonials

## Technical Requirements

### Dependencies to Add
```json
{
  "@stripe/stripe-js": "^2.4.0",
  "stripe": "^14.21.0",
  "framer-motion": "^11.0.0",
  "react-hook-form": "^7.56.3",
  "zod": "^3.24.4",
  "@hookform/resolvers": "^5.0.1"
}
```

### Environment Variables
```
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=pk_test_...
STRIPE_SECRET_KEY=sk_test_...
STRIPE_WEBHOOK_SECRET=whsec_...
NEXT_PUBLIC_CALENDLY_URL=https://calendly.com/revika-healing
```

### File Structure Changes
```
src/
├── app/
│   ├── home/page.tsx (new)
│   ├── about/page.tsx (new)
│   ├── cart/page.tsx (new)
│   └── api/
│       ├── create-checkout-session/route.ts (new)
│       ├── webhooks/stripe/route.ts (new)
│       └── subscriptions/route.ts (new)
├── components/
│   ├── Cart/ (new directory)
│   ├── Payment/ (new directory)
│   ├── Interactive/ (new directory)
│   ├── Forms/ (new directory)
│   ├── Gallery/ (new directory)
│   └── Images/ (new directory)
├── contexts/
│   └── CartContext.tsx (new)
├── lib/
│   └── stripe.ts (new)
└── hooks/
    ├── useCart.ts (new)
    └── useLocalStorage.ts (new)
```

## Implementation Timeline
- **Week 1**: Cart system and Stripe integration
- **Week 2**: Interactive features and animations
- **Week 3**: Image integration and galleries
- **Week 4**: New pages and final polish

## Success Metrics
- Functional shopping cart with multiple items
- Stripe payment processing for single and multiple items
- Subscription billing for memberships
- Smooth animations and interactions
- Professional image galleries
- Enhanced user experience
- Mobile-responsive design
