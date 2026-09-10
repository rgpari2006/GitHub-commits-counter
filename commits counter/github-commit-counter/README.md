# 📊 GitHub Commit Counter

A modern, responsive, and feature-rich web application to analyze, visualize, and count GitHub commits across repositories, users, and organizations.

![GitHub Commit Counter](https://img.shields.io/badge/Status-Active-brightgreen)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-v3.4-blue)
![Vanilla JS](https://img.shields.io/badge/JavaScript-ES6+-yellow)
![License](https://img.shields.io/badge/License-MIT-purple)

---

## ✨ Features

- **Multi-Mode Analytics**:
  - 👤 **User Commit Counter**: Count and analyze commits across all public repositories for any GitHub user.
  - 📦 **Repository Commit Counter**: In-depth commit insights for specific repositories (e.g., `facebook/react`, `torvalds/linux`).
  - 🏢 **Organization Counter**: Aggregated activity for entire GitHub organizations.
- **Visual Insights & Heatmaps**:
  - 📈 Commit activity over time (interactive line & bar charts powered by Chart.js).
  - 🍩 Commit distribution across repositories and contributors.
  - 🗓️ Day-of-week and hourly commit cadence breakdowns.
- **Advanced Filtering**:
  - Filter by date range (last 7 days, 30 days, 1 year, custom range).
  - Filter by author name or email.
  - Filter by branch name.
- **Export & Share**:
  - Export commit data to **CSV** and **JSON**.
  - Copy structured markdown report summary to clipboard.
- **Rate Limit & Token Support**:
  - Live GitHub API rate-limit monitor with countdown timer.
  - Optional Personal Access Token (PAT) input to upgrade from 60 req/hr to 5,000 req/hr.
  - Secure client-side storage (`localStorage` / session only).
- **Interactive UI**:
  - Sleek GitHub-inspired dark/light theme.
  - Live search in commit logs with pagination and direct links to GitHub commits.
  - Instant demo mode with preloaded sample data for testing without API limits.

---

## 📁 Project Structure

```text
github-commit-counter/
│
├── index.html               # The complete application (HTML, Tailwind CSS, JS)
├── github_token_guide.md    # Instructions for generating GitHub API tokens
└── README.md                # Project documentation (this file)
```

---

## 🚀 Getting Started

### Prerequisites
All you need is a modern web browser (Google Chrome, Firefox, Microsoft Edge, Safari). No backend build steps or `node_modules` required!

### Running the Application

1. **Option A: Direct Browser Open**
   - Double-click `index.html` or drag and drop it into your favorite browser.

2. **Option B: Local Development Server**
   If you have Python or Node installed:
   ```bash
   # Using Python 3
   cd github-commit-counter
   python -m http.server 8000

   # Or using npx serve
   npx serve .
   ```
   Open `http://localhost:8000` in your browser.

---

## 🔑 GitHub API Tokens & Rate Limits

GitHub limits unauthenticated API requests to **60 requests per hour**. For active users or large repositories, we recommend using a GitHub Personal Access Token (PAT) for up to **5,000 requests per hour**.

For detailed setup instructions on creating fine-grained or classic tokens, refer to **[github_token_guide.md](github_token_guide.md)**.

---

## 🛠️ Tech Stack

- **HTML5 & Vanilla JavaScript (ES6+)**: Zero framework overhead, high performance.
- **Tailwind CSS (CDN)**: Modern, utility-first styling with responsive design and glassmorphism.
- **Chart.js**: Smooth, interactive data visualization.
- **Lucide Icons**: Crisp vector icons.
- **GitHub REST API (v3)**: Official GitHub data integration.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
