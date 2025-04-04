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
