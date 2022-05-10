# wasm-entity-core
this repo handles the new wasm entity core project



# Title
WASM Entity Core
## Language
Go

## Description
The wasm entity core os a project that focus the world inside the browser application to work with a datastorage as a local or remote extension.
You can define in javascript or typescript a entity mapping to resolve the data from a instance. inside the web assembly there is an go implementation of a sql like database new defined. It gives you a relational view to data inside a much better usage then a library.


## Examples
### Entities
   var customer = EntityCore.create("Customer").scheme("Name","text",50).scheme("Id","auto-int").build();
   var result = EntityCore.execute(customer);
   if (Entity.IsDone(result)){
        Console.Write("Statement executed");
   }else{
        Console.Write("Error Statement",EntityCore.Log(result).Message);
   }
### Query
  var customers = EntityCore.query("Customer");
  foreach(var customer in customers){
      Console.Write(customer.json());
  }
### Filtering
  var customers = EntityCore.query("Customer").where("Name").equals("John Doe").lower();
  foreach(var customer in customers){
      Console.Write(customer.json());
  }

