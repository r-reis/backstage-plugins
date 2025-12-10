# Pull Requests Report for {{ owner }}/{{ repo }}

**State Filter:** {{ state }}  
**Generated:** {{ now | date('YYYY-MM-DD HH:mm:ss') }}

## Repository Information

- **Owner:** {{ owner }}
- **Repository:** {{ repo }}
- **State Filter:** {{ state }}

## View Pull Requests

### On GitHub Web Interface
[View {{ state }} PRs on GitHub]({{ githubUrl }}?q=is:pr+is:{{ state }})

### Via GitHub API

You can fetch the pull requests using the GitHub API:

**Endpoint:**
```
{{ apiUrl }}
```

**Example using curl:**
```bash
curl -H "Accept: application/vnd.github.v3+json" \
     -H "Authorization: token YOUR_GITHUB_TOKEN" \
     "{{ apiUrl }}"
```

**Example using JavaScript/Node.js:**
```javascript
const response = await fetch('{{ apiUrl }}', {
  headers: {
    'Accept': 'application/vnd.github.v3+json',
    'Authorization': 'token YOUR_GITHUB_TOKEN'
  }
});
const prs = await response.json();

prs.forEach(pr => {
  console.log(`#${pr.number}: ${pr.title}`);
  console.log(`  Author: ${pr.user.login}`);
  console.log(`  Created: ${pr.created_at}`);
  console.log(`  URL: ${pr.html_url}`);
  console.log(`  Branch: ${pr.head.ref} → ${pr.base.ref}`);
  console.log('');
});
```

## PR Information Structure

Each PR object from the GitHub API contains:

- `number` - PR number
- `title` - PR title
- `body` - PR description
- `state` - PR state (open, closed)
- `user` - Author information
  - `login` - Username
  - `html_url` - Profile URL
- `created_at` - Creation timestamp
- `updated_at` - Last update timestamp
- `head` - Source branch
  - `ref` - Branch name
- `base` - Target branch
  - `ref` - Branch name
- `html_url` - PR URL
- `labels` - Array of labels
- `requested_reviewers` - Array of requested reviewers

## Notes

- The API returns up to 100 PRs per page
- Use pagination (`page` parameter) to get more results
- Authentication is required for private repositories
- The GitHub token needs `repo` scope for private repos, or no scope for public repos

