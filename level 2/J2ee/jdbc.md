## JDBC

JDBC stands for Java Database Connectivity. JDBC is a Java API to connect and execute the query with the database.
# Statement interface

The  **Statement interface**  provides methods to execute queries with the database. The statement interface is a factory of ResultSet i.e. it provides factory method to get the object of ResultSet.

### Commonly used methods of Statement interface:

The important methods of Statement interface are as follows:

**1) public ResultSet executeQuery(String sql):**  is used to execute SELECT query. It returns the object of ResultSet.

**2) public int executeUpdate(String sql):**  is used to execute specified query, it may be create, drop, insert, update, delete etc.

**3) public boolean execute(String sql):**  is used to execute queries that may return multiple results.

**4) public int[] executeBatch():**  is used to execute batch of commands.

    1.  public  static  void main(String args[])throws Exception{
    2.  Class.forName("oracle.jdbc.driver.OracleDriver");
    3.  Connection con=DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:xe","system","oracle");
    4.  Statement stmt=con.createStatement();
    
    5.  //stmt.executeUpdate("insert into emp765 values(33,'Irfan',50000)");
    6.  //int result=stmt.executeUpdate("update emp765 set name='Vimal',salary=10000 where id=33");
    7.  int result=stmt.executeUpdate("delete from emp765 where id=33");
    8.  System.out.println(result+" records affected");
    9.  con.close();
    10.  }}
    11. 

# ResultSet interface

**The object of ResultSet maintains a cursor pointing to a row of a table.** Initially, cursor points to before the first row.


    1.  Statement stmt = con.createStatement(ResultSet.TYPE_SCROLL_INSENSITIVE,
    2.  ResultSet.CONCUR_UPDATABLE);
    3.  Class.forName("oracle.jdbc.driver.OracleDriver");
    4.  Connection con=DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:xe","system","oracle");
    5.  Statement stmt=con.createStatement(ResultSet.TYPE_SCROLL_SENSITIVE,ResultSet.CONCUR_UPDATABLE);
    6.  ResultSet rs=stmt.executeQuery("select * from emp765");
    
    7.  //getting the record of 3rd row
    8.  rs.absolute(3);
    9.  System.out.println(rs.getString(1)+" "+rs.getString(2)+" "+rs.getString(3));
    
    10.  con.close();

# PreparedStatement interface

The PreparedStatement **interface is a subinterface of Statement.** It is used to execute parameterized query.


### Why use PreparedStatement?

**Improves performance**: The performance of the application will be faster if you use PreparedStatement interface because query is compiled only once.

    1.  PreparedStatement stmt=con.prepareStatement("insert into Emp values(?,?)");
    2.  stmt.setInt(1,101);//1 specifies the first parameter in the query
    3.  stmt.setString(2,"Ratan");
    
    5.  int i=stmt.executeUpdate();
    6.  System.out.println(i+" records inserted");
    
    8.  con.close();
