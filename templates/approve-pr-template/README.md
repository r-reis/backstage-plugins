# Approve PR Template

This template is used to approve pending PR requests and create the actual GitHub Pull Request.

## Purpose

This is the second step in the two-step PR approval workflow:
1. **Request PR** (using `open-pr-template`) - Creates a catalog entity representing a PR request
2. **Approve PR** (using this template) - Approves the request and creates the actual GitHub PR

## How to Use

1. Go to the Backstage "Create" page
2. Select "Approve and Create Pull Request" template
3. Use the Entity Picker to select a pending PR request from the catalog
4. Fill in the PR details from the selected request entity:
   - Look at the entity's annotations for the details
   - Copy: owner, repo, branchName, prTitle, prDescription, requestedBy
5. Add your username as the approver
6. Submit to create the GitHub PR

## What It Does

1. **Fetches template files** - Gets the skeleton files
2. **Creates GitHub PR** - Uses the `publish:github:pull-request` action to create the actual PR
3. **Updates catalog entity** - Updates the PR request entity status from "pending" to "approved" and adds the PR URL

## Entity Annotations

The PR request entities use these annotations:
- `backstage.io/approval-status`: "pending" or "approved"
- `backstage.io/pr-branch`: Branch name for the PR
- `backstage.io/pr-title`: PR title
- `backstage.io/pr-description`: PR description
- `backstage.io/requested-by`: Username who requested the PR
- `backstage.io/approved-by`: Username who approved the PR (added after approval)
- `backstage.io/approved-at`: Timestamp of approval

## Future Enhancements

- Auto-populate PR details from the selected entity (requires custom action)
- Add rejection workflow
- Add notification system for requesters when PR is approved
- Add approval permissions/policies
