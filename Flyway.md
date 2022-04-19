---
aliases: []
---
# Flyway
#computer-science #computer-engineering #database

Flyway is an open-source database migration tool. It strongly favors simplicity and convention over configuration.

Migrations can be written in [[SQL]] or [[Java]].

## Supported Database Engines
- [[Oracle]]
- [[MS SQL]]
- [[MySQL]]
- [[PostgreSQL]]
- [[Redshift]]
- [[Amazon RDS]]

There's more than this, but these are some important ones.

## Migrations
---

All database changes via Flyway are called migrations. Migrations can be either _versioned_ or _repeatable_.

### Versioned Migrations

Versioned migrations have three parts:

- **Version** - The version of the migration. Must be unique.
- **Description** - The description of the migration.
- **Checksum** - The checksum of the migration to detect accidental changes.


Versioned migrations are the most common type of migration. They are applied in order exactly once.


Versioned migrations are typically used for:

- Creating/altering/dropping tables/indexes/foreign keys/enums/UDTs/…
- Reference data updates
- User data corrections

#### Example
```sql
CREATE TABLE car (
    id INT NOT NULL PRIMARY KEY,
    license_plate VARCHAR NOT NULL,
    color VARCHAR NOT NULL
);

ALTER TABLE owner ADD driver_license_id VARCHAR;

INSERT INTO brand (name) VALUES ('DeLorean');
```

### Repeatable Migrations

Repeatable migrations have two parts:

- **Description** - The description of the migration.
- **Checksum** - The checksum of the migration to detect accidental changes.

Repeatable migrations are run every time their checksum changes. They are typically used for:

- (Re-)creating views/procedures/functions/packages/…
- Bulk reference data reinserts

#### Example
```sql
CREATE OR REPLACE VIEW blue_cars AS
    SELECT id, license_plate FROM cars WHERE color='blue';
```

## Migration Syntax
Migration files have specific naming conventions to identify the type and order of migration.

- **Prefix** - `V` for versioned migration, `U` for undo migration, `R` for repeatable migration
- **Version** - Whatever version number you want to use
- **Seperator** - `__` two underscores
- **Description** - The description of the migration
- **Suffix** - `.sql`

### Example
Versioned migration:
`V2__Add_New_Table.sql`

Undo migration:
`U2__Add_New_Table.sql`

Repeatable migration:
`R__Add_New_Table.sql`

## Flyway Config Options
---
Flyway can be configured via command line options, a config file, or both.

### Config File Options




## Flyway Commands
---