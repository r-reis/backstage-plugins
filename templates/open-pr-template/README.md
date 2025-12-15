# Request PR Template

## Description

This template creates a **PR request** in the Backstage catalog that requires approval before the actual GitHub pull request is created. This enables a two-step approval workflow for PR creation.

## Two-Step Approval Workflow

### Step 1: Request PR (This Template)
1. Navigate to "Create" in Backstage
2. Select "Request Pull Request" template
3. Fill in the form with your PR details
4. Click "Create" to submit your PR request
5. A catalog entity is created with status "pending"

### Step 2: Approve PR (Use `approve-pr-template`)
1. A reviewer navigates to "Create" in Backstage
2. Selects "Approve and Create Pull Request" template
3. Picks the pending PR request from the catalog
4. Fills in approval details
5. The actual GitHub PR is created and the entity is updated to "approved"

## Parameters

- **username**: Your GitHub/GitLab username
- **owner**: Repository owner (organization or username)
- **repo**: Repository name
- **prTitle**: Title for the pull request
- **prDescription**: Description for the pull request
- **branchName**: Name of the branch to create

## Features

- ✅ Creates a **PR request** entity in the Backstage catalog (not the actual GitHub PR yet)
- ✅ Sets approval status to "pending" for reviewer action
- ✅ Stores all PR details in entity annotations
- ✅ Enables approval workflow before PR creation
- ✅ Provides visibility into pending PR requests

## Catalog Registration

After running this template, a catalog entity is created with:
- **Type**: `pr-request`
- **Lifecycle**: `experimental` (pending approval)
- **Status**: `pending` (in `backstage.io/approval-status` annotation)
- **Entity name pattern**: `pr-request-{owner}-{repo}-{branchName}`

The entity stores all PR details in annotations:
- `backstage.io/approval-status`: Current approval status
- `backstage.io/pr-branch`: Branch name for the PR
- `backstage.io/pr-title`: PR title
- `backstage.io/pr-description`: PR description
- `backstage.io/requested-by`: Username who requested the PR
- `backstage.io/requested-at`: Request timestamp

## What Happens Next

1. **Review**: A reviewer finds the pending PR request in the catalog
2. **Approve**: Reviewer uses the `approve-pr-template` to approve and create the PR
3. **PR Created**: The actual GitHub PR is created
4. **Entity Updated**: The catalog entity is updated to "approved" status with PR link

## Requirements

- Catalog write permissions (for creating request entities)
- Reviewers need access to the `approve-pr-template`
