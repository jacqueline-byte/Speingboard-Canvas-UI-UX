# Springboard Canvas UI/UX

A collection of custom HTML and CSS interfaces, course homepage designs, and learning resources developed for integration with Springboard's Canvas LMS.

This repository contains the source files for custom-designed Canvas experiences. It provides a central location to maintain, update, and publish these interfaces independently of the Canvas course pages in which they are embedded.

## Table of Contents

- [Project Overview](#project-overview)
- [Live Site](#live-site)
- [Repository Structure](#repository-structure)
- [Technology Stack](#technology-stack)
- [How It Works](#how-it-works)
- [Making Changes](#making-changes)
- [Deployment and Publishing](#deployment-and-publishing)
- [Embedding Pages in Canvas](#embedding-pages-in-canvas)
- [Testing and Quality Assurance](#testing-and-quality-assurance)
- [Troubleshooting](#troubleshooting)
- [Security and Access Considerations](#security-and-access-considerations)
- [Maintenance and Handover](#maintenance-and-handover)

## Project Overview

The purpose of this repository is to support custom UI/UX experiences within Springboard's Canvas learning environment.

The repository can be used to:

- Create and maintain custom course homepage layouts.
- Develop reusable HTML and CSS components for Canvas pages.
- Host static HTML resources that can be embedded in Canvas using an iframe.
- Maintain standalone learning resources, including flashcard interfaces.
- Iterate on design and functionality without having to rebuild the entire Canvas page for every visual change.

**Important:** Changes to files in this repository may affect live pages embedded in Canvas. Always identify where a file is being used before modifying or removing it.

## Live Site

**GitHub Pages URL:**  
https://jacqueline-byte.github.io/Springboard-Canvas-UI-UX/

The site is intended to serve the repository's published static HTML files.

To access an individual page, append its filename to the base URL. For example:

`https://jacqueline-byte.github.io/Springboard-Canvas-UI-UX/ailep-dark.html`

The availability of individual pages depends on their current filenames and GitHub Pages deployment status.

## Repository Structure

The repository currently includes the following files and folders:

| File or folder | Description |
|---|---|
| `2spt-homepage.html` | SPT homepage interface, version 2 |
| `SPTnew-homepage.html` | SPT homepage design |
| `spt-homepage.html` | SPT homepage implementation |
| `ailep-dark.html` | Dark-themed AILEP homepage |
| `ailep-homepage.html` | AILEP homepage interface |
| `vital-signs-flashcards.html` | Standalone vital signs flashcard resource |
| `SPT Homepage/` | Supporting files associated with the SPT Homepage work; inspect the folder before making changes |
| `README.md` | Project documentation and maintenance instructions |

**Before modifying files:** Review the HTML source and Git history to determine which versions are current, which are historical, and which are actively embedded in Canvas. Do not assume that a filename containing "new" or a higher version number is the production version.

## Technology Stack

- **HTML:** Page structure and content.
- **CSS:** Layout, typography, spacing, colors, and responsive styling.
- **JavaScript:** Interactive behavior, where implemented.
- **GitHub:** Source control and version history.
- **GitHub Pages:** Static website hosting.
- **Instructure Canvas LMS:** Learning platform where selected pages may be embedded.

This is intended to be a static front-end project. No backend server is assumed. Confirm the individual files before introducing additional frameworks, libraries, or build tools.

## How It Works

The workflow has three main components:

1. **Source files:** HTML, CSS, and any supporting assets are maintained in GitHub.
2. **Published pages:** GitHub Pages serves the deployed static files over HTTPS.
3. **Canvas integration:** A Canvas page can embed a published HTML page using an iframe, allowing the external interface to appear within the Canvas learning environment.

The HTML hosted on GitHub Pages and the Canvas page containing the iframe are separate resources. Updating the external HTML may change what appears inside Canvas without requiring the iframe URL itself to change.

However, Canvas permissions, browser restrictions, caching, and iframe configuration can affect the final result.

## Making Changes

### 1. Review the existing implementation

Before editing a file:

- Read the existing HTML, CSS, and JavaScript.
- Identify referenced images, fonts, scripts, stylesheets, and other assets.
- Search for the filename or URL in the repository to identify related implementations.
- Determine whether the page is currently embedded in a live Canvas course.
- Preserve existing course content, approved wording, and working links unless a change has been explicitly requested.

### 2. Edit the appropriate file

Make the smallest practical change that meets the requirement.

Avoid unnecessarily rewriting an entire page when a targeted CSS or HTML change will work. This reduces the risk of introducing regressions.

### 3. Preview and validate

Before publishing, verify:

- The page loads without errors.
- Layouts render correctly at desktop and mobile widths.
- Links, buttons, navigation, and interactive elements work.
- Images, fonts, and other assets load successfully.
- Content is readable and accessible.
- No unintended changes have been made to existing text or functionality.

### 4. Save and review the change

Use meaningful commit messages that explain what changed and why.

Examples:

- `Update SPT homepage spacing`
- `Fix vital signs flashcard interaction`
- `Improve responsive homepage layout`
- `Document Canvas embedding process`

For changes with a significant impact on a live page, review the diff and test the updated page before considering the work complete.

## Deployment and Publishing

GitHub Pages publishing is configured through the repository's **Settings → Pages** section.

Check the current publishing configuration before making deployment changes. The existing configuration should be treated as the source of truth.

If the repository publishes from the `main` branch and the root directory, changes to files in that publishing source can be deployed automatically after they are committed and pushed.

If a GitHub Actions workflow is configured instead, follow that workflow's build and deployment process.

### Recommended publishing workflow

1. Review the current production version.
2. Make and validate the required change.
3. Commit the change with a descriptive message.
4. Push it to the appropriate branch.
5. Check the repository's Actions tab for deployment status.
6. Open the published page and confirm that the change is visible.
7. Test the page inside Canvas if it is embedded in a course.

Do not change the publishing branch, folder, or workflow without understanding the impact on the live site.

## Embedding Pages in Canvas

A published HTML page can be embedded in a Canvas page using an iframe.

Example:

```html
<iframe
  src="https://jacqueline-byte.github.io/Springboard-Canvas-UI-UX/2spt-homepage.html"
  width="100%"
  height="2500"
  style="border: none;"
  title="SPT Homepage">
</iframe>
```

Replace the `src` value with the exact published URL of the intended page.

The height in this example is illustrative and should be adjusted to fit the content. A fixed iframe height can cause excess whitespace or internal scrolling if the page content changes.

### Canvas integration checks

- Confirm that the published URL is correct and uses HTTPS.
- Confirm that the HTML page is accessible from the intended viewing environment.
- Check that Canvas permits the external content to load.
- Test the embedded experience at typical desktop and mobile widths.
- Verify that links and navigation behave as expected inside the iframe.
- Confirm that the embedded page does not expose content that should remain restricted.

A published GitHub Pages URL should not be treated as private merely because it is embedded inside a restricted Canvas course.

## Testing and Quality Assurance

Use the following checklist for meaningful updates:

- [ ] HTML structure and styling render correctly.
- [ ] No broken images, scripts, stylesheets, or external links.
- [ ] Interactive components work as expected.
- [ ] Text, headings, and approved course content remain intact.
- [ ] Responsive layouts are checked.
- [ ] Accessibility basics, including keyboard navigation and text contrast, are reviewed.
- [ ] The published page reflects the intended changes.
- [ ] The page is tested inside Canvas when applicable.
- [ ] No unintended changes affect other pages or shared assets.

## Troubleshooting

### Changes are not appearing on the live page

1. Check the latest commit on GitHub.
2. Check the Actions tab for deployment failures.
3. Confirm that the correct branch and publishing source are configured.
4. Wait for deployment to finish.
5. Hard-refresh the browser.
6. Check whether browser or Canvas caching is serving an older version.

If necessary, a temporary cache-busting query parameter can help test whether a stale resource is being served:

`https://jacqueline-byte.github.io/Springboard-Canvas-UI-UX/2spt-homepage.html?v=2`

Increment the version value when testing a new revision. This does not fix deployment failures, and it should not replace proper cache management.

### The page works in a browser but not in Canvas

- Verify the iframe URL.
- Check browser developer tools for loading errors.
- Review Canvas restrictions and browser security policies.
- Check whether external resources are blocked.
- Verify the page's layout at the iframe's actual dimensions.

### A page appears broken after an update

- Review the latest commit and compare the changes.
- Check the browser console for JavaScript errors.
- Check for missing assets or incorrect relative paths.
- Restore a known-good version if needed, following the team's change-control process.

## Security and Access Considerations

This repository contains static front-end resources. It should not be used to store secrets, API keys, access tokens, private learner information, or other sensitive data.

Keep the following in mind:

- GitHub repository visibility and GitHub Pages site visibility are separate considerations.
- A public GitHub Pages URL can be accessed independently of Canvas login requirements.
- An iframe does not provide authentication or authorization for the page it embeds.
- Private repository access does not automatically make published website content private.
- Access restrictions must be implemented and verified through an appropriate authentication and authorization system when restricted access is required.
- Do not assume that hiding a link or keeping a URL out of navigation makes a page secure.

Before hosting course-specific or restricted resources, confirm the required access controls with the relevant platform or security owner.

## Maintenance and Handover

A future maintainer should complete the following checks before making production changes:

1. Confirm access to the GitHub repository and the account or organization responsible for maintaining it.
2. Review the GitHub Pages publishing configuration and any associated Actions workflows.
3. Identify the current production HTML files and their Canvas locations.
4. Identify shared assets, external dependencies, and any third-party scripts.
5. Review the latest commits and previous working versions.
6. Test the affected page in a browser and within Canvas.
7. Document any new dependencies, configuration changes, or known limitations.

### Recommended ongoing practices

- Keep filenames descriptive and consistent.
- Remove obsolete files only after confirming that they are no longer referenced.
- Record significant changes in commit messages.
- Update this README whenever deployment procedures, dependencies, or project structure change.
- Maintain a clear distinction between active production pages and archived or experimental versions.
- Keep repository ownership and publishing permissions available to the appropriate team members.

## Related Resources

- [GitHub Repository](https://github.com/jacqueline-byte/Springboard-Canvas-UI-UX)
- [Published GitHub Pages Site](https://jacqueline-byte.github.io/Springboard-Canvas-UI-UX/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Pages Publishing Configuration](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

---

**Documentation maintenance:** Update this file as the project evolves so that it remains a reliable reference for future contributors and maintainers.
