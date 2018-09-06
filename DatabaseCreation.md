Data creattion:
  1. Module folders create Module class, eg Student.cs, Course.cs, Enrollment.cs:
 ------------------------------------      
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
-------------------------------------
  2. Data folder create Database Context, eg SchoolContext.cs:
-----------------------------------
using ContosoUniversity.Models;
using Microsoft.EntityFrameworkCore;

namespace ContosoUniversity.Data
{
    public class SchoolContext : DbContext
    {
        public SchoolContext(DbContextOptions<SchoolContext> options) : base(options)
        {
        }

        public DbSet<Course> Courses { get; set; }
        public DbSet<Enrollment> Enrollments { get; set; }
        public DbSet<Student> Students { get; set; }
    }
}
------------------------------------


