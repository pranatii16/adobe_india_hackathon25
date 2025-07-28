# Adobe-India-Hackathon25

Welcome to our submission for the **“Connecting the Dots” Challenge** organized by Adobe India Hackathon 2025.

---
## How can I edit this code?

There are several ways of editing your application:

**Use your preferred IDE**

If you want to work locally using your own IDE, you can clone this repo and push changes.

The only requirement is having Node.js & npm installed - [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating)

Follow these steps:

```sh
# Step 1: Clone the repository using the project's Git URL.
git clone <YOUR_GIT_URL>

# Step 2: Navigate to the project directory.
cd <YOUR_PROJECT_NAME>

# Step 3: Install the necessary dependencies.
npm i

# Step 4: Start the development server with auto-reloading and an instant preview.
npm run dev
```

**Edit a file directly in GitHub**

- Navigate to the desired file(s).
- Click the "Edit" button (pencil icon) at the top right of the file view.
- Make your changes and commit the changes.

**Use GitHub Codespaces**

- Navigate to the main page of your repository.
- Click on the "Code" button (green button) near the top right.
- Select the "Codespaces" tab.
- Click on "New codespace" to launch a new Codespace environment.
- Edit files directly within the Codespace and commit and push your changes once you're done.

## What technologies are used for this project?

This project is built with:

- Vite
- TypeScript
- React
- shadcn-ui
- Tailwind CSS

## 🚀 What did we build?

This project addresses both **Round 1A** and **Round 1B** of the Adobe India Hackathon 2025 challenge.

---

### ✅ Round 1A: PDF Outline Extractor

We created a **Python-based Dockerized solution** that:

- Accepts a directory of PDFs (`/app/input`)
- Extracts structured outlines: **Title**, **H1**, **H2**, **H3** with page numbers
- Outputs a `.json` file per PDF to `/app/output`
- Compatible with `linux/amd64`, runs **offline** with **no internet access**
- Processes 50-page PDFs in **≤10 seconds**
- Detects headings using heuristics beyond just font size (e.g., font style, position, and hierarchy)

#### 📦 Sample Output Format

```json
{
  "title": "Understanding AI",
  "outline": [
    { "level": "H1", "text": "Introduction", "page": 1 },
    { "level": "H2", "text": "What is AI?", "page": 2 },
    { "level": "H3", "text": "History of AI", "page": 3 }
  ]
}
```

### Docker Usage Instructions
 Build the Docker image
```sh

Copy code
docker build --platform linux/amd64 -t mysolution:uniqueid .
###Run the container
```
```sh
Copy code
docker run --rm \
  -v $(pwd)/input:/app/input \
  -v $(pwd)/output:/app/output \
  --network none mysolution:uniqueid
  ```
This will:

Process all PDFs inside /input

Generate corresponding .json output files in /output