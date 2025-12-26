# HR AI Interview Platform

## Overview
A comprehensive HR platform powered by AI that enables:
- **AI-Powered Interviews**: Conduct real-time chat-based interviews with candidates where AI acts as the interviewer
- **Video Analysis**: Upload video recordings of candidates and get AI-powered analysis and feedback
- **Candidate Management**: Full CRUD for candidates, positions, and interviews
- **Hiring Recommendations**: AI-generated scores and recommendations for hiring decisions

## Tech Stack
- **Frontend**: React + TypeScript with Vite
- **UI Components**: shadcn/ui with Tailwind CSS
- **Backend**: Express.js
- **AI**: OpenAI (gpt-5.1) + Gemini (gemini-2.5-flash for vision) via Replit AI Integrations
- **Storage**: In-memory storage (MemStorage)
- **Routing**: wouter
- **State Management**: TanStack Query

## Project Structure
```
├── client/src/
│   ├── components/        # Reusable UI components
│   │   ├── ui/           # shadcn/ui components
│   │   ├── app-sidebar.tsx
│   │   └── theme-toggle.tsx
│   ├── pages/            # Page components
│   │   ├── dashboard.tsx
│   │   ├── candidates.tsx
│   │   ├── positions.tsx
│   │   ├── interviews.tsx
│   │   ├── interview-chat.tsx
│   │   ├── video-interview.tsx
│   │   ├── videos.tsx
│   │   ├── reports.tsx
│   │   └── settings.tsx
│   ├── hooks/            # Custom hooks
│   ├── lib/              # Utilities
│   └── App.tsx           # Main app with routing
├── server/
│   ├── routes.ts         # API endpoints
│   ├── storage.ts        # In-memory data storage
│   └── replit_integrations/  # AI integration modules
├── shared/
│   └── schema.ts         # Data models and types
└── design_guidelines.md  # UI design system
```

## Key Features

### Dashboard
- Overview stats: total candidates, pending reviews, active interviews, hired this month
- Recent candidates list
- Upcoming interviews
- Open positions

### Candidates
- Add/edit/delete candidates
- Filter by status
- Search functionality
- Link to positions

### Positions
- Job opening management
- Department categorization
- Status tracking (open/closed/paused)

### AI Interviews (Chat)
- Real-time chat interface with streaming responses
- AI conducts interviews as a professional HR interviewer
- Automatic transcript generation
- Complete and analyze to get AI evaluation

### Video Call Interviews (NEW)
- Real-time video interview with WebRTC camera access
- AI speaks questions using text-to-speech (browser SpeechSynthesis)
- Speech recognition transcribes candidate responses (browser Web Speech API)
- Periodic frame capture analyzes facial expressions and gestures (Gemini Vision)
- Combined analysis of verbal + non-verbal communication
- Metrics: confidence level, eye contact, posture, expressions

### Video Analysis
- Upload video metadata with transcriptions
- AI analyzes content and provides feedback
- Scoring on communication, technical, and cultural fit

### Reports
- Aggregated analysis results
- Hiring recommendations overview
- Score breakdowns by candidate

## API Endpoints

### Dashboard
- `GET /api/dashboard/stats` - Get dashboard statistics

### Positions
- `GET /api/positions` - List all positions
- `GET /api/positions/:id` - Get position details
- `POST /api/positions` - Create position
- `PATCH /api/positions/:id` - Update position
- `DELETE /api/positions/:id` - Delete position

### Candidates
- `GET /api/candidates` - List all candidates
- `GET /api/candidates/:id` - Get candidate details
- `POST /api/candidates` - Create candidate
- `PATCH /api/candidates/:id` - Update candidate
- `DELETE /api/candidates/:id` - Delete candidate

### Interviews
- `GET /api/interviews` - List all interviews
- `GET /api/interviews/:id` - Get interview with messages and analysis
- `POST /api/interviews` - Create interview
- `POST /api/interviews/:id/messages` - Send message (SSE streaming)
- `POST /api/interviews/:id/complete` - Complete and analyze interview

### Video Interview
- `POST /api/video-interview/:id/message` - Send speech transcript, get AI response (SSE)
- `POST /api/video-interview/:id/analyze-frame` - Analyze video frame for expressions/gestures
- `POST /api/video-interview/:id/complete` - Complete video interview with full analysis

### Videos
- `GET /api/videos` - List all videos
- `GET /api/videos/:id` - Get video details
- `POST /api/videos` - Register video
- `POST /api/videos/:id/analyze` - Analyze video with AI

### Analysis
- `GET /api/analyses` - List all analysis results
- `GET /api/analyses/:id` - Get analysis details

## Running the Application
The app runs on port 5000 with `npm run dev`. Frontend and backend are served together via Vite.

## Design System
Uses Material Design 3 principles with Inter font. See `design_guidelines.md` for full design specifications.
