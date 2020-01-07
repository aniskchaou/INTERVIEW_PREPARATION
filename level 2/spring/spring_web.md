
### 2. Create the bean class

Here, the bean class contains the variables (along setter and getter methods) corresponding to the fields exist in the database.

**Emp.java**

    1.  package com.javatpoint.beans;
    
    3.  public  class Emp {
    4.  private  int id;
    5.  private String name;
    6.  private  float salary;
    7.  private String designation;
    
    9.  public  int getId() {
    10.  return id;
    11.  }
    12.  public  void setId(int id) {
    13.  this.id = id;
    14.  }
    15.  public String getName() {
    16.  return name;
    17.  }
    18.  public  void setName(String name) {
    19.  this.name = name;
    20.  }
    21.  public  float getSalary() {
    22.  return salary;
    23.  }
    24.  public  void setSalary(float salary) {
    25.  this.salary = salary;
    26.  }
    27.  public String getDesignation() {
    28.  return designation;
    29.  }
    30.  public  void setDesignation(String designation) {
    31.  this.designation = designation;
    32.  }
    
    34.  }

### 3. Create the controller class

**EmpController.java**

    1.  package com.javatpoint.controllers;
    2.  import java.util.List;
    3.  import org.springframework.beans.factory.annotation.Autowired;
    4.  import org.springframework.stereotype.Controller;
    5.  import org.springframework.ui.Model;
    6.  import org.springframework.web.bind.annotation.ModelAttribute;
    7.  import org.springframework.web.bind.annotation.PathVariable;
    8.  import org.springframework.web.bind.annotation.RequestMapping;
    9.  import org.springframework.web.bind.annotation.RequestMethod;
    10.  import com.javatpoint.beans.Emp;
    11.  import com.javatpoint.dao.EmpDao;
    12.  @Controller
    13.  public  class EmpController {
    14.  @Autowired
    15.  EmpDao dao;//will inject dao from XML file
    
    17.  /*It displays a form to input data, here "command" is a reserved request attribute
    18.  *which is used to display object data into form
    19.  */
    20.  @RequestMapping("/empform")
    21.  public String showform(Model m){
    22.  m.addAttribute("command", new Emp());
    23.  return  "empform";
    24.  }
    25.  /*It saves object into database. The @ModelAttribute puts request data
    26.  * into model object. You need to mention RequestMethod.POST method
    27.  * because default request is GET*/
    28.  @RequestMapping(value="/save",method = RequestMethod.POST)
    29.  public String save(@ModelAttribute("emp") Emp emp){
    30.  dao.save(emp);
    31.  return  "redirect:/viewemp";//will redirect to viewemp request mapping
    32.  }
    33.  /* It provides list of employees in model object */
    34.  @RequestMapping("/viewemp")
    35.  public String viewemp(Model m){
    36.  List<Emp> list=dao.getEmployees();
    37.  m.addAttribute("list",list);
    38.  return  "viewemp";
    39.  }
    40.  /* It displays object data into form for the given id.
    41.  * The @PathVariable puts URL data into variable.*/
    42.  @RequestMapping(value="/editemp/{id}")
    43.  public String edit(@PathVariable  int id, Model m){
    44.  Emp emp=dao.getEmpById(id);
    45.  m.addAttribute("command",emp);
    46.  return  "empeditform";
    47.  }
    48.  /* It updates model object. */
    49.  @RequestMapping(value="/editsave",method = RequestMethod.POST)
    50.  public String editsave(@ModelAttribute("emp") Emp emp){
    51.  dao.update(emp);
    52.  return  "redirect:/viewemp";
    53.  }
    54.  /* It deletes record for the given id in URL and redirects to /viewemp */
    55.  @RequestMapping(value="/deleteemp/{id}",method = RequestMethod.GET)
    56.  public String delete(@PathVariable  int id){
    57.  dao.delete(id);
    58.  return  "redirect:/viewemp";
    59.  }
    60.  }

### 4. Create the DAO class

Let's create a DAO class to access the required data from the database.

**EmpDao.java**

    1.  package com.javatpoint.dao;
    2.  import java.sql.ResultSet;
    3.  import java.sql.SQLException;
    4.  import java.util.List;
    5.  import org.springframework.jdbc.core.BeanPropertyRowMapper;
    6.  import org.springframework.jdbc.core.JdbcTemplate;
    7.  import org.springframework.jdbc.core.RowMapper;
    8.  import com.javatpoint.beans.Emp;
    
    10.  public  class EmpDao {
    11.  JdbcTemplate template;
    
    13.  public  void setTemplate(JdbcTemplate template) {
    14.  this.template = template;
    15.  }
    16.  public  int save(Emp p){
    17.  String sql="insert into Emp99(name,salary,designation) values('"+p.getName()+"',"+p.getSalary()+",'"+p.getDesignation()+"')";
    18.  return template.update(sql);
    19.  }
    20.  public  int update(Emp p){
    21.  String sql="update Emp99 set name='"+p.getName()+"', salary="+p.getSalary()+",designation='"+p.getDesignation()+"' where id="+p.getId()+"";
    22.  return template.update(sql);
    23.  }
    24.  public  int delete(int id){
    25.  String sql="delete from Emp99 where id="+id+"";
    26.  return template.update(sql);
    27.  }
    28.  public Emp getEmpById(int id){
    29.  String sql="select * from Emp99 where id=?";
    30.  return template.queryForObject(sql, new Object[]{id},new BeanPropertyRowMapper<Emp>(Emp.class));
    31.  }
    32.  public List<Emp> getEmployees(){
    33.  return template.query("select * from Emp99",new RowMapper<Emp>(){
    34.  public Emp mapRow(ResultSet rs, int row) throws SQLException {
    35.  Emp e=new Emp();
    36.  e.setId(rs.getInt(1));
    37.  e.setName(rs.getString(2));
    38.  e.setSalary(rs.getFloat(3));
    39.  e.setDesignation(rs.getString(4));
    40.  return e;
    41.  }
    42.  });
    43.  }
    44.  }
