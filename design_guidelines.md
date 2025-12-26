# HR AI Interview Platform - Design Guidelines

## Design Approach
**System Selected**: Material Design 3 (Modern, professional productivity focus)
**Justification**: HR platforms require trust, efficiency, and clarity. Material Design 3 provides robust component patterns for data-heavy interfaces while maintaining a modern, approachable aesthetic that reduces user anxiety during high-stakes hiring decisions.

## Typography System
- **Primary Font**: Inter (via Google Fonts CDN)
- **Headings**: 
  - H1: 32px/40px, font-weight: 700
  - H2: 24px/32px, font-weight: 600
  - H3: 20px/28px, font-weight: 600
- **Body**: 16px/24px, font-weight: 400
- **UI Elements**: 14px/20px, font-weight: 500
- **Captions/Metadata**: 12px/16px, font-weight: 400

## Layout & Spacing System
**Tailwind Units**: Consistently use 2, 4, 6, 8, 12, and 16 for all spacing
- Component padding: p-4 to p-6
- Section spacing: py-8 to py-12
- Card gaps: gap-6
- Form field spacing: space-y-4

**Grid System**:
- Dashboard: 12-column responsive grid
- Video preview: 16:9 aspect ratio containers
- Candidate cards: 3-column grid (lg:grid-cols-3 md:grid-cols-2 grid-cols-1)

## Core Components

### Navigation
- **Primary**: Persistent left sidebar (w-64), collapsible on mobile
- **Structure**: Logo top, main nav items with icons (Heroicons), user profile bottom
- **Mobile**: Hamburger menu overlay

### Dashboard Layout
- **Main Content Area**: max-w-7xl mx-auto, px-6
- **Stats Cards**: 4-column grid showing active interviews, pending reviews, candidates analyzed, hiring recommendations
- **Recent Activity**: Timeline-style list with avatar, action, timestamp

### Interview Interface
- **Layout**: Split view - Video feed (60% width) | AI Analysis Panel (40% width)
- **Video Controls**: Bottom-aligned overlay with record, pause, end, settings
- **AI Panel**: Real-time transcription, sentiment indicators, key insights feed

### Candidate Review Cards
- **Structure**: 
  - Header: Avatar, name, position, application date
  - Body: AI summary scores (communication, technical, cultural fit) with progress bars
  - Footer: Video thumbnail, view full analysis CTA, status badge
- **Spacing**: p-6 cards with rounded-xl borders

### Video Analysis Results
- **Layout**: Two-column (lg:grid-cols-2)
  - Left: Video player with timestamp markers
  - Right: Tabbed interface (Overview, Transcript, Metrics, Comparison)
- **Metrics Display**: Radial progress charts for scoring dimensions

### Forms & Inputs
- **Style**: Outlined inputs with floating labels (Material Design pattern)
- **Validation**: Inline error messages, mb-1
- **Button Hierarchy**: 
  - Primary: Filled, font-weight: 600
  - Secondary: Outlined
  - Tertiary: Text only

## Component Library

**Icons**: Heroicons (CDN)
- Navigation: outline style, 24px
- Cards/Buttons: solid style, 20px
- Status indicators: mini style, 16px

**Data Displays**:
- Tables: Striped rows, hover states, sticky headers
- Progress Indicators: Linear bars for scores, circular for completion
- Badges: Rounded-full, px-3 py-1, uppercase text-xs

**Overlays**:
- Modals: max-w-2xl, p-6, centered with backdrop
- Tooltips: Compact, appear on hover for complex metrics
- Notifications: Toast style, top-right, auto-dismiss

## Animations
**Minimal & Purposeful**:
- Page transitions: Fade-in only (duration-200)
- Loading states: Skeleton screens for cards/tables
- NO scroll animations, parallax, or decorative motion

## Images

**Hero Section**: 
- Full-width background image (h-96) showing professional interview setting
- Overlay gradient for text readability
- Centered headline + CTA with blur backdrop (backdrop-blur-sm bg-white/30)

**Candidate Avatars**: 
- Circular, 48px standard, 64px on detail pages
- Placeholder: Initials on solid background if no photo

**Empty States**:
- Illustrations for "No candidates yet", "No active interviews"
- Centered, max-w-md, supportive not decorative

## Page-Specific Layouts

**Dashboard**: Stats grid → Quick actions → Recent activity table → Upcoming interviews calendar
**Interview Queue**: Filter bar → Candidate card grid with sorting
**Live Interview**: Fullscreen mode option, picture-in-picture support
**Analysis Report**: Breadcrumb navigation → Video + metrics split → Detailed breakdown accordion → Comparison tool → Export/Share actions