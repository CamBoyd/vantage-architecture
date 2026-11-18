
# Vantage — Construction Accounting Platform

Vantage is a full-stack construction accounting application currently under development.

The platform is designed to support the financial and operational needs of construction companies, including project costing, accounts payable, accounts receivable, general ledger, payroll, equipment management, and cash management.

I am the co-founder and sole software engineer responsible for the architecture and implementation of Vantage, working alongside two business partners who provide business and design consultation.

> Development Status: Pre-launch. Core application infrastructure and foundational features have been implemented. Most accounting-specific business logic remains under development.

## Technology Stack

| Component | Technology |
|-----------|------------|
| Language | TypeScript |
| Application Framework | Next.js |
| Frontend | React |
| Database | PostgreSQL |
| ORM | Prisma |
| Data Grids | AG Grid |
| Styling | Tailwind CSS, DaisyUI |
| API Layer | Next.js REST Route Handlers |

## Architecture Highlights

### Relational Database Design

Vantage currently contains almost 200 relational database tables designed to represent construction accounting entities, financial transactions, and associated business relationships.

### REST API Architecture

The application contains more than 100 custom REST API routes that provide database access and foundational application functionality.

### Metadata-Driven User Interface

Vantage uses a reusable interface framework built with React and AG Grid.

Rather than hard-coding individual data-entry tables, the application reads metadata defining the available columns, their data types, editing behavior, and validation requirements.

The interface dynamically generates its configuration from this metadata.

### Dynamic Validation Framework

The validation framework uses column metadata to determine which database routine should validate a field.

When users finish editing a field, the application can resolve the appropriate routine, construct its parameters, execute the validation, and display any returned errors.

### Unified Ledger Architecture

Vantage is designed around a unified ledger architecture where financial transactions maintain direct relationships with their corresponding general ledger entries.

This design aims to improve transaction traceability and reduce the need for manual reconciliation.

## Technical Documentation

- [System Architecture](docs/system-architecture.md)
- [Database Design](docs/database-design.md)
- [Metadata Driven UI](https://github.com/CamBoyd/vantage-architecture/blob/main/docs/metadata-driven-ui.md)

## Project Status

Vantage is an active, independently developed commercial software project.

The source code is proprietary and is not publicly available. This repository provides a high-level technical overview of selected architectural decisions and engineering challenges.
