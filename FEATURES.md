# Fabric Academy Platform - Feature Specification

**Project:** Fabric Academy Platform  
**Type:** B2B SaaS Platform  
**Target:** Marketing teams seeking coaching and training  
**Created:** 2026-02-01  
**Last Updated:** 2026-02-04  

---

## Overview

Marketing coaching and training platform combining:
- Skills & behavioral assessments
- Personalized learning pathways
- 1-1 and group coaching
- On-demand content library
- Real-time progress tracking
- Quarterly impact reporting

**Total Features:** 25  
**Total Estimated Hours:** 676  
**Estimated Build Time:** 3-4 months (focused effort)

---

## Feature List

### 🔴 CRITICAL PRIORITY

#### F001: User Authentication & Registration
**Priority:** Critical  
**Category:** Core  
**Estimate:** 24 hours  
**Status:** Backlog  

**Description:**  
Multi-role authentication system supporting four user types:
- Learners (individual users taking courses)
- Coaches (deliver 1-1 and group sessions)
- Company Admins (manage teams, view reports)
- Platform Admins (system configuration)

**Requirements:**
- Email/password authentication
- OAuth (Google, Microsoft)
- Role-based access control (RBAC)
- Password reset flow
- Email verification
- Session management
- Multi-factor authentication (optional)

**Technical Notes:**
- JWT tokens for auth
- Refresh token rotation
- Secure password hashing (bcrypt)

---

### 🟠 HIGH PRIORITY

#### F002: Skills & Behavioral Assessment Tool
**Priority:** High  
**Category:** Assessment  
**Estimate:** 40 hours  
**Status:** Backlog  

**Description:**  
Interactive assessment to identify strengths, gaps, and growth opportunities across both technical marketing skills and behavioral/mindset traits.

**Requirements:**
- Question bank (skills + behavioral)
- Progress tracking during assessment
- Scoring algorithm
- Results visualization
- Downloadable results PDF
- Re-assessment capability (track growth over time)

**Assessment Areas:**
- Marketing skills (strategy, analytics, content, channels)
- Behavioral traits (confidence, collaboration, strategic thinking)
- Leadership capabilities

**Technical Notes:**
- Store results for historical comparison
- Algorithm to map results to learning pathways

---

#### F003: Personalized Learning Pathway Builder
**Priority:** High  
**Category:** Learning  
**Estimate:** 48 hours  
**Status:** Backlog  

**Description:**  
Algorithm-driven system that generates customized development journeys based on assessment results, role, and company goals.

**Requirements:**
- Pathway recommendation engine
- Mix of content types (coaching, videos, workshops)
- Timeline/milestone setting
- Adaptive pathways (adjust based on progress)
- Visual pathway map for learners
- Admin override capability

**Pathway Components:**
- Recommended 1-1 coaching sessions
- On-demand video courses
- Live workshops/programmes
- Reading materials/resources
- Action items/exercises

**Technical Notes:**
- Rule-based recommendation system (Phase 1)
- ML-based recommendations (Phase 2 - optional)

---

#### F004: 1-1 Coaching Booking System
**Priority:** High  
**Category:** Coaching  
**Estimate:** 32 hours  
**Status:** Backlog  

**Description:**  
Scheduling system for learners to book individual coaching sessions with matched coaches.

**Requirements:**
- Calendar integration (Google Calendar, Outlook)
- Timezone handling
- Session duration options (30/60/90 min)
- Automated reminders (email/SMS)
- Video conferencing link generation (Zoom/Meet/Teams)
- Reschedule/cancel functionality
- Coach availability checking
- Session history

**Technical Notes:**
- Google Calendar API / Microsoft Graph API
- Webhook support for calendar updates
- Buffer time between sessions

---

#### F006: On-Demand Learning Library
**Priority:** High  
**Category:** Content  
**Estimate:** 36 hours  
**Status:** Backlog  

**Description:**  
Video library with courses, modules, and lessons. Content organized by topic, skill level, and learning pathway.

**Requirements:**
- Video player with playback controls
- Course catalog with search/filter
- Content categorization (tags, topics, difficulty)
- Progress tracking (% complete per course)
- Bookmarking/favorites
- Continue watching
- Transcript display (optional)
- Download option for offline viewing (optional)

**Content Categories:**
- Marketing strategy
- Channel-specific skills (SEO, PPC, Social, Email)
- Analytics & reporting
- Leadership & soft skills

**Technical Notes:**
- Video hosting (Vimeo/Mux)
- CDN for fast delivery
- Adaptive bitrate streaming

---

#### F007: Coach Profile & Matching System
**Priority:** High  
**Category:** Coaching  
**Estimate:** 24 hours  
**Status:** Backlog  

**Description:**  
Coach profiles showcasing expertise, experience, and background. Automated matching algorithm pairs learners with best-fit coaches.

**Requirements:**
- Coach profile pages (bio, experience, specialties)
- Expertise tags (B2B, B2C, SaaS, Brand, Performance, etc.)
- Industry background
- Learner reviews/ratings
- Availability status
- Automated matching based on:
  - Learner assessment results
  - Industry preference
  - Specialty needs
  - Availability
- Manual coach selection option

**Coach Backgrounds:**
- CMOs
- Heads of Brand
- Strategy Directors
- Marketing Leaders at top brands

**Technical Notes:**
- Matching algorithm (weighted scoring)
- Override capability for admins

---

#### F008: Progress Tracking Dashboard (Learner)
**Priority:** High  
**Category:** Analytics  
**Estimate:** 32 hours  
**Status:** Backlog  

**Description:**  
Real-time dashboard showing learner progress across skills, confidence, and behavior. Visual indicators and milestone tracking.

**Requirements:**
- Skills progress bars
- Confidence score (self-reported + coach-assessed)
- Behavioral growth metrics
- Completed sessions/courses
- Upcoming sessions/milestones
- Achievement badges
- Historical trend charts
- Goal tracking

**Metrics Displayed:**
- Skills development (before/after assessment)
- Confidence levels (1-10 scale)
- Learning hours completed
- Pathway completion %
- Coaching sessions attended

**Technical Notes:**
- Chart.js or D3.js for visualizations
- Real-time updates after sessions/courses

---

#### F012: Content Delivery & Streaming
**Priority:** High  
**Category:** Content  
**Estimate:** 32 hours  
**Status:** Backlog  

**Description:**  
Robust video hosting and streaming infrastructure. Adaptive streaming, playback tracking, and transcript generation.

**Requirements:**
- Video upload pipeline (for admins)
- Encoding/transcoding
- Adaptive bitrate streaming
- Playback position tracking (resume where you left off)
- Subtitles/captions support
- Transcript generation (auto or manual)
- Playback analytics (watch time, completion rate)
- DRM/content protection (optional)

**Technical Notes:**
- Vimeo API or Mux for video processing
- CDN integration (Cloudflare, Fastly)
- S3 or similar for storage

---

#### F015: Payment & Subscription Management
**Priority:** High  
**Category:** Monetization  
**Estimate:** 32 hours  
**Status:** Backlog  

**Description:**  
Stripe integration for subscription billing, payment processing, and invoice generation.

**Requirements:**
- Tiered pricing plans (Individual, Team, Enterprise)
- Credit card processing
- Subscription management (upgrade/downgrade)
- Invoice generation (auto-email)
- Payment history
- Failed payment handling
- Proration for mid-cycle changes
- Company billing (multiple learners under one account)
- License management (per-seat pricing)

**Pricing Tiers:**
- Individual: £X/month per learner
- Team (5-20 learners): £X/month
- Enterprise (20+): Custom pricing

**Technical Notes:**
- Stripe API (Checkout, Billing, Invoices)
- Webhook handling for payment events
- Grace period for failed payments

---

#### F016: Mobile Responsive Design
**Priority:** High  
**Category:** UX  
**Estimate:** 40 hours  
**Status:** Backlog  

**Description:**  
Fully responsive UI optimized for mobile and tablet. Learners can access content, book sessions, and track progress on-the-go.

**Requirements:**
- Mobile-first design approach
- Touch-friendly UI components
- Responsive video player
- Mobile calendar integration
- Push notifications (optional)
- Offline mode for downloaded content (optional)
- Progressive Web App (PWA) support (optional)

**Target Devices:**
- iOS (Safari)
- Android (Chrome)
- Tablets

**Technical Notes:**
- Tailwind CSS responsive breakpoints
- Service worker for PWA

---

### 🟡 MEDIUM PRIORITY

#### F005: Group Coaching Session Management
**Priority:** Medium  
**Category:** Coaching  
**Estimate:** 28 hours  
**Status:** Backlog  

**Description:**  
Create and manage group coaching sessions. Multiple learners join a single session with one or more coaches.

**Requirements:**
- Group session creation (coach-initiated)
- Attendee limit setting
- Registration/RSVP system
- Waiting list
- Video conferencing (multi-participant)
- Session recordings
- Post-session materials upload
- Attendance tracking

**Technical Notes:**
- Zoom/Teams API for group calls
- Recording storage (S3 + Mux)

---

#### F009: Admin Reporting & Insights Dashboard
**Priority:** Medium  
**Category:** Analytics  
**Estimate:** 40 hours  
**Status:** Backlog  

**Description:**  
Company admin dashboard with quarterly L&D insights, impact reports, and team performance metrics.

**Requirements:**
- Team-wide progress overview
- Skills gap analysis
- Coaching utilization metrics
- Content engagement stats
- ROI metrics (skills improvement, confidence growth)
- Quarterly report generation (PDF)
- Exportable data (CSV/Excel)
- Filterable views (by team, role, date range)

**Key Metrics:**
- Average skill improvement
- Coaching sessions completed
- Content completion rate
- Learner engagement score
- NPS/satisfaction scores

**Technical Notes:**
- PDF generation (jsPDF or similar)
- Chart libraries for visualizations

---

#### F010: Live Programme/Workshop Management
**Priority:** Medium  
**Category:** Learning  
**Estimate:** 28 hours  
**Status:** Backlog  

**Description:**  
Schedule and manage live training programmes and workshops. Registration, attendance tracking, and post-event materials.

**Requirements:**
- Event creation (date, time, duration, capacity)
- Registration system
- Automated reminders
- Video conferencing integration
- Attendance tracking
- Recordings upload
- Post-event resource sharing
- Feedback collection

**Event Types:**
- Live workshops (2-4 hours)
- Multi-day programmes
- Webinars

**Technical Notes:**
- Calendar event creation
- Zoom/Teams integration

---

#### F011: Notification & Reminder System
**Priority:** Medium  
**Category:** Engagement  
**Estimate:** 16 hours  
**Status:** Backlog  

**Description:**  
Automated notifications via email and SMS. Reminders for sessions, new content alerts, and milestone celebrations.

**Notification Types:**
- Upcoming session reminders (24h, 1h before)
- New content published
- Pathway milestone reached
- Feedback requests (post-session)
- Progress reports ready
- Payment/subscription updates

**Channels:**
- Email (primary)
- SMS (optional)
- In-app notifications

**Technical Notes:**
- SendGrid or Postmark for email
- Twilio for SMS
- Notification preferences (user-configurable)

---

#### F013: Session Notes & Action Items
**Priority:** Medium  
**Category:** Coaching  
**Estimate:** 20 hours  
**Status:** Backlog  

**Description:**  
Coaches and learners can add session notes, goals, and action items after 1-1 or group sessions.

**Requirements:**
- Note-taking interface (rich text editor)
- Action item tracking (checklist)
- Goal setting (SMART framework)
- Shared notes (coach + learner visibility)
- Historical notes view
- Export notes (PDF)

**Technical Notes:**
- Rich text editor (Quill or TipTap)
- Markdown support (optional)

---

#### F017: Marketing Landing Pages
**Priority:** Medium  
**Category:** Marketing  
**Estimate:** 24 hours  
**Status:** Backlog  

**Description:**  
Public-facing pages to attract and convert prospects. SEO-optimized, conversion-focused.

**Pages:**
- Homepage
- How It Works
- Pricing
- Coach Profiles (public directory)
- Testimonials/Case Studies
- About Us
- Blog (optional)

**Requirements:**
- SEO optimization (meta tags, schema markup)
- Fast loading (Core Web Vitals)
- Lead capture forms
- CTA buttons (Book a Demo, Start Free Trial)
- Social proof (logos, testimonials, stats)

**Technical Notes:**
- Next.js for SSR/SSG
- Analytics tracking (Google Analytics, Meta Pixel)

---

#### F018: Demo Booking Flow
**Priority:** Medium  
**Category:** Sales  
**Estimate:** 12 hours  
**Status:** Backlog  

**Description:**  
Calendly-style scheduling for prospective clients to book product demos with sales team.

**Requirements:**
- Available time slot selection
- Timezone auto-detection
- Form capture (name, email, company, team size)
- Calendar integration (sales team calendar)
- Automated confirmation email
- Meeting link generation
- Reminder emails

**Technical Notes:**
- Calendly embed or custom build
- HubSpot integration (optional)

---

#### F019: Team Management (Company Admin)
**Priority:** Medium  
**Category:** Admin  
**Estimate:** 28 hours  
**Status:** Backlog  

**Description:**  
Company admins can add/remove learners, assign coaches, view team progress, and manage licenses.

**Requirements:**
- Add/remove team members (bulk upload CSV)
- Assign/reassign coaches
- View team dashboard (progress, engagement)
- License management (per-seat)
- Role assignment (learner, admin)
- Onboarding workflow (send invites)
- Offboarding (data export, account deactivation)

**Technical Notes:**
- CSV import/export
- Email invitations

---

#### F020: Coach Availability Calendar
**Priority:** Medium  
**Category:** Coaching  
**Estimate:** 20 hours  
**Status:** Backlog  

**Description:**  
Coaches set their availability, blocked times, and recurring schedules. Integrates with their personal calendars.

**Requirements:**
- Availability slots (weekly recurring)
- Block off dates/times
- Buffer time settings
- Max sessions per day
- Calendar sync (Google/Outlook)
- Timezone support
- Override for special sessions

**Technical Notes:**
- Calendar API integration
- Conflict detection

---

#### F023: Automated Progress Reports
**Priority:** Medium  
**Category:** Analytics  
**Estimate:** 24 hours  
**Status:** Backlog  

**Description:**  
Auto-generate quarterly progress reports for company admins. Email delivery and PDF export.

**Requirements:**
- Scheduled report generation (quarterly)
- PDF format with branding
- Include: team progress, skills growth, coaching utilization, ROI metrics
- Automated email delivery
- On-demand report generation

**Technical Notes:**
- Cron job or scheduled task
- PDF generation library

---

#### F025: Search & Discovery
**Priority:** Medium  
**Category:** UX  
**Estimate:** 20 hours  
**Status:** Backlog  

**Description:**  
Global search across content, coaches, and resources. Smart filters and autocomplete.

**Requirements:**
- Search bar (global header)
- Autocomplete suggestions
- Filters (content type, topic, difficulty)
- Recent searches
- Search history
- Fuzzy matching

**Search Scope:**
- Video content
- Coaches
- Resources
- Help articles

**Technical Notes:**
- Elasticsearch or Algolia
- Indexed search for performance

---

### 🔵 LOW PRIORITY

#### F014: Feedback & Rating System
**Priority:** Low  
**Category:** Quality  
**Estimate:** 16 hours  
**Status:** Backlog  

**Description:**  
Learners rate sessions and provide feedback on coaches and content quality.

**Requirements:**
- Star rating (1-5)
- Written feedback (optional)
- Post-session survey
- Aggregate ratings (coach/content level)
- Feedback visibility (coach only or public)

**Technical Notes:**
- Store ratings in database
- Calculate averages

---

#### F021: Email Campaign Integration
**Priority:** Low  
**Category:** Marketing  
**Estimate:** 16 hours  
**Status:** Backlog  

**Description:**  
Newsletter signup, automated drip campaigns, and HubSpot integration for marketing automation.

**Requirements:**
- Newsletter subscription form
- Welcome email sequence
- Engagement drip campaigns
- HubSpot sync (contacts, events)
- Unsubscribe management
- Email template builder

**Technical Notes:**
- HubSpot API
- SendGrid for email delivery

---

#### F022: Resource Library (PDFs, Templates)
**Priority:** Low  
**Category:** Content  
**Estimate:** 12 hours  
**Status:** Backlog  

**Description:**  
Downloadable resources, templates, worksheets, and tools for learners.

**Requirements:**
- File upload (admin)
- Categorization (tags, topics)
- Search/filter
- Download tracking
- Preview (for PDFs)

**Resource Types:**
- Strategy templates
- Worksheets
- Checklists
- Reading lists

**Technical Notes:**
- S3 for file storage
- Signed URLs for secure downloads

---

#### F024: API for Third-Party Integrations
**Priority:** Low  
**Category:** Integration  
**Estimate:** 32 hours  
**Status:** Backlog  

**Description:**  
RESTful API for integrations with HRIS, LMS, and CRM systems.

**Endpoints:**
- User management (create, update, delete)
- Progress data export
- Content library access
- Reporting data

**Requirements:**
- API authentication (OAuth 2.0)
- Rate limiting
- API documentation (Swagger/OpenAPI)
- Webhooks for events
- SDKs (optional)

**Integration Targets:**
- HRIS (BambooHR, Workday)
- LMS (Cornerstone, Docebo)
- CRM (Salesforce, HubSpot)

**Technical Notes:**
- RESTful design
- JSON responses
- Versioned API (v1, v2)

---

## Summary by Category

| Category | Features | Total Hours |
|----------|----------|-------------|
| Core | 1 | 24 |
| Assessment | 1 | 40 |
| Learning | 2 | 76 |
| Coaching | 5 | 124 |
| Content | 3 | 80 |
| Analytics | 3 | 96 |
| Engagement | 1 | 16 |
| Quality | 1 | 16 |
| Monetization | 1 | 32 |
| UX | 2 | 60 |
| Marketing | 2 | 40 |
| Sales | 1 | 12 |
| Admin | 1 | 28 |
| Integration | 1 | 32 |

**Total:** 25 features, 676 hours

---

## Summary by Priority

| Priority | Count | Hours |
|----------|-------|-------|
| Critical | 1 | 24 |
| High | 10 | 316 |
| Medium | 11 | 284 |
| Low | 3 | 52 |

---

## Phased Roadmap

### Phase 1: MVP (Core Platform)
**Goal:** Launch beta with core functionality  
**Duration:** 8-10 weeks  
**Features:** F001, F002, F003, F004, F006, F008, F015  
**Hours:** ~244  

### Phase 2: Enhanced Learning
**Goal:** Add group coaching and advanced features  
**Duration:** 6-8 weeks  
**Features:** F005, F007, F010, F013, F011  
**Hours:** ~136  

### Phase 3: Admin & Reporting
**Goal:** Company admin tools and reporting  
**Duration:** 6-8 weeks  
**Features:** F009, F019, F020, F023  
**Hours:** ~112  

### Phase 4: Scale & Polish
**Goal:** Optimization, marketing, integrations  
**Duration:** 6-8 weeks  
**Features:** F012, F016, F017, F018, F014, F021, F022, F024, F025  
**Hours:** ~184  

---

## Tech Stack Recommendations

**Frontend:**
- React + Next.js (SSR/SSG for SEO)
- Tailwind CSS (rapid UI development)
- Chart.js (analytics visualizations)

**Backend:**
- Node.js + Express or Python + FastAPI
- PostgreSQL (relational data)
- Redis (caching, sessions)

**Infrastructure:**
- Video: Vimeo API or Mux
- Payments: Stripe
- Calendar: Google Calendar API
- Email: SendGrid
- Storage: AWS S3
- Hosting: Vercel (frontend) + Railway/AWS (backend)

**AI/ML:**
- Learning pathway recommendations (rule-based → sklearn)
- Coach matching algorithm

---

## Success Metrics

- **User Retention:** Monthly active learners
- **Engagement:** Session completion rate, content watch time
- **Satisfaction:** NPS (learners & admins)
- **Revenue:** MRR, revenue per company
- **Impact:** Skills improvement (pre/post assessment)

---

**Document Version:** 1.0  
**Last Updated:** 2026-02-04  
**Author:** Mr Slave 🎯
