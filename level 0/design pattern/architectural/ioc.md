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


class OracleServer implements IDBServer{
    @Override
    public void data(){
        System.out.println("get data from orcale server"); 
    }
}

interface IDBServer{
    void data();
}
class MySQLServer implements IDBServer{
    @Override
    public void data(){
        System.out.println("get data from mysql server");
    }
}

class Client{
    public static void main(String[] args) {
      Employee employee=new Employee(new MySQLServer());
      employee.getData();
      
      employee.setDataBase(new OracleServer());
      employee.getData();
    }
}