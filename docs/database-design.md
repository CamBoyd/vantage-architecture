# Database Design

I have designed the entire database myself, by hand, using Draw.io.  Currently, the diagram is split between seven different categories for improved readability.

Those seven categories are:
1. Settings
2. Financials
3. Vendors
4. Customers
5. Projects
6. Payroll
7. Operations

The full database design is proprietary, but I can provide a few screenshots with examples of the design.

This is a section of the Vendors category.  "Vendors" includes anything that relates to accounts payable. 
<img width="1315" height="845" alt="image" src="https://github.com/user-attachments/assets/b5419d56-483b-4c70-9776-4b0ef4476ab6" />

This is a section of the Customers category.  "Customers" includes anything that relates to accounts receivable.
<img width="1317" height="853" alt="image" src="https://github.com/user-attachments/assets/f873ab2b-e3d9-4fa2-bd4b-dbca2dd01d19" />

This is a section of the Projects category.  "Projects" are all the projects that a construction company would work on and relates to both "Vendors" (expenses) and "Customers" (revenue).
<img width="1180" height="757" alt="image" src="https://github.com/user-attachments/assets/583f88f0-3f8f-4fe9-b6be-48132d0b4bed" />

### Unified Ledger Architecture

Vantage is being designed around a unified ledger architecture that maintains direct relationships between business transactions and their corresponding ledger entries.

Traditional accounting applications often maintain separate subledgers containing financial values that must be reconciled with the ledger. Vantage aims to reduce this duplication by treating the ledger as the authoritative source of financial transaction amounts and accounting dates.

Rather than storing the same financial values independently across multiple accounting tables, Vantage uses entity-specific linking tables to associate business records with their corresponding ledger entries. Separate linking tables exist for different entities, such as accounts payable invoices, accounts receivable invoices, and projects.

These linking records also contain transaction type identifiers that distinguish the nature of the associated financial activity, such as invoices and payments.

This design allows financial values to be derived from the related ledger activity while business-specific tables maintain the information required to describe and manage their respective entities.

Using separate linking tables also provides a relational structure through which foreign key constraints can enforce relationships between business entities and ledger records.

The architecture is intended to reduce duplicated financial data, improve transaction traceability, and minimize the need for traditional subledger-to-general-ledger reconciliation.

The database schema establishes the foundation for these relationships. However, much of the business logic required to implement complete accounting workflows is still under development.

As development progresses, the architecture will need to address transaction consistency, reversals, corrections, auditability, and the performance implications of deriving financial values from ledger entries.

### Potential Cross-Entity Relationships

The use of entity-specific linking tables may also allow individual ledger entries to be associated with multiple business entities. For example, a financial transaction could potentially be linked to both an accounts payable invoice and a construction project without duplicating the underlying ledger entry.

Although this capability has not yet been implemented or tested, the relational design provides a foundation for exploring cross-entity transaction relationships. Future development will need to ensure that these relationships preserve financial accuracy, avoid double-counting, and distinguish transaction references from financial allocations.
