# List Pull Requests Template

## Description

This template creates an interactive HTML report that fetches and displays all open (or closed/all) pull requests for a GitHub repository. The HTML file includes:

- **Interactive Interface**: Opens in your browser and automatically fetches PRs
- **Rich Information Display**: Shows PR number, title, author, dates, branches, labels, and descriptions
- **GitHub Token Support**: Optional token input for private repositories
- **Auto-refresh**: Button to refresh the PR list
- **Pagination Support**: Can fetch all pages of PRs

## Usage

1. Navigate to "Create" in Backstage
2. Select "List Open Pull Requests" template
3. Fill in the repository owner and name
4. Select PR state (open, closed, or all) - default is `open`
5. Click "Create" to generate the reports
6. Open the generated `pr-list.html` file in your browser
7. (Optional) Enter your GitHub token if accessing private repositories
8. Click "Refresh PR List" to fetch and display PRs

## Parameters

- **owner**: GitHub organization or username (e.g., `r-reis`)
- **repo**: Repository name (e.g., `backstage-plugins`)
- **state**: Filter by PR state - `open`, `closed`, or `all` (default: `open`)

## Output Files

The template generates two files:

1. **pr-list.html** - Interactive HTML report that:
   - Automatically fetches PRs when opened
   - Displays PRs in a beautiful card layout
   - Shows PR number, title, author, dates, branches, labels, and descriptions
   - Supports GitHub token for private repos
   - Can fetch all pages of PRs

2. **pr-list.md** - Markdown documentation with:
   - API endpoint information
   - Example code snippets for fetching PRs
   - PR data structure documentation

## Features

- **No Backend Required**: The HTML file runs entirely in the browser
- **Public Repo Support**: Works without authentication for public repositories
- **Private Repo Support**: Enter GitHub token for private repositories
- **Real-time Data**: Fetches latest PR data from GitHub API
- **Responsive Design**: Works on desktop and mobile devices
- **Error Handling**: Shows helpful error messages for authentication or API issues

## Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- For private repositories: GitHub Personal Access Token with `repo` scope
- For public repositories: No authentication needed

## Example

After running the template and opening `pr-list.html`, you'll see:

- Header with repository information
- Control panel to enter GitHub token and refresh
- Statistics showing total, open, and closed PR counts
- List of PR cards, each showing:
  - PR number and title (linked to GitHub)
  - Author name (linked to profile)
  - Creation and update dates
  - Source and target branches
  - PR state badge (open/closed)
  - Labels (if any)
  - Description preview

## GitHub Token

To access private repositories, you'll need a GitHub Personal Access Token:

1. Go to https://github.com/settings/tokens
2. Click "Generate new token (classic)"
3. Select `repo` scope
4. Copy the token
5. Paste it into the token field in the HTML page
