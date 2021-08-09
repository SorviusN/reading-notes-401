# Read 12 - Entity Framework

### EF Core NuGet Packages
The EF SQL Server package and its dependencies, Microsoft.EntityFrameworkCore and Microsoft.EntityFrameworkCore.Relational, provide runtime support for EF.

## Create data models / classes

``` cs
using System;
using System.Collections.Generic;

namespace ContosoUniversity.Models
{
    public class Student
    {
        public int ID { get; set; }
        public string LastName { get; set; }
        public string FirstMidName { get; set; }
        public DateTime EnrollmentDate { get; set; }

        public ICollection<Enrollment> Enrollments { get; set; }
    }
}
```
The ID property is the primary key (PK) column of the database table that corresponds to this class. By default, EF interprets a property that's named ID or classnameID as the primary key. For example, the PK could be named StudentID rather than ID.

## Database context

    The main class that coordinates EF functionality for a given data model is the DbContext database context class. This class is created by deriving from the Microsoft.EntityFrameworkCore.DbContext class. The DbContext derived class specifies which entities are included in the data model. Some EF behaviors can be customized. In this project, the class is named SchoolContext.

### Database context example
``` cs
using ContosoUniversity.Models;
using Microsoft.EntityFrameworkCore;

namespace ContosoUniversity.Data
{
    public class SchoolContext : DbContext
    {
        public SchoolContext(DbContextOptions<SchoolContext> options) : base(options)
        {
        }

        // Setting up the database components, just telling the database that they exist.
        public DbSet<Course> Courses { get; set; }
        public DbSet<Enrollment> Enrollments { get; set; }
        public DbSet<Student> Students { get; set; }
    }
}
```
