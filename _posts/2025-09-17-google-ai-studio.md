---
title: "Google AI Studio"
date: 2025-09-17 10:00:00 -0700
categories: architectures
---

## Google AI Studio

Google AI Studio is a collaborative platform that allows users to build, deploy, and manage AI models and applications. It provides tools for data scientists, developers, and business users to work together on AI projects.

[google aistudio/](https://aistudio.google.com/)


### Example of prompt to build an app with Google AI Studio

Starting prompt:

``` plaintext
Generate a Web app design for the UTU Merchant Engagement Program (MEP). The app's primary purpose is to empower merchant staff to track performance and manage promotions. The app should be clean, modern, and branded with UTU’s core colors: teal (#00A79C) and a vibrant accent green (#6BCB7C).

The app should have the following key screens and features:
1. **Login**: A clean login screen followed by a dashboard that serves as the home screen. The login screen should be simple, with fields for username and password, and a "Forgot Password" link. Social media login options (e.g., Google, Facebook) can be included for convenience.

2. **Dashboard**: A clean dashboard that serves as the home screen. The dashboard should display key performance metrics for the current day, week, and month. Key metrics should include:
  - *Total Vouchers Issued*: Number of vouchers issued to customers.
  - *Total Upsell Value*: The total amount spent using UTU vouchers.
  The dashboard should show a linear progress bar indicating progress towards monthly goals for both metrics.
  - Conversion Rate: Percentage of customers who used vouchers out of total customers.
  - Total customers served.

  Performance Summary Cards: Two cards displaying:
  - This week's total vouchers count along with the upsell value. A badge indicating the performance against the last week.
  - This month's total vouchers count along with the upsell value. A badge indicating the performance against the last month.

3. **Academic**: A section dedicated to academic resources, including articles, tutorials, and case studies related to AI and machine learning. This section should be easily navigable with categories and a search function.

4. **Incentive Program Management**: A screen that show the details of the incentive program, including:
  - *Ambassador Tier*: Information about the ambassador tier, including eligibility criteria and benefits.
  - *Reward Catalogue*: A list of available rewards that staff can redeem using their earned points, with images and descriptions.

5. **Settings & Profile**: A screen for managing account settings, including staff profiles, store details, and push notification preferences.

The design should be intuitive and user-friendly, with a focus on quick, actionable insights for busy retail staff.

The application should be responsive and optimized for both iOS and Android devices. Use modern design principles, ensuring that the app is visually appealing and easy to navigate.
The application should also include onboarding screens to guide new users through the app's features.
The application should be built based on React and Tailwind CSS.
```

---

# UTU Merchant Engagement Program (MEP) - Web Application Design Brief

## Project Overview
Design a responsive web application for the UTU Merchant Engagement Program targeting **merchant staff/ambassadors** in retail environments. The app empowers users to track performance metrics, manage promotions, and participate in an incentive program.

## Target Users
- **Primary**: Retail staff/ambassadors using the UTU reward system
- **Secondary**: Store managers monitoring team performance
- **Environment**: Fast-paced retail settings, mobile-first usage

## Brand Guidelines
- **Primary Color**: Teal (#00A79C)
- **Accent Color**: Vibrant Green (#6BCB7C)
- **Design Language**: Clean, modern, accessible
- **Typography**: Sans-serif, high readability on mobile devices

## Technical Requirements
- **Frontend**: React with Tailwind CSS
- **Responsive**: Mobile-first design optimized for iOS/Android browsers
- **Performance**: < 3s load time on 3G networks
- **Offline Support**: Cache critical data for basic functionality
- **Accessibility**: WCAG 2.1 AA compliance

## Core Features & User Flows

### 1. Authentication & Onboarding
**Login Screen:**
- Username/password fields with validation
- "Remember me" option
- "Forgot Password" flow
- Optional: SSO integration (Google/Microsoft)
- Error handling with clear messaging

**Onboarding Flow (First-time users):**
- Welcome screens introducing key features
- Tutorial for issuing first voucher
- Goal-setting wizard for personal targets
- Skip option for returning users

### 2. Dashboard (Home Screen)
**Primary Metrics (Prominent display):**
- Total Vouchers Issued (daily/weekly/monthly views)
- Total Upsell Value with currency formatting
- Progress bars toward personal/team goals with percentage completion
- Visual indicators for goal achievement (badges/icons)

**Secondary Metrics:**
- Conversion Rate (vouchers redeemed vs issued)
- Total Customers Served
- Average voucher value

**Performance Cards:**
- **Weekly Summary**: Voucher count + upsell value with trend indicator (↗️↘️)
- **Monthly Summary**: Same format with month-over-month comparison
- **Quick Actions**: "Issue Voucher" and "View Rewards" buttons

**Data Refresh:**
- Real-time updates or manual refresh option
- Loading states and error handling
- Offline mode indicator

### 3. Learning Center (Previously "Academic")
**Purpose**: Product knowledge and sales training resources

**Features:**
- Categorized content (Product Info, Sales Techniques, UTU Updates)
- Search functionality with filters
- Progress tracking for completed materials
- Downloadable resources for offline access
- Interactive quizzes or assessments

### 4. Incentive Program Management
**Ambassador Profile:**
- Current tier status with visual progress indicator
- Points balance and earning history
- Requirements for next tier advancement
- Achievement badges and milestones

**Reward Catalogue:**
- Grid/card layout with high-quality images
- Point costs clearly displayed
- Redemption status (available, out of stock, redeemed)
- Wishlist functionality
- Redemption history

### 5. Settings & Profile
**Account Management:**
- Personal information editing
- Store/location assignment
- Language preferences
- Notification settings (push, email, in-app)

**App Settings:**
- Theme preferences (light/dark mode)
- Data usage settings
- Cache management
- Help/Support contact information

## User Experience Priorities

### Navigation
- Bottom tab bar for main sections on mobile
- Breadcrumb navigation for deeper screens
- One-handed operation optimization
- Clear visual hierarchy

### Performance Indicators
- Loading skeletons for data-heavy screens
- Progressive image loading
- Optimistic UI updates where possible
- Graceful error states with retry options

### Accessibility
- High contrast ratios for outdoor retail use
- Large touch targets (44px minimum)
- Screen reader compatibility
- Keyboard navigation support

## Edge Cases & Error Handling
- Network connectivity loss scenarios
- Invalid/expired authentication tokens
- Empty states (no vouchers issued, no rewards available)
- Server maintenance/downtime messaging
- Data synchronization conflicts

## Success Metrics
- Time to complete primary actions (issue voucher, check progress)
- Daily/weekly active usage rates
- Feature adoption rates (learning center, reward redemption)
- User satisfaction scores

## Technical Considerations
- Progressive Web App (PWA) capabilities
- Browser compatibility (Safari, Chrome, Firefox mobile)
- Touch gesture support
- Battery usage optimization
- Data usage awareness (image optimization, API efficiency)

## Future Considerations
- Integration with POS systems
- Team collaboration features
- Manager dashboard with team overview
- Advanced analytics and reporting
- Gamification elements (leaderboards, challenges)

## Questions to Clarify
1. What's the expected concurrent user volume?
2. Are there integration requirements with existing merchant systems?
3. What's the data retention policy for performance metrics?
4. Are there regional/language localization needs?
5. What level of analytics/tracking is required?

