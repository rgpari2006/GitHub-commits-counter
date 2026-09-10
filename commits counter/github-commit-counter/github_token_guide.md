# GitHub Personal Access Token (PAT) Guide

This guide explains how to create a GitHub Personal Access Token to use with the **GitHub Commit Counter** application.

---

## Why Do You Need a GitHub Token?

GitHub provides a public REST API, but imposes rate limits:

| Access Type | Rate Limit |
| :--- | :--- |
| **Unauthenticated** (No Token) | **60 requests per hour** (per IP address) |
| **Authenticated** (With Token) | **5,000 requests per hour** (per user account) |

When querying users with many repositories or repositories with extensive commit histories, unauthenticated requests can quickly exhaust the 60 req/hour limit. Adding a Personal Access Token increases your quota significantly.

> [!NOTE]
> The GitHub Commit Counter runs entirely in your browser (client-side). Your token is stored locally in your browser's `localStorage` (if opted in) and is sent **only** to official GitHub API endpoints (`api.github.com`). It is never sent to any third-party server.

---

## Option 1: Fine-Grained Personal Access Token (Recommended)

Fine-grained tokens are GitHub's modern token type offering restricted permissions and repository-level scoping.

### Steps:
1. Log in to your GitHub account and navigate to **Settings** > **Developer Settings** > **Personal access tokens** > **[Fine-grained tokens](https://github.com/settings/tokens?type=beta)**.
2. Click **Generate new token**.
3. Fill in the token details:
   - **Token name**: e.g., `GitHub Commit Counter`
   - **Expiration**: Choose your desired duration (e.g., 30, 60, or 90 days).
   - **Resource owner**: Select your account or relevant organization.
   - **Repository access**:
     - Select **Public Repositories (read-only)** if analyzing public repos.
     - Select **All repositories** or **Only select repositories** if you want to count commits in private repositories.
4. **Permissions**:
   - Under **Repository permissions**, locate **Contents**: set to **Read-only** (this grants access to commits and repository metadata).
   - Under **Repository permissions**, locate **Metadata**: set to **Read-only** (mandatory, automatically selected).
5. Scroll to the bottom and click **Generate token**.
6. **Copy and save your token** immediately (GitHub will not show it again).

---

## Option 2: Classic Personal Access Token

Classic tokens are straightforward and work across all GitHub repositories.

### Steps:
1. Go to **Settings** > **Developer Settings** > **Personal access tokens** > **[Tokens (classic)](https://github.com/settings/tokens)**.
2. Click **Generate new token** -> **Generate new token (classic)**.
3. Provide a note: `GitHub Commit Counter`.
4. Choose an **Expiration** date.
5. Select scopes:
   - **For Public Repositories Only**: You do **not** need to check any scopes! A token without scopes still receives the full 5,000 req/hr rate limit on public data.
   - **For Private Repositories**: Check the `repo` scope (`Full control of private repositories`).
6. Click **Generate token** at the bottom of the page.
7. Copy your token (starts with `ghp_`).

---

## How to Use Your Token in GitHub Commit Counter

1. Open the **GitHub Commit Counter** application in your browser.
2. Click the **API Token / Settings** button in the header or toolbar.
3. Paste your token into the **GitHub Token** input field.
4. Click **Save Token** or **Validate & Save**.
5. The application will immediately verify your token against `https://api.github.com/user` and display your available API rate limit quota.

---

## Security Best Practices

- **Never share or commit your token**: Do not commit tokens to git repositories or paste them in public chat/forums.
- **Minimum Permissions**: Only grant `read-only` access or no extra scopes if analyzing public projects.
- **Revocation**: You can revoke or delete your token anytime under [GitHub Developer Settings](https://github.com/settings/tokens).
- **Clear Storage**: You can click **Remove Token** in the application settings anytime to clear it from browser storage.
