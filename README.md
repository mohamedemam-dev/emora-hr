# Emora HR

**Arabic-first workforce management for growing companies.**

Emora HR brings employee self-service and day-to-day people operations into one responsive SaaS experience. Teams can organize company locations, manage shifts and attendance, submit employee requests, and review workforce and payroll information through role-aware workspaces.

> **Showcase note:** Emora HR is a commercial product. Its full source code and operational configuration are maintained in a private repository. This README is intended for a public product and engineering showcase.

[Open the web experience](https://hr-emora.vercel.app)

## What the product supports

- **Company setup and organization:** company profile, regions, branches, employees, and company-scoped roles.
- **Attendance:** employee check-in and check-out with browser geolocation, branch geofence checks, attendance history, and management review.
- **Shift planning:** branch and region workspaces, weekly schedules, spreadsheet import/export, publishing, and review requests for scoped changes.
- **Employee requests:** leave, hourly permission, salary advance, and penalty workflows with staged management review.
- **People operations:** employee access management, device activation, payroll views, reports, and notifications.
- **Employee portal:** personal attendance, schedule, requests, and payroll information in a mobile-friendly experience.
- **Arabic-first interface:** RTL layouts, Arabic copy, and responsive views for desktop and phones.

## Authorization model

Emora separates company membership from platform administration. Company roles apply within a company, and operational access is limited by assigned scope:

| Role | Typical access |
| --- | --- |
| Company Owner | Company-wide administration and settings |
| HR / Company Moderator | Company people operations according to granted permissions |
| Area Manager | Employees, branches, schedules, and reviews within assigned regions |
| Branch Manager | Employees and schedules within the assigned branch; selected actions require higher-level review |
| Employee | Personal portal, attendance, schedule, and requests |

Authorization is enforced through Supabase-backed server operations and company/region/branch scope checks. The interface reflects those permissions, but backend checks remain the security boundary.

## Engineering showcase

This project demonstrates full-stack product work across:

- Authentication and onboarding, including email verification and session callbacks.
- A multi-tenant data model with PostgreSQL, row-level security, scoped RPCs, and server-side operations.
- Supabase Edge Functions for privileged workflows that must remain server-side.
- Hierarchical authorization and staged approvals for workforce requests.
- Geolocation-based attendance validation against branch settings.
- Responsive Arabic RTL application design and reusable loading states.
- SQL migrations, TypeScript integration, and focused contract tests.

## Technology

- **Web:** Next.js App Router, React, TypeScript
- **Data and identity:** Supabase Auth, PostgreSQL, SQL migrations, RPCs, and Edge Functions
- **Hosting:** Vercel
- **Additional libraries:** `@supabase/ssr`, `@supabase/supabase-js`, Lucide icons, and SheetJS (`xlsx`)

## Validation snapshot

The local project has passed TypeScript type checking and a focused set of 16 authorization and workflow contract tests. These checks validate selected code and SQL contracts; they are not a substitute for end-to-end testing with representative Owner, HR, Area Manager, Branch Manager, and Employee accounts.

## Product and source

- **Web experience:** [hr-emora.vercel.app](https://hr-emora.vercel.app)
- **Product:** Emora HR — إدارة الموارد البشرية
- **Built by:** Mohamed Ahmed Emam — Full-stack development with Next.js, TypeScript, Supabase, and PostgreSQL

For a showcase review or a guided product walkthrough, contact the maintainer. Access to the commercial source repository and production administration is restricted.
