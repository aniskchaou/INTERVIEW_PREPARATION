# Inversion of control
![enter image description here](https://1.bp.blogspot.com/-J8WpN1ggXbg/UwngjVI0J-I/AAAAAAAABO0/KPZfOMrnWrg/s1600/1.png)
IoC is a design principle which **recommends the inversion of different kinds of controls in object-oriented design to achieve loose coupling between application classes.**
**Employee.java**

    class Employee{
       
        IDBServer  dataBase;
    
        public Employee(IDBServer dataBase) {
            this.dataBase = dataBase;
        }
       
        
        void getData(){
             this.dataBase.data();
        }
    
        public void setDataBase(IDBServer dataBase) {
            this.dataBase = dataBase;
        }
        
        
    }

**OracleServer .java**

    class OracleServer implements IDBServer{
        @Override
        public void data(){
            System.out.println("get data from orcale server"); 
        }
    }

**IDBServer.java**

    interface IDBServer{
        void data();
    }

**MySQLServer .java**

    class MySQLServer implements IDBServer{
        @Override
        public void data(){
            System.out.println("get data from mysql server");
        }
    }

**Client.java**

    class Client{
        public static void main(String[] args) {
          Employee employee=new Employee(new MySQLServer());
          employee.getData();
          
          employee.setDataBase(new OracleServer());
          employee.getData();
        }
    }


