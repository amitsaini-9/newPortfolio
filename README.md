# Disaster Tracker

A real-time disaster information aggregation system built for tracking and monitoring disasters across India, providing timely updates, news, and AI-powered insights to assist with disaster management and response.

## Features

- **Real-time Disaster Tracking**: Monitor active disasters across India with interactive map visualization
- **Disaster Information Dashboard**: View detailed statistics, impacts, and status updates
- **News Aggregation**: Automatically fetch and display disaster-related news from multiple sources
- **AI-Powered Analysis**: Get intelligent insights, severity classifications, and impact predictions
- **Risk Assessment**: View region-specific disaster risk analysis and predictions
- **Emergency Assistant**: AI chatbot providing guidance during disaster situations

## Tech Stack

- **Frontend**: Next.js with TypeScript
- **Styling**: Tailwind CSS with shadcn/ui and aceternityui components
- **Database**: Postgressq
- **Maps**: Leaflet for interactive mapping
- **State Management**: React Hooks and Context API
- **Data Visualization**: Recharts
- **Animation**: Framer Motion

## Getting Started

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- Postgressql(NeonDB) account (or local Postgresql installation)

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/disaster-tracker.git
cd disaster-tracker
```

2. Install dependencies
```bash
npm install --legacy-peer-deps
# or
yarn install
```

3. Set up environment variables
Create a `.env.local` file in the root directory with the following variables:
```
DATABASE_URL=your_database_url_postgressql
NEWSAPI_KEY=your_newsapi_key
GNEWS_API_KEY=your_gnews_key
NEWSDATA_API_KEY=your_newsdata_key
```

4. Initalize the Postgressql Database
```bash
npx prisma@latest init 
# and
npx prisma generate
```

5. Start the development server
```bash
npm run dev
# or
yarn dev
```

6. Open [http://localhost:3000](http://localhost:3000) in your browser to view the application

## Project Structure

```
disaster-tracker/
├── public/              # Static files
├── scripts/             # Database scripts
├── src
├── app
│   ├── api
│   │   ├── auth
│   │   │   ├── [...nextauth]
│   │   │   │   └── route.ts
│   │   │   └── register
│   │   │       └── route.ts
│   │   ├── cron
│   │   │   └── route.ts
│   │   ├── data-collection
│   │   │   └── route.ts
│   │   ├── disasters
│   │   │   └── route.ts
│   │   ├── events
│   │   │   ├── [id]
│   │   │   │   ├── route.ts
│   │   │   │   └── sources
│   │   │   │       └── route.ts
│   │   │   └── route.ts
│   │   └── news
│   │       └── route.ts
│   ├── dashboard
│   │   ├── alerts
│   │   │   └── page.tsx
│   │   ├── analytics
│   │   │   └── page.tsx
│   │   ├── data-collection
│   │   │   └── page.tsx
│   │   ├── events
│   │   │   ├── [id]
│   │   │   │   └── page.tsx
│   │   │   └── page.tsx
│   │   ├── feed
│   │   │   └── page.tsx
│   │   ├── help
│   │   │   └── page.tsx
│   │   ├── layout.tsx
│   │   ├── map
│   │   │   └── page.tsx
│   │   ├── monitoring
│   │   │   └── page.tsx
│   │   ├── notifications
│   │   │   └── page.tsx
│   │   ├── page.tsx
│   │   ├── responders
│   │   │   └── page.tsx
│   │   ├── risk-assessment
│   │   │   └── page.tsx
│   │   └── settings
│   │       └── page.tsx
│   ├── favicon.ico
│   ├── globals.css
│   ├── layout.tsx
│   ├── login
│   │   └── page.tsx
│   ├── page.tsx
│   └── signup
│       └── page.tsx
├── components
│   ├── ModeToggle.tsx
│   ├── analytics
│   │   ├── disaster-trends.tsx
│   │   └── severity-distribution.tsx
│   ├── dashboard
│   │   ├── sidebar.tsx
│   │   ├── stat-card.tsx
│   │   └── top-nav.tsx
│   ├── emergency-chatbot.tsx
│   ├── floating-chatbot.tsx
│   ├── header.tsx
│   ├── news-analysis.tsx
│   ├── news-card.tsx
│   ├── news-feed.tsx
│   ├── notifications
│   │   └── notification-list.tsx
│   ├── risk-assessment-dashboard.tsx
│   ├── theme-provider.tsx
│   └── ui
│       ├── accordion.tsx
│       ├── aceternity
│       │   └── shimmer-button.tsx
│       ├── alert.tsx
│       ├── avatar.tsx
│       ├── badge.tsx
│       ├── button.tsx
│       ├── calendar.tsx
│       ├── card.tsx
│       ├── checkbox.tsx
│       ├── dialog.tsx
│       ├── dropdown-menu.tsx
│       ├── form.tsx
│       ├── hover-card.tsx
│       ├── input.tsx
│       ├── label.tsx
│       ├── loading-spinner.tsx
│       ├── popover.tsx
│       ├── progress.tsx
│       ├── radio-group.tsx
│       ├── select.tsx
│       ├── separator.tsx
│       ├── sheet.tsx
│       ├── sonner.tsx
│       ├── switch.tsx
│       ├── table.tsx
│       ├── tabs.tsx
│       └── textarea.tsx
├── constant
│   ├── Monitoring.ts
│   ├── SampleDisaster.ts
│   ├── alert.ts
│   ├── dashboard.ts
│   ├── demoFeed.ts
│   ├── help.ts
│   └── responder.ts
├── context
│   └── auth-provider.tsx
├── hooks
│   └── use-events.ts
├── lib
│   ├── auth
│   │   ├── api-auth.ts
│   │   ├── auth-options.ts
│   │   └── auth-utils.ts
│   ├── data-collection
│   │   ├── collector.ts
│   │   ├── processors
│   │   │   ├── classifier.ts
│   │   │   ├── content-generator.ts
│   │   │   ├── location-extractor.ts
│   │   │   └── types.ts
│   │   ├── sources
│   │   │   ├── news.ts
│   │   │   ├── twitter.ts
│   │   │   └── weather.ts
│   │   └── types.ts
│   ├── database
│   │   └── client.ts
│   ├── services
│   │   └── event-service.ts
│   ├── utils
│   │   ├── mock-data-generator.ts
│   │   └── utils.ts
│   └── websocket
│       └── socket-server.ts
├── middleware.ts
├── scripts
│   └── seed-database.ts
├── server.ts
├── services
│   ├── assistant-service.ts
│   ├── news-analysis-service.ts
│   ├── news-service.ts
│   └── risk-assessment-service.ts
└── types
    ├── mapbox-gl.d.ts
    ├── news.ts
    └── typeDisaster.ts
├── .env                 # Environment variables
├── next.config.js       # Next.js configuration
└── package.json         # Project dependencies
```

## Key Components

- **Disaster Map**: Interactive map showing disaster locations with severity indicators
- **Disaster Feed**: Real-time feed of disaster information with filtering capabilities
- **News Feed**: Aggregated news articles from multiple sources with AI analysis
- **Statistics Dashboard**: Visual representation of disaster impacts and trends
- **Risk Assessment**: Region-specific disaster risk analysis and predictions
- **AI Assistant**: Interactive chatbot for disaster guidance and information

## AI Features

The application incorporates several AI-powered features:

1. **Disaster Severity Classification**: Analyzes disaster descriptions to classify severity levels
2. **News Content Analysis**: Analyzes news articles for relevance, reliability, and key points
3. **Disaster Impact Prediction**: Predicts potential impacts of active disasters
4. **Emergency Alert Generation**: Generates natural language alerts for disasters
5. **Evacuation Route Recommendation**: Suggests evacuation routes based on disaster type and location
6. **AI Assistant**: Provides guidance during disasters through a chat interface
7. **Risk Assessment**: Analyzes regional risk factors for different disaster types

## Deployment

The application can be deployed to Vercel with minimal configuration:

```bash
npm run build
# or
yarn build
```

Then follow the deployment instructions for your hosting platform of choice.

## Future Enhancements

- Integration with government disaster management APIs
- Mobile application development
- User account system for personalized alerts
- Integration with SMS and notification services
- Enhanced AI model training with historical disaster data
- Multilingual support for regional languages

## Contributors

- Amit Saini (Team Leader)
- Krrish Raj
- Neeraj Kumar
- Mohit Kumawat

## Acknowledgments

- All the open-source libraries and tools used in this project
- HackCrux for the hackathon opportunity

---

*This project was developed as part of the HackCrux hackathon 2025.*
