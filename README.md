# Nxt Watch - YouTube Clone

A feature-rich video streaming platform built with React.js that allows users to browse, search, and save videos across different categories. The application includes authentication, theme switching, and responsive design.

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Routes](#routes)
- [API Endpoints](#api-endpoints)
- [Authentication](#authentication)
- [State Management](#state-management)
- [Styling](#styling)
- [Testing](#testing)
- [Deployment](#deployment)

## ✨ Features

### Core Features
- **User Authentication**: Secure login/logout functionality with JWT tokens
- **Theme Support**: Toggle between light and dark themes
- **Video Categories**: Browse videos by Home, Trending, Gaming
- **Search Functionality**: Search for videos with dynamic results
- **Video Player**: Full-featured video player with controls
- **Save Videos**: Save videos for later viewing
- **Responsive Design**: Optimized for mobile, tablet, and desktop

### Additional Features
- Like/Dislike functionality for videos
- Channel information and subscriber counts
- Video descriptions and metadata
- Loading states and error handling
- Protected routes for authenticated users

## 🛠️ Tech Stack

- **Frontend Framework**: React.js (v17+)
- **Routing**: React Router DOM (v5.2.0)
- **Styling**: Styled Components
- **Video Player**: React Player
- **HTTP Client**: Axios/Fetch API
- **State Management**: React Context API
- **Authentication**: JWT (JSON Web Tokens)
- **Date Formatting**: date-fns
- **Icons**: React Icons
- **Popups**: React Popup

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn package manager

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/nxt-watch.git
cd nxt-watch
```

2. Install dependencies
```bash
npm install
```

3. Start the development server
```bash
npm start
```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

### Login Credentials
```
Username: rahul
Password: rahul@2021
```

## 📁 Project Structure

```
nxt-watch/
├── public/
│   ├── index.html
│   └── ...
├── src/
│   ├── components/
│   │   ├── Login/
│   │   ├── Home/
│   │   ├── Trending/
│   │   ├── Gaming/
│   │   ├── VideoItemDetails/
│   │   ├── SavedVideos/
│   │   ├── NotFound/
│   │   ├── Header/
│   │   ├── Sidebar/
│   │   ├── VideoCard/
│   │   └── ...
│   ├── context/
│   │   └── ThemeContext.js
│   ├── App.js
│   ├── App.css
│   └── index.js
├── package.json
└── README.md
```

## 🗺️ Routes

| Route | Path | Description |
|-------|------|-------------|
| Login | `/login` | User authentication page |
| Home | `/` | Homepage with video feed and search |
| Trending | `/trending` | Trending videos section |
| Gaming | `/gaming` | Gaming videos section |
| Video Details | `/videos/:id` | Individual video player page |
| Saved Videos | `/saved-videos` | User's saved videos |
| Not Found | `/not-found` | 404 error page |

## 🔌 API Endpoints

### Authentication
```
POST https://apis.ccbp.in/login
Body: { username: string, password: string }
```

### Videos
```
GET https://apis.ccbp.in/videos/all?search={searchQuery}
GET https://apis.ccbp.in/videos/trending
GET https://apis.ccbp.in/videos/gaming
GET https://apis.ccbp.in/videos/:id
```

All video endpoints require JWT token in cookies.

## 🔐 Authentication

The app uses JWT-based authentication:

1. User submits credentials to login endpoint
2. Server returns JWT token on successful authentication
3. Token is stored in cookies
4. Token is sent with all subsequent API requests
5. Protected routes check for valid token

## 💾 State Management

### Context API Usage

```javascript
// ThemeContext for theme management
const ThemeContext = React.createContext({
  isDarkTheme: false,
  toggleTheme: () => {},
})

// SavedVideosContext for managing saved videos
const SavedVideosContext = React.createContext({
  savedVideos: [],
  addVideo: () => {},
  deleteVideo: () => {},
})
```

## 🎨 Styling

The project uses Styled Components for styling:

```javascript
import styled from 'styled-components'

export const LoginContainer = styled.div`
  background-color: ${props => props.isDark ? '#181818' : '#f9f9f9'};
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
`
```

### Theme Colors

| Light Theme | Dark Theme |
|-------------|------------|
| Background: #f9f9f9 | Background: #181818 |
| Text: #1e293b | Text: #f9f9f9 |
| Primary: #3b82f6 | Primary: #3b82f6 |

## 🧪 Testing

### Unit Tests
```bash
npm test
```

### Test Requirements
- All routes must have correct `data-testid` attributes
- Loader components must be wrapped with `data-testid="loader"`
- Images must have appropriate alt attributes
- Theme button must have `data-testid="theme"`

## 📱 Responsive Design

The app is responsive across different screen sizes:

- **Mobile**: < 576px
- **Tablet**: 576px - 768px
- **Desktop**: > 768px

## 🚀 Deployment

### Build for Production
```bash
npm run build
```

### Deploy to Hosting Service
The build folder can be deployed to services like:
- Netlify
- Vercel
- GitHub Pages
- AWS S3

