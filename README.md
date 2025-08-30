# Python Portal Frontend

## Modern React Application with TypeScript

This is the frontend application for the Python Learning Portal, built with React, TypeScript, Vite, and Tailwind CSS. It provides an interactive learning environment with a code editor, exercise management, and progress tracking.

## 🏗️ Architecture

```
@python-portal/frontend/
├── src/
│   ├── components/           # Reusable UI components
│   │   ├── ui/               # Base UI components
│   │   ├── editor/           # Code editor components
│   │   ├── exercises/        # Exercise-related components
│   │   └── layout/           # Layout components
│   ├── pages/               # Page components
│   │   ├── Dashboard.tsx
│   │   ├── Learn.tsx
│   │   ├── Practice.tsx
│   │   └── Dictionary.tsx
│   ├── hooks/               # Custom React hooks
│   ├── services/            # API services
│   ├── store/               # State management (Zustand)
│   ├── utils/               # Utility functions
│   ├── types/               # TypeScript type definitions
│   └── App.tsx              # Main application component
├── public/              # Static assets
└── dist/                # Built application
```

## ✨ Features

### 💻 Interactive Code Editor
- Monaco Editor integration
- Python syntax highlighting
- Auto-completion and IntelliSense
- Real-time error detection
- Code formatting and linting

### 📚 Learning Management
- Progressive exercise system
- 17 comprehensive Python exercises
- Difficulty-based categorization
- Progress tracking and analytics
- Achievement system

### 🎨 Modern UI/UX
- Responsive design (mobile, tablet, desktop)
- Dark/light theme support
- Smooth animations with Framer Motion
- Accessible components
- Tailwind CSS styling

### 🔐 User Experience
- Guest mode for immediate access
- User authentication and profiles
- Progress persistence
- Exercise bookmarking
- Search and filtering

## 🚀 Quick Start

```bash
# Install dependencies
npm install

# Development mode
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## 🔧 Development

### Environment Variables

```env
# API Configuration
VITE_API_URL=http://localhost:3000/api
VITE_EXECUTOR_URL=http://localhost:8000

# Feature Flags
VITE_ENABLE_AUTH=true
VITE_ENABLE_ANALYTICS=false
VITE_ENABLE_PWA=true

# UI Configuration
VITE_APP_NAME="Python Learning Portal"
VITE_APP_VERSION=1.0.0
```

### Code Style

```bash
# Lint code
npm run lint

# Fix linting issues
npm run lint:fix

# Type checking
npm run type-check
```

## 🎨 Styling

### Tailwind CSS
- Utility-first CSS framework
- Custom design system
- Responsive breakpoints
- Dark mode support

### Component Library
```tsx
// Example component usage
import { Button } from '@/components/ui/Button';
import { Card } from '@/components/ui/Card';
import { CodeEditor } from '@/components/editor/CodeEditor';

function ExercisePage() {
  return (
    <Card className="p-6">
      <CodeEditor 
        value={code}
        onChange={setCode}
        language="python"
      />
      <Button onClick={runCode} variant="primary">
        Run Code
      </Button>
    </Card>
  );
}
```

## 📱 Responsive Design

### Breakpoints
- **Mobile**: < 640px
- **Tablet**: 640px - 1024px
- **Desktop**: > 1024px

### Mobile Features
- Touch-optimized code editor
- Collapsible navigation
- Swipe gestures
- Optimized layouts

## 📡 API Integration

### Services
```typescript
// Exercise service
import { exerciseService } from '@/services/exerciseService';

const exercises = await exerciseService.getAll();
const result = await exerciseService.runCode(exerciseId, code);

// User service
import { userService } from '@/services/userService';

const user = await userService.login(email, password);
const progress = await userService.getProgress();
```

### State Management
```typescript
// Zustand store
import { useExerciseStore } from '@/store/exerciseStore';
import { useUserStore } from '@/store/userStore';

function Component() {
  const { exercises, currentExercise, setCurrentExercise } = useExerciseStore();
  const { user, isAuthenticated } = useUserStore();
  
  // Component logic
}
```

## 🔍 Testing

### Unit Tests
```bash
# Run tests
npm test

# Watch mode
npm run test:watch

# Coverage
npm run test:coverage
```

### E2E Testing
```bash
# Playwright tests
npm run test:e2e

# Visual regression tests
npm run test:visual
```

## 🐳 Docker Deployment

```dockerfile
# Multi-stage build
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

```bash
# Build and run
npm run docker:build
npm run docker:run
```

## 📊 Performance

### Optimizations
- Code splitting by route
- Lazy loading of heavy components
- Image optimization
- Bundle analysis
- Caching strategies

### Bundle Analysis
```bash
# Analyze bundle size
npx vite-bundle-analyzer

# Performance audit
npm run audit
```

## 🌍 Progressive Web App

### PWA Features
- Offline functionality
- Install prompts
- Background sync
- Push notifications
- App-like experience

### Service Worker
- Caches static assets
- Offline fallback pages
- Background updates
- Network-first strategies

## ⚖️ Accessibility

### WCAG Compliance
- Keyboard navigation
- Screen reader support
- High contrast mode
- Focus management
- ARIA attributes

### Testing
```bash
# Accessibility audit
npm run test:a11y

# Lighthouse audit
npm run audit:lighthouse
```

## 📚 Component Documentation

### Storybook
```bash
# Run Storybook
npm run storybook

# Build Storybook
npm run build-storybook
```

## 🛠️ Development Tools

### VS Code Extensions
- ES7+ React/Redux/React-Native snippets
- Tailwind CSS IntelliSense
- TypeScript Hero
- Auto Rename Tag
- Prettier - Code formatter

### Browser DevTools
- React Developer Tools
- Redux DevTools
- Lighthouse
- Performance Monitor

## 📋 Build Configuration

### Vite Config
```typescript
// vite.config.ts
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
import { VitePWA } from 'vite-plugin-pwa';

export default defineConfig({
  plugins: [
    react(),
    VitePWA({
      registerType: 'autoUpdate',
      workbox: {
        globPatterns: ['**/*.{js,css,html,ico,png,svg}']
      }
    })
  ],
  resolve: {
    alias: {
      '@': '/src'
    }
  }
});
```

## 🤝 Contributing

1. Fork the repository
2. Create feature branch
3. Follow component patterns
4. Write comprehensive tests
5. Update documentation
6. Submit pull request

## 📝 License

MIT - see [LICENSE](LICENSE) file

---

**Modern & Responsive**: Built with the latest React ecosystem and optimized for all devices and screen sizes.