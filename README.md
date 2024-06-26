# Serverless with TypeScript - Web Hooks with github and Discord - TS-Node-dev (favorite) - Netlify deploy

## After clone, you must do

1. setup env file like .env.template

   ```text
   MY_IMPORTANT_VARIABLE="Greetings from here"
   DISCORD_WEBHOOK_URL=https://discord.com/api/webhooks/1250...some..like..this

   ```

2. Run this:

   ```sh
   pnpm i
   pnpm dev
   ```

## This project was created with this steps

1. Install TypeScript and more dependencies

   ```sh
   pnpm i -D typescript @types/node ts-node-dev rimraf
   ```

2. init TypeScript config file

   ```sh
   pnpm exec tsc --init --outDir dist/ --rootDir src
   ```

3. scripts for dev, build and start ([more info about TS-NODE here](https://www.npmjs.com/package/ts-node-dev))

   ```sh
   "dev": "tsnd --respawn --clear src/app.ts",
   "build": "rimraf ./dist && tsc",
   "start": "npm run build && node dist/app.js",
   "netlify:dev": "netlify dev"
   ```

NOTE 1: You must install netlify cli and login. More info [here](https://docs.netlify.com/functions/get-started/?fn-language=ts)

NOTE 2: Set environment variables to netlify site config.

NOTE 3: To deploy run `netlify deploy --prod`
