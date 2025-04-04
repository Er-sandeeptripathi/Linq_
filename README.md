Linq 

class-1
 List<int> list = new List<int> { 1,22,3,4,5,6,7,8,9,10};

 var querysyntax = from obj in list where obj%2== 0 select obj;

 var query = list.Where(x => x %2==0);
 foreach (var item in querysyntax)
 {
     Console.WriteLine(item);
 }
 Console.WriteLine("-------------------------------------------------");

 foreach (var item in querysyntax)
 {
     Console.WriteLine(item);
 }
        
        class-2  using select operator 
         
static void Main(string[] args)
{

    List<employee> employee = new List<employee>
    {
        new employee(){id=1,name="sandeep",Email="sandeeptripathi1212.s@gmail.com"},
        new employee(){id=2,name="tanu",Email="tanu122.s@gmail.com"},
        new employee(){id=3,name="Anurag",Email="Anurag.s@gmail.com"},
        new employee(){id=4,name="Adarsh",Email="adarsh122.s@gmail.com"},
        new employee(){id=5,name="Pranshu",Email="pa122.s@gmail.com"}


    };

    var Query = (from emp in employee  select emp).ToList();//fetch all data 

    var Query = (from emp in employee  select emp.name).ToList();// only id 
    foreach(var item in Query)
    {
        Console.WriteLine(item);
    }


    //Mehod syntax 

    var methodQuery = employee.Select(x => x.id).ToList();
    Console.ReadKey();
}

 class -4 

    var query = (from emp in employee select emp.id+1).ToList();
  var MehodQuery = employee.Select(x => x.id.tostring()).ToList();

  
  Query -5 


to select only sume specific fields like name and id so we can use
 new keyword 

 syntax


  var query = (from emp in employee
             select new employee()
             {
               id=emp.id,
               name=emp.name
             }).ToList();
          
 foreach(var item in query)
 {
     Console.WriteLine(item.id+""+item.name+""+item.Email);
 }

 methodQuery 
   var mehod = employee.Select(x => new employee()
  {
      Email = x.Email,
      name = x.name
  }).ToList();


  
  class- 

  single char print 

1. SelectMany
    List<string> strList = new List<string>() { "Ramesh", "Kumar" };

  var Method= strList.SelectMany(x => x).ToList();


Query syntax

  var Query = (from emp in strList select from ch in emp select ch).ToList();
      
           
class- selectin the all employee Skill using SelectMany Method

            var dataSource = new List<employee>
    {
        new employee(){id=1,name="sandeep",Email="sandeeptripathi1212.s@gmail.com",Program=new List<string>(){"C#","PHP","Java"} },
        new employee(){id=2,name="tanu",Email="tanu122.s@gmail.com",Program=new List<string>(){"C#","PHP","Java"}},
        new employee(){id=3,name="Anurag",Email="Anurag.s@gmail.com",Program=new List<string>(){"Linq","c++","Javasript"}},
        new employee(){id=4,name="Adarsh",Email="adarsh122.s@gmail.com",Program=new List<string>(){"C#","PHP","Java"}},
        new employee(){id=5,name="Pranshu",Email="pa122.s@gmail.com",Program=new List<string>(){"C#","PHP","Java"}}


    };


            var MethosSyntax = dataSource.SelectMany(emp => emp.Program).ToList();
            foreach (var item in MethosSyntax)
            {
                Console.WriteLine(item);
            }

            var Query = (from emp in dataSource from Skill in emp.Program select Skill).ToList();

            foreach (var item in Query)
            {
                Console.WriteLine(item);
            }

in employee class
        public List<string> Program { get; set; }



Filtering operator

 Filtering is the process of selecting a subset of elements from a 
 collection based on a specified condition. In LINQ, filtering is typically done using the
  Where operator. The Where operator takes a predicate (a function that returns true or false)
   and returns a new collection containing only the elements that satisfy the predicate.

   We can wrire one more condition based on the requirements

   example
    student having number f greater than 50 and less than 80
    emplyee having salary less than 50k
     list of student having attendance more than 90% and marks MORE THAN 80% 



     where operator
      where come under filtering operator
      where operator is used to filter the data based on the condition 
      where operator is used in query syntax and method syntax
      condition can be written using following symbols
    
    == equal to
    != not equal to 
    > greater than
    < less than
    >= greater than or equal to
    <= less than or equal to
    && and
    || or
    ! not
    ? : conditional operator
    

    example

var datasourec = new List<int>() { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

var Querysyntax = (from number in datasourec
                  where number > 5
                  select number).ToList();

var MethodQuery = datasourec.Where(x => x > 5).ToList();
foreach (var item in Querysyntax)
{
    Console.WriteLine(item);
}

example -2 using string

 var datasourec = new List<string>() {"ram","Shaym","Suresh","Rakesh","Rajesh","Mukesh","Sukhes"};

 var querySyntax = (from name in datasourec where name.Length == 3 select name).ToList();

 var MethodQuery = datasourec.Where(emp => emp.Length == 3||emp.Length<=5).ToList();
 foreach (var item in MethodQuery)
 {
     Console.WriteLine(item);
 }
more complex example using string

 using System.Collections.Generic;
using System.ComponentModel.Design;

namespace Linq_
{
    internal class employee
    {
        public int id { get; set; }
        public string name  { get; set; }
        public  string Email { get; set; }
        public List<techs> programming{ get; set; }
    }
    public class techs
    {
        public string Technology { get; set; }
    }
}



*fatching the  student hwo have no any Technology

using System;
using System.Collections.Generic;
using System.Linq;

namespace Linq_
{
    class Program
    {
        static void Main(string[] args)
        {
            var dataSource = new List<employee>
            {
                new employee(){id=1, name="sandeep", Email="sandeeptripathi1212.s@gmail.com", programming=new List<techs>{ new techs() { Technology="C#" } } },
                new employee(){id=2, name="john", Email="john.doe@example.com", programming=new List<techs>{ new techs() { Technology="Java" } } },
                new employee(){id=3, name="alice", Email="alice.smith@example.com", programming=new List<techs>{ new techs() { Technology="Python" } } },
                new employee(){id=4, name="bob", Email="bob.jones@example.com", programming=new List<techs>{ new techs() { Technology="JavaScript" } } },
                new employee(){id=5, name="carol", Email="carol.white@example.com", programming=new List<techs>{ new techs() { Technology="Ruby" } } },
                new employee(){id=6, name="david", Email="david.brown@example.com", programming=new List<techs>{ new techs() { Technology="Go" } } },
                new employee(){id=7, name="eva", Email="eva.green@example.com", programming=new List<techs>{ new techs() { Technology="Swift" } } },
                new employee(){id=8, name="frank", Email="frank.miller@example.com", programming=new List<techs>{ new techs() { Technology="Kotlin" } } },
                new employee(){id=9, name="grace", Email="grace.moore@example.com", programming=new List<techs>{ new techs() { Technology="PHP" } } },
                new employee(){id=10, name="hank", Email="hank.taylor@example.com", programming=new List<techs>{ new techs() { Technology="TypeScript" } } },
                new employee(){id=11, name="sandeep", Email="sandeeptripathi1212.s@gmail.com"},
                new employee(){id=12, name="tanu", Email="tanu122.s@gmail.com"},
                new employee(){id=13, name="Anurag", Email="Anurag.s@gmail.com"}
            };

            var Querysynt = (from std in dataSource
                             where std.programming == null || std.programming.Count == 0
                             select std).ToList();

            // Printing out the result
            foreach (var item in Querysynt)
            {
                Console.WriteLine($"Id: {item.id}, Name: {item.name}, Email: {item.Email}");
            }

            Console.ReadKey();
        }
    }

    
}







