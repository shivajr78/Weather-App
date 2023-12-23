To host a Vite + React app on GitHub Pages, you can follow these steps:

1. **Create a Vite + React App:**
   Create a new Vite app with the React template using the following commands in your terminal:

   ```bash
   npx create-vite my-react-app --template react
   cd my-react-app
   ```

2. **Configure GitHub Repository:**
   Make sure you have a GitHub repository where you want to host your app. If not, create a new repository on GitHub.

3. **Install GitHub Pages Package:**
   Install the `gh-pages` package, which simplifies the process of deploying to GitHub Pages:

   ```bash
   npm install -D gh-pages
   ```

4. **Update `package.json`:**
   Add the following scripts to your `package.json` file:

   ```json
   "scripts": {
     "deploy": "vite build && gh-pages -d dist",
     "predeploy": "rm -rf dist",
     // Other scripts...
   }
   ```

   The `deploy` script builds your Vite app and deploys it to the `gh-pages` branch.

5. **Configure `base` in `vite.config.js`:**
   Open your `vite.config.js` file and make sure the `base` is set correctly:

   ```js
   export default {
     base: '/my-react-app/', // Set this to your repository name
     // Other config...
   }
   ```

6. **Deploy to GitHub Pages:**
   Run the deploy script to build your app and deploy it to GitHub Pages:

   ```bash
   npm run deploy
   ```

   This command will create a `dist` folder and deploy its contents to the `gh-pages` branch.

7. **Configure GitHub Pages in Repository Settings:**
   Go to your GitHub repository settings, scroll down to the GitHub Pages section, and configure it to use the `gh-pages` branch.

   - Select the `gh-pages` branch as the source.
   - Set the root folder as `/ (root)`.

   After saving, your app should be accessible at `https://yourusername.github.io/repository-name/` (replace `yourusername` and `repository-name` with your GitHub username and repository name).

That's it! Your Vite + React app should now be hosted on GitHub Pages. Keep in mind that it may take a few minutes for the changes to take effect.
