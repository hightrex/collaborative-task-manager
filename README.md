# Collaborative Task Manager

A real-time collaborative task management application built with SvelteKit, NestJS, and Supabase.

## Prerequisites
- Docker and Docker Compose
- Node.js 18+
- Supabase account
- Pusher account

## Tech Stack
- **Frontend**: SvelteKit + Tailwind CSS
- **Backend**: NestJS
- **Database**: Supabase (PostgreSQL)
- **Real-time**: Pusher
- **Containerization**: Docker

## Current Progress
### Completed
- ✅ Project initialization and repository setup
- ✅ Docker configuration for development
  - Frontend Dockerfile with hot reload
  - Backend Dockerfile with hot reload
  - Docker Compose setup
- ✅ Frontend base setup
  - SvelteKit installation and configuration
  - Tailwind CSS integration
  - Basic layout structure
  - PostCSS configuration
  - Environment variables setup

### In Progress
- 🔄 Frontend Features
  - Basic UI components
  - Task list view
  - Supabase client integration

### Next Steps
- Backend API setup with NestJS
- Database schema design in Supabase
- Authentication implementation
- Real-time updates with Pusher

## Development Setup
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd collaborative-task-manager
   ```

2. Copy environment example and configure:
   ```bash
   cp .env.example .env
   ```

3. Start the development environment:
   ```bash
   docker-compose up
   ```

4. Access the applications:
   - Frontend: http://localhost:3000
   - Backend: http://localhost:4000

## Development Notes
- Hot reload is enabled for both frontend and backend
- Frontend uses Vite's HMR through port 24678
- Backend supports debugging through port 9229

## Project Structure
```
project-root/
├── frontend/                      # SvelteKit frontend
│   ├── src/
│   │   ├── app.css               # Global styles and Tailwind imports
│   │   ├── lib/
│   │   │   └── supabase.ts       # Supabase client configuration
│   │   └── routes/
│   │       ├── +layout.svelte    # Main layout component
│   │       └── +page.svelte      # Home page component
│   ├── static/
│   ├── tailwind.config.js        # Tailwind configuration
│   ├── postcss.config.js         # PostCSS configuration
│   ├── package.json
│   └── svelte.config.js
├── backend/                       # NestJS backend
│   ├── src/
│   ├── package.json
│   └── nest-cli.json
├── docker/
│   └── .env.example
├── docker-compose.yml            # Docker services configuration
└── README.md
```

## Features (Planned)
- User authentication (sign-up, login)
- Create, read, update, and delete (CRUD) tasks
- Real-time updates for task changes
- Collaborative features (shared tasks)
- Notifications for updates

## Docker Services
The project is containerized using Docker. Current services include:
- Frontend (SvelteKit) - Development environment with hot reload
- Backend (NestJS) - Development environment with hot reload
- Database (Supabase) - External service

## Contributing
1. Create a feature branch
2. Make your changes
3. Submit a pull request

## License
[MIT License](LICENSE)