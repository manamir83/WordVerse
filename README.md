# WordVerse — complete starter project

A working Next.js vocabulary-universe prototype with an interactive semantic map, add/remove/select words, local browser saving, and an optional Groq AI vocabulary tutor. This project does not claim that manually suggested connections are verified linguistic facts.

## Run it on Windows (VS Code)

1. Extract this ZIP file.
2. In VS Code, choose **File → Open Folder** and open the extracted `WordVerse-Complete` folder (the folder containing `package.json`).
3. Open **Terminal → New Terminal**. Check the prompt is inside `WordVerse-Complete`.
4. Run:

   ```powershell
   npm install
   npm run dev
   ```

5. Open http://localhost:3000

If PowerShell says `Missing script: dev`, the terminal is not in this project's root folder. Run `dir` and make sure `package.json` is listed.

## Add the AI API key (optional)

1. Copy `.env.example` and name the copy `.env.local` in the same folder as `package.json`.
2. Open `.env.local` and replace `PASTE_YOUR_GROQ_API_KEY_HERE` with your own key from https://console.groq.com/keys:

   ```env
   GROQ_API_KEY=gsk_your_real_key_here
   GROQ_MODEL=llama-3.3-70b-versatile
   ```

3. Save. Stop the dev server with **Ctrl+C**, then run `npm run dev` again.
4. Ask a question in the **Explore with AI** panel.

**Security:** `.env.local` is ignored by Git. Never put an API key in frontend code, screenshots, or a public repository. Do not submit a real key inside the ZIP. API availability and model access depend on your Groq account.

## Files

- `src/app/page.tsx` — app UI, word nodes, add/remove/select actions, AI chat request, localStorage.
- `src/app/globals.css` — responsive styling.
- `src/app/layout.tsx` — page metadata and root layout.
- `src/app/api/chat/route.ts` — server-side AI endpoint; key is read from environment variables.
- `.env.example` — safe template for environment settings.

## Current prototype limits

- The graph and starter relationships are sample content; new words are linked to the currently selected word as a prompt to explore, not as a verified synonym relationship.
- Word definitions for newly added words are not automatically fetched. Use the AI panel to ask for definitions, nuance, examples, and memory aids.
- Saved words and graph are stored in the current browser only, not synced across devices or users.
- AI calls require a configured Groq API key and internet access.
