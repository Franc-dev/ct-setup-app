```markdown
# Complete Setup Guide: React + Vite + shadcn/ui + Tailwind CSS + TypeScript

This guide provides a detailed, step-by-step process to set up a new project using React, Vite, shadcn/ui, Tailwind CSS, and TypeScript. Follow these instructions carefully to create a powerful, modern web development environment.

## Prerequisites

Ensure you have the following installed on your system:
- Node.js (version 14.18+ or 16+)
- npm (comes with Node.js)

You can check your Node.js and npm versions by running:
```bash
node --version
npm --version
```

## Step 1: Create a new Vite project

1. Open your terminal and navigate to the directory where you want to create your project.
2. Run the following command to create a new Vite project with React and TypeScript:


```shellscript
npm create vite@latest my-react-app -- --template react-ts
```

3. Navigate into your new project directory:


```shellscript
cd my-react-app
```

## Step 2: Install dependencies

Install the project dependencies:

```shellscript
npm install
```

## Step 3: Add Tailwind CSS

1. Install Tailwind CSS and its peer dependencies:


```shellscript
npm install -D tailwindcss postcss autoprefixer
```

2. Generate Tailwind CSS configuration files:


```shellscript
npx tailwindcss init -p
```

This creates `tailwind.config.js` and `postcss.config.js` files.

## Step 4: Configure Tailwind CSS

1. Open `tailwind.config.js` and replace its content with:


```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

2. Create or update `src/index.css` with Tailwind directives:


```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Step 5: Install and configure shadcn/ui

1. Run the shadcn/ui init command:


```shellscript
npx shadcn@latest init
```

2. Follow the prompts:

1. Would you like to use TypeScript (recommended)? `Yes`
2. Which style would you like to use? `Default`
3. Which color would you like to use as base color? `Slate`
4. Where is your global CSS file? `src/index.css`
5. Do you want to use CSS variables for colors? `Yes`
6. Where is your tailwind.config.js located? `tailwind.config.js`
7. Configure the import alias for components: `@/components`
8. Configure the import alias for utils: `@/lib/utils`
9. Are you using React Server Components? `No`





## Step 6: Update tsconfig.json

1. Open `tsconfig.json` and add the following to the `compilerOptions` object:


```json
{
  "compilerOptions": {
    // ... existing options
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

## Step 7: Update vite.config.ts

1. Open `vite.config.ts` and update it to include path resolution:


```typescript
import path from "path"
import react from "@vitejs/plugin-react"
import { defineConfig } from "vite"

export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
})
```

## Step 8: Create a sample component using shadcn/ui

1. Install the Button component:


```shellscript
npx shadcn@latest add button
```

2. Create a new file `src/components/HelloWorld.tsx`:


```typescriptreact
import { Button } from "@/components/ui/button"

export function HelloWorld() {
  return (
    <div className="p-4">
      <h1 className="text-2xl font-bold mb-4">Hello, World!</h1>
      <Button>Click me</Button>
    </div>
  )
}
```

3. Update `src/App.tsx` to use the new component:


```typescriptreact
import { HelloWorld } from './components/HelloWorld'

function App() {
  return (
    <div className="container mx-auto mt-8">
      <HelloWorld />
    </div>
  )
}

export default App
```

## Step 9: Run the development server

Start your development server:

```shellscript
npm run dev
```

Open your browser and navigate to `http://localhost:5173` (or the port Vite is running on).

## Conclusion

You now have a fully set up project using React, Vite, shadcn/ui, Tailwind CSS, and TypeScript. This setup provides a powerful foundation for building modern web applications with a beautiful UI and type safety.

## Next Steps

1. Explore the shadcn/ui documentation to add more components to your project.
2. Dive deeper into Tailwind CSS to customize your styles.
3. Start building your React components and pages.
4. Consider setting up ESLint and Prettier for code linting and formatting.


## Additional Resources

- [React Documentation](https://reactjs.org/)
- [Vite Documentation](https://vitejs.dev/)
- [shadcn/ui Documentation](https://ui.shadcn.com/)
- [Tailwind CSS Documentation](https://tailwindcss.com/)
- [TypeScript Documentation](https://www.typescriptlang.org/)


Happy coding!

```plaintext

This `SETUP_GUIDE.md` file provides a comprehensive, step-by-step guide to setting up a project with React, Vite, shadcn/ui, Tailwind CSS, and TypeScript. It includes all the necessary commands, code snippets, and explanations without creating separate components or additional files.
```