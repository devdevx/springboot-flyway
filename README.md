# Introduction

Flyway allows us to manage all database migrations in a easy and automatic mode.

# Configuration

## Add the maven dependency

```
<dependency>
    <groupId>org.flywaydb</groupId>
    <artifactId>flyway-core</artifactId>
</dependency>
```

## Configure the properties

```
spring.flyway.out-of-order=true
```

By enabling this feature you now can fill all gaps in the migration sequence. This is really helpful for dealing with migration scripts that are in different branches.

## Define the sql version scripts

The slq scripts are located in the `resources/db/migration` folder.

By default, the name should follow the pattern `V<version_number>__<description>.sql`

# Try it

You can run the project, go to `localhost:8080/h2-console` and log in with the default credentials (simply click 'Connect').

The table `flyway_schema_history` contains all the info related to the migration scripts.

The `ddl-auto` property is configured in validation mode to ensure that the database schema is correct.