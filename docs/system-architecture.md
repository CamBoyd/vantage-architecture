
flowchart TD
    A["React / AG Grid UI"]
    B["Next.js Application"]
    C["REST API Routes"]
    D["Metadata and Validation Logic"]
    E["Prisma ORM"]
    F[("PostgreSQL")]

    A <--> B
    B --> C
    B --> D
    C --> E
    E <--> F
    D --> F
