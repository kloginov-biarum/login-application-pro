# Gym Application - Frontend

A modern, stylish frontend application for a gym management system with role-based access control.

## Features

- **Login Page**: Secure authentication with username and password
- **User Dashboard**: View remaining workouts, membership information, and gym details
- **Trainer Dashboard**: Manage training schedule and track conducted trainings
- **Administrator Dashboard**: Overview of all gym trainings with links to manage clients and trainers
- **Sales Dashboard**: Track sales plan and performance metrics

## Test Users

### User Role
- **Username**: `testuser1`
- **Password**: `user123`

### Trainer Role
- **Username**: `trainer1`
- **Password**: `trainer123`

### Administrator Role
- **Username**: `admin1`
- **Password**: `admin123`

### Salesperson Role
- **Username**: `sales1`
- **Password**: `sales123`

## Installation

1. Install dependencies:
```bash
npm install
```

2. Start the development server:
```bash
npm run dev
```

3. Open your browser and navigate to `http://localhost:5173`

## Build

To build for production:
```bash
npm run build
```

## Deploy to GitHub Pages

The application is configured to deploy automatically to GitHub Pages using GitHub Actions.

### Automatic Deployment

1. Push your code to the `main` or `master` branch
2. GitHub Actions will automatically build and deploy the application
3. Enable GitHub Pages in your repository settings:
   - Go to Settings → Pages
   - Under "Source", select "GitHub Actions"
4. Your app will be available at `https://{username}.github.io/{repository-name}/`

### Manual Deployment

If you want to deploy manually:

1. Build the project:
```bash
npm run build
```

2. The `dist` folder contains the production build

### Note

The application uses HashRouter for compatibility with GitHub Pages. URLs will look like:
- `https://{username}.github.io/{repo}/#/`
- `https://{username}.github.io/{repo}/#/user`
- `https://{username}.github.io/{repo}/#/trainer`
- etc.

## Technologies Used

- React 18
- TypeScript
- Vite
- Tailwind CSS
- React Router DOM

## Project Structure

```
src/
├── components/          # React components
│   ├── LoginPage.tsx
│   ├── UserDashboard.tsx
│   ├── TrainerDashboard.tsx
│   ├── AdminDashboard.tsx
│   ├── SalesDashboard.tsx
│   └── ProtectedRoute.tsx
├── data/               # Mock data
│   └── mockData.ts
├── types.ts           # TypeScript type definitions
├── auth.ts            # Authentication logic
├── App.tsx            # Main app component with routing
└── main.tsx           # Entry point
```


