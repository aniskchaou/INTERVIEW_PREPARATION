## SRP : The Single Responsibility Principle

A class should have one, and only one, reason to change.

## Bad

**Employee.java**

    public class Employee {
    
        long id;
        String name;
        String type;
    
        public Employee(long id, String name, String type) {
            this.id = id;
            this.name = name;
            this.type = type;
        }
    
        public void saveToDatabase()
        {
            
        }
        
        public void calculateTax()
        {
            if(this.type.equals("full time"))
            {
                
            }
        }
    }

## Good
**Employee.java**

    public class Employee {
    
        long id;
        String name;
        String type;
    
        public Employee(long id, String name, String type) {
            this.id = id;
            this.name = name;
            this.type = type;
        }
    
        public void saveToDatabase()
        {
            new EmployeeRepository().save(this);
        }
        
        public void calculateTax()
        {
           new TaxCalculator().calculateTax(this);
        }
    }

**EmployeeRepository.java**

    public class EmployeeRepository{
        
        public void save(Employee employee)
        {
            
        }
    }

**TaxCalculator.java**

    public class TaxCalculator{
        
        public void calculateTax(Employee employee)
        {
             if(employee.equals("full time"))
            {
                
            }
        }
    }

