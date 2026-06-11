# Cloud Online Reader

Cloud Online Reader is a full-stack web application for browsing, reading, and managing a cloud-hosted digital library. Readers can open PDF and EPUB books directly in the browser, automatically save their progress, maintain a personal reading list, review books, and participate in a gamified reader community.

Administrators can upload and maintain books, manage users, control catalog visibility, award badges, and inspect reading activity from a dedicated admin workspace.

## Features

### Reader Experience

- Secure registration and login
- Searchable PDF and EPUB library
- Featured and continue-reading sections
- Automatic reading-progress saving
- PDF page navigation, zoom, themes, and fullscreen mode
- EPUB table of contents, themes, font sizing, and line-height controls
- Personal **My List** reading shelf
- Book details, ratings, reviews, and helpful votes
- Reader profiles, avatars, goals, levels, XP, titles, and badges
- Community activity feed, following, and leaderboard

### Administration

- Upload PDF and EPUB books with optional cover images
- Feature, hide, edit, replace, or delete books
- View catalog, storage, completion, and reader statistics
- Inspect saved progress for individual books
- Manage user roles
- Manage user XP, levels, titles, and badges
- Moderate book reviews

## Technology Stack

| Layer | Technologies |
| --- | --- |
| Frontend | React 19, JavaScript, CSS, React PDF, PDF.js, EPUB.js |
| Backend | Node.js, Express 5, Multer, JWT, bcrypt |
| Database | Azure SQL Database using `mssql` |
| File storage | Azure Blob Storage |
| Deployment | Vercel frontend and Azure-hosted backend services |
| Workflow | GitHub, Azure DevOps, Git |

## Architecture

```text
User
  |
  v
React frontend
  |
  | HTTPS / REST API
  v
Node.js + Express API
  |                     |
  v                     v
Azure SQL Database      Azure Blob Storage
users, books, progress  PDF, EPUB, covers, avatars
reviews, profiles, XP
```

The frontend sends authenticated requests to the Express API. The API validates JWT access and role permissions, stores structured application data in Azure SQL, and streams protected files from Azure Blob Storage.
