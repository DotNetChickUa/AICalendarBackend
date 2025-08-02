# ðŸ“… AI Calendar WebAPI

**AI Calendar** is an ASP.NET Core WebAPI for managing personal calendar events. It supports natural language prompts, multi-user scheduling, and can integrate with LLMs via MCP. Backend is deployed on Render, frontend on GitHub Pages.

## ðŸš€ Features

- ðŸ‘¤ Simple user authentication
- ðŸ“† Event CRUD: create, update, delete events
- ðŸ‘¥ Manage participants for events
- ðŸ” Find the earliest available slot for all participants
- ðŸ’¬ Natural Language Prompt Support:
  - `"Add meeting with Anna on Friday from 10:00 to 11:00"`
  - `"Cancel all events with title 'Coffee break'"`

## ðŸ› ï¸ Tech Stack

- **Backend:** .NET 8 ASP.NET Core WebAPI
- **LLM Integration:** PromptProcessor + MCP server
- **Frontend:** React + Vite + TypeScript, FullCalendar
- **Swagger / OpenAPI** for testing
- **Docker** for deployment

## ðŸ”— Links

- ðŸ–¥ï¸ Backend API: [Render](https://aicalendarbackend.onrender.com)

- ðŸ“˜ Swagger UI: [Swagger](https://aicalendarbackend.onrender.com/swagger)

- ðŸŒ Frontend Live [GitHub Pages deployment](https://DotNetChickUa.github.io/AI-Calendar/)

## ðŸ“Œ Main Endpoints

### ðŸ“‘ Events

```http
GET    /api/v1/events
GET    /api/v1/events/{id}
POST   /api/v1/events
PUT    /api/v1/events/{id}
DELETE /api/v1/events/{id}
```

### ðŸ‘¥ Event Participants

```http
GET    /api/v1/events/{eventId}/participants
POST   /api/v1/events/{eventId}/participants
PUT    /api/v1/events/{eventId}/participants/{userId}
DELETE /api/v1/events/{eventId}/participants/{userId}
```

### ðŸ’¬ Prompt Executor

```http
POST /api/v1/events/prompt
```

### ðŸ§ª Free Slot Finder

```http
POST /api/v1/events/find-slot
```

### ðŸ§  Architecture (MCP + LLM Integration)

- Users interact via Console / Web / Native apps
- Prompts go to MCP Server
- MCP Server calls your WebAPI
- WebAPI performs scheduling logic and CRUD actions
- Optionally integrates with Google, Microsoft, Apple Calendars

### ðŸŒ Frontend UI

- React + TailwindCSS + Vite
- FullCalendar for event display
- PromptExecutor.tsx for entering natural language instructions

### ðŸ§ª Testing

âœ… Unit-tested free-slot finder algorithm (TimeSlotFinderService)

âœ… Prompt processor tested manually and via Swagger

### âš™ï¸ Getting Started

#### Backend

```
cd AICalendar
dotnet run
```

#### You can also run via Docker:

```
docker build -t aicalendar .
docker run -p 8080:8080 aicalendar
```

#### Frontend (ai-calendar-ui)

https://github.com/DotNetChickUa/AI-Calendar

### âœ… Completed Tasks

- Full WebAPI for events and participants
- Prompt endpoint for LLM integration
- Frontend UI for calendar and prompt
- Free-slot search algorithm
- Unit testing
- Docker support
- Deployed backend (Render) & frontend (GitHub Pages)

