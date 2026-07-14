# Governance

The Engineering Interview Handbook is a community-driven open-source project. This document outlines how decisions are made, how contributions are reviewed, and how the community is managed.

## Roles and Responsibilities

1. **Maintainers:** Individuals with write access to the repository. They are responsible for reviewing PRs, managing issues, and enforcing the Style Guide and Code of Conduct.
2. **Contributors:** Anyone who submits a pull request, opens an issue, or participates in discussions.
3. **Readers:** The engineers utilizing the handbook to prepare for their interviews.

## Decision Making Process

1. **Content Additions:** Significant new content (e.g., adding a new Learning Path or Company Guide) requires a GitHub Issue proposing the addition. This allows maintainers to ensure the topic aligns with the repository's scope before effort is expended.
2. **Style Changes:** Modifications to the `STYLE_GUIDE.md` or global templates require a PR and approval from at least two maintainers.
3. **Dispute Resolution:** In the event of a disagreement on technical accuracy (e.g., the "Excellent Answer" for a system design question), maintainers will defer to official documentation or consensus from reputable engineering blogs (e.g., Netflix Tech Blog, AWS Architecture Center).

## Pull Request Lifecycle

1. **Submission:** A contributor opens a PR. The CI pipeline runs `markdownlint`, `markdown-link-check`, and `spellcheck`.
2. **Review:** A maintainer reviews the PR within 72 hours, focusing on technical accuracy and adherence to the `STYLE_GUIDE.md` (specifically the "Hiring Manager" tone).
3. **Merge:** Once approved and CI passes, the PR is merged via Squash and Merge to maintain a clean history.

## Code of Conduct Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported by contacting the project team. The maintainers will review and investigate all complaints, and will respond in a way that it deems appropriate to the circumstances.
