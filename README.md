# Gemini React Tutorial

A step-by-step guide to running Gemini-generated React code locally.

## Prerequisites

- Node.js and npm installed on your system
- Basic knowledge of React and command line operations

## Step 1: Create a New React App with Vite

1. Open your terminal and run:
   ```bash
   npm create vite@latest my-app
   ```
2. Select the following options:
   - Framework: React
   - Variant: JavaScript
3. Navigate to the new project folder and install dependencies:
   ```bash
   cd my-app
   npm install
   ```

## Step 2: Set Up Tailwind CSS and Shadcn UI

1. Install Tailwind CSS and its dependencies:
   ```bash
   npm install -D tailwindcss postcss autoprefixer
   npx tailwindcss init -p
   ```

2. Update `vite.config.js`:
   ```javascript
   import { defineConfig } from 'vite'
   import react from '@vitejs/plugin-react'
   import path from 'path'

   export default defineConfig({
     plugins: [react()],
     resolve: {
       alias: {
         '@': path.resolve(__dirname, './src'),
       },
     },
   })
   ```

3. Create `jsconfig.json`:
   ```json
   {
     "compilerOptions": {
       "baseUrl": ".",
       "paths": {
         "@/*": ["src/*"]
       }
     },
     "include": ["src/**/*"]
   }
   ```

4. Initialize Shadcn UI:
   ```bash
   npx shadcn-ui@latest init
   ```
   Follow the prompts, selecting options appropriate for your project.

## Step 3: Install Additional Libraries and Components

1. Install required Shadcn UI components:
   ```bash
   npx shadcn-ui@latest add card button input
   ```

2. Install other necessary libraries (e.g., Lucide React):
   ```bash
   npm install lucide-react
   ```

## Step 4: Add Your React Component

1. Create a new file for your component (e.g., `src/components/LLMModel.jsx`).
2. Paste your Gemini-generated React code into this file.
3. Update `src/App.jsx` to include your new component:
   ```jsx
   import './App.css'
   import LLMModel from './components/LLMModel'

   function App() {
     return (
       <>
         <LLMModel/>
       </>
     )
   }

   export default App
   ```

## Step 5: Run the App

1. Start the development server:
   ```bash
   npm run dev
   ```
2. Open your browser and navigate to the URL provided in the terminal (usually `http://localhost:5173`).

Your Gemini-generated React component should now be running locally!