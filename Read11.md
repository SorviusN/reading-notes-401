# Read 11 - Database Schemas (ERD)

    What is a Schema?
    A schema is a "blueprint" of sorts that defines what properties a query will have.
    Why do we use them?
    To understand the relationship between one diagram and the next. Creates context.
    What do they look like?
    They are boxes of sorts that contain Keys, Properties and Nav properties.

Keys  

    What is a Primary Key?
    The defined key of the schema that it represents.
    What is a Foreign Key?
    Foreign keys are used within navigation properties to assign one schema to another.
    What is a Composite Key?
    Joins together the two primary keys of different schemas. (Hotel and associated room, for instance)
    How are they different? When do you use 1 over the others?
    Primary is for idenitification, foreign is for association and composite is for unification.

Relationships

    What is a 1:1 relationship?
    One schema per one schema.
    What is a Many:Many relationship?
    Many schemas may be attached to many other types of schemas.
    How about a 1: Many or a Many:1?
    One schema has many of the other type of schema and vice versa.

