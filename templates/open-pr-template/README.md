# Open PR Template

## Description

This template creates a pull request with a hello world file in any target repository and automatically registers it in the Backstage catalog, allowing team members to follow the PR's progress directly in Backstage.

## Usage

1. Navigate to "Create" in Backstage
2. Select "Open Pull Request" template
3. Fill in the form with your details
4. Click "Create" to open the PR
5. The PR will be automatically registered in the catalog

## Parameters

- **username**: Your GitHub/GitLab username
- **owner**: Repository owner (organization or username)
- **repo**: Repository name
- **prTitle**: Title for the pull request
- **prDescription**: Description for the pull request
- **branchName**: Name of the branch to create

## Features

- ✅ Creates a pull request with a hello world file
- ✅ Automatically registers the PR in the Backstage catalog
- ✅ Allows team members to track PR progress in Backstage
- ✅ Links to view the PR on GitHub and in the catalog

## Catalog Registration

After the PR is created, it will be automatically registered in the Backstage catalog as a Component entity with type `pull-request`. This allows you to:

- View the PR entity in the Backstage catalog
- Track PR status and metadata
- Access the PR directly from Backstage with a link to GitHub
- Share PR information with team members through Backstage

The entity name follows the pattern: `pr-{owner}-{repo}-{branchName}`

## Requirements

- GitHub/GitLab token configured in Backstage
- Write access to target repository
- Catalog write permissions (for automatic registration)
