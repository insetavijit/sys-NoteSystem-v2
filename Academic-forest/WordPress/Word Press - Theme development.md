# Senior WordPress Developer Course Syllabus

### Quick Access
- [[Wordpress functions table]]

## Course Overview

This course is designed for industry professionals seeking to upgrade their skills to become Senior WordPress Developers. It focuses on advanced WordPress development, modern workflows, and enterprise-grade practices. Over **16 weeks**, participants will master WordPress core, theme and plugin development, DevOps integration, and portfolio-building projects to meet the expectations of mid-to-large agencies and enterprises.

**Duration:** 16 weeks (8–10 hours/week)  
**Target Audience:** Intermediate developers with foundational PHP, JavaScript, HTML/CSS, and Git knowledge.  
**Outcome:** Participants will be job-ready for Senior WordPress Developer roles, with a robust portfolio and advanced technical skills.

---

## Phase 0: Prerequisites (Pre-Course Review, 1 Week)

**Objective:** Ensure foundational skills are solid before diving into advanced WordPress concepts.  
**Topics:**

- PHP: OOP (classes, interfaces, traits), namespaces, design patterns (Singleton, Factory)
- JavaScript: ES6+ (arrow functions, destructuring, modules), async/await, fetch/AJAX
- HTML/CSS: Semantic HTML, CSS Grid/Flexbox, responsive design
- Git: Branching, merging, rebasing, pull requests

**Activities:**

- Review PHP OOP with a small project (e.g., build a simple class-based CLI app).
- Practice modular JavaScript with a small ES6+ script.
- Set up a Git repository and practice advanced workflows (e.g., resolving merge conflicts).

---

## Phase 1: WordPress Core Deep Dive (Weeks 1–3)

**Objective:** Master WordPress architecture and core APIs for professional development.  
**Topics:**

- **Week 1: [[WordPress Architecture]]**
    - Core files, template hierarchy, execution flow
    - Database schema: `wp_posts`, `wp_postmeta`, `wp_terms`, etc.
    - Hooks system: Actions and filters
- **Week 2: [[Core APIs - wp]]**
    - Options API, Metadata API, Transients API
    - Shortcodes API, Settings API, HTTP API
    - Introduction to WP-CLI: Commands and scripting
- **Week 3: Security & Performance**
    - Security: Nonces, sanitization, escaping, user roles/capabilities
    - Performance: Object caching, query optimization, lazy loading

**Activities:**

- Build a custom settings page using the Settings API.
- Create a WP-CLI script to automate database updates.
- Analyze and optimize a WordPress query for performance.

---

## Phase 2: Professional Theme Development (Weeks 4–6)

**Objective:** Develop scalable, maintainable, and client-ready WordPress themes.  
**Topics:**

- **Week 4: Theme Fundamentals**
    - Starter themes: `_s`, Sage, Roots.io
    - Modular theme structure: Template parts, partials, hooks
    - Enqueueing scripts/styles, conditional logic
- **Week 5: Gutenberg Development**
    - Custom Gutenberg blocks using React
    - Block patterns and dynamic blocks
    - Block editor APIs
- **Week 6: Advanced Theme Features**
    - Accessibility (WCAG 2.1 compliance)
    - Internationalization (i18n) and localization (l10n)
    - Custom queries with `WP_Query` and `get_posts`

**Activities:**

- Develop a custom theme from `_s` with modular template parts.
- Create a custom Gutenberg block with React and register it in a theme.
- Localize a theme for multiple languages.

---

## Phase 3: Advanced Plugin Development (Weeks 7–9)

**Objective:** Build enterprise-grade plugins with robust architecture and integrations.  
**Topics:**

- **Week 7: Plugin Architecture**
    - OOP structure, MVC patterns, autoloading
    - Advanced hooks: Actions and filters
    - Custom post types and taxonomies
- **Week 8: Database & Admin Interfaces**
    - Custom database tables, `wpdb` usage, migrations
    - Admin interfaces: Settings pages, meta boxes
- **Week 9: APIs & Security**
    - REST API: Custom endpoints, authentication
    - Security: Input sanitization, nonces, capability checks
    - Packaging plugins for WordPress.org or private distribution

**Activities:**

- Build a plugin with a custom post type, settings page, and REST API endpoint.
- Create a database migration script for a custom table.
- Secure a plugin with proper validation and nonces.

---

## Phase 4: Modern Workflow & DevOps (Weeks 10–12)

**Objective:** Integrate WordPress development with industry-standard DevOps practices.  
**Topics:**

- **Week 10: Local Development & Build Tools**
    - Local environments: Docker, LocalWP, Lando
    - Task runners: NPM, Webpack, Gulp
- **Week 11: Version Control & CI/CD**
    - Git workflows: Feature branches, pull requests, code reviews
    - CI/CD pipelines: GitHub Actions for testing/deployment
- **Week 12: Deployment & Environments**
    - Staging/production setup: Backups, rollback strategies
    - WP-CLI for migrations and automation
    - Environment configuration (`.env`, `wp-config.php`)

**Activities:**

- Set up a Docker-based WordPress development environment.
- Configure a GitHub Actions pipeline for automated testing.
- Deploy a WordPress site to a staging environment with WP-CLI.

---

## Phase 5: Enterprise WordPress Skills (Weeks 13–15)

**Objective:** Prepare for large-scale WordPress projects and senior-level responsibilities.  
**Topics:**

- **Week 13: WooCommerce Customization**
    - Hooks, filters, custom endpoints
    - Custom checkout flows, payment integrations
- **Week 14: Headless WordPress**
    - Headless architecture with React/Next.js
    - WP REST API for content delivery
    - GraphQL integration with WPGraphQL
- **Week 15: Performance & Security**
    - Performance: Query profiling, CDN integration, image optimization
    - Security: Penetration testing, vulnerability mitigation
    - Multisite: Network setup, domain mapping

**Activities:**

- Build a custom WooCommerce checkout field with validation.
- Develop a headless WordPress site with a Next.js frontend.
- Conduct a performance audit and optimize a WordPress site.

---

## Phase 6: Portfolio & Industry Readiness (Week 16)

**Objective:** Build a professional portfolio and prepare for senior-level roles.  
**Topics:**

- Portfolio projects:
    - Custom theme with Gutenberg blocks
    - Advanced plugin with REST API integration
    - WooCommerce store with customizations
    - Headless WordPress + React/Next.js site
- Contributing to WordPress Core or open-source plugins
- Soft skills: Client communication, requirement gathering, code documentation
- Job preparation: Debugging legacy code, technical interviews

**Activities:**

- Complete and polish portfolio projects.
- Contribute a patch to a WordPress plugin or Core.
- Practice debugging a poorly written WordPress theme/plugin.

---

## Course Requirements

- **Technical Setup:** Local development environment (Docker/LocalWP), Git, Node.js, WP-CLI
- **Portfolio:** 4 completed projects showcasing advanced skills
- **Final Assessment:** Build and deploy a fully functional WordPress site with custom theme, plugin, and headless frontend.

## Industry Expectations

- **Technical Skills:** Mastery of WordPress APIs, modular code, performance optimization
- **Workflow:** Git-based collaboration, CI/CD, modern tooling
- **Problem-Solving:** Debugging, legacy code refactoring, client-facing solutions
- **Portfolio:** Demonstrates real-world, scalable WordPress projects

## Resources

- Official WordPress Codex & Developer Handbook
- WP-CLI Documentation
- React & Next.js Documentation for headless setups
- WooCommerce Developer Guides
- GitHub Actions Documentation