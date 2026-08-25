---
name: agents-entry-point
description: The primary entry point and rulebook for the AI agents. It provides the foundational understanding of the repository's structure, versioning system, and directory guidelines to properly locate and utilize domain-specific prompts.
---

# Agents Prompt Formatting Guide

This document outlines the standard structure, metadata, and directory guidelines required for creating and organizing prompts within this repository. 

Whenever an external repository uses a prompt from this repository, it **must** clearly document the exact file path and the specific version being used.

## Prompt Header Format

Every markdown file containing a prompt must begin with the following frontmatter header. This ensures we can programmatically track versions and avoid conflicts.

---
name: {name-id}
description: {description}
version: {Major}.{Minor}.{Patch}
---

*   **`name`**: A unique identifier for the prompt. (It must not duplicate any other prompt name in the repository).
*   **`description`**: A brief summary of what the prompt is designed to do.
*   **`version`**: Semantic versioning. Used to keep the prompt version, so each external repository will know exactly which version it is using and can update safely.

## Directory and File Structure

To maintain a clean and scalable repository, prompts must be organized using a 3-tier structure: Domain, Type (or Sub-system), and Technology/Core file. Please use the following structure:

### Core Sub-system Prompts
This file acts as the foundational or base prompt for a specific type or sub-system within a business domain.
*   **Path:** `{domain-name}/{type}/core.md`
*   **Example 1:** `account/user/core.md` (Base business rules and AI instructions for the standard user account system)
*   **Example 2:** `account/org/core.md` (Base rules for the organization/tenant account system)

### Specific Frameworks/Technologies
These files resemble the core sub-system project but contain specialized instructions tailored for specific tools, languages, or frameworks.
*   **Path:** `{domain-name}/{type}/{file-name}.md`
*   **Example 1:** `account/user/expressjs.md` (Specific backend API instructions for the user account system using ExpressJS)
*   **Example 2:** `account/org/react.md` (Specific frontend UI instructions for the organization account system using React)
*   **Example 3:** `car/rental/flutter.md` (Specific UI/mobile instructions for a car rental sub-system using Flutter)
