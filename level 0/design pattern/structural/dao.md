## Data access object

Data Access Object Pattern or DAO pattern **is used to separate low level data accessing API or operations from high level business services** 
![Image result for dao pattern](https://www.tutorialspoint.com/design_pattern/images/dao_pattern_uml_diagram.jpg)

## Student

    public class Student {
       private String name;
       private int rollNo;
    
       Student(String name, int rollNo){
          this.name = name;
          this.rollNo = rollNo;
       }
    
       public String getName() {
          return name;
       }
    
       public void setName(String name) {
          this.name = name;
       }
    
       public int getRollNo() {
          return rollNo;
       }
    
       public void setRollNo(int rollNo) {
          this.rollNo = rollNo;
       }
    }

## StudentDAO

    public interface StudentDao {
       public List<Student> getAllStudents();
       public Student getStudent(int rollNo);
       public void updateStudent(Student student);
       public void deleteStudent(Student student);
    }

## StudentDAOImpl

    public class StudentDaoImpl implements StudentDao {
    	
       //list is working as a database
       List<Student> students;
    
       public StudentDaoImpl(){
          students = new ArrayList<Student>();
          Student student1 = new Student("Robert",0);
          Student student2 = new Student("John",1);
          students.add(student1);
          students.add(student2);		
       }
       @Override
       public void deleteStudent(Student student) {
          students.remove(student.getRollNo());
          System.out.println("Student: Roll No " + student.getRollNo() + ", deleted from database");
       }
    
       //retrive list of students from the database
       @Override
       public List<Student> getAllStudents() {
          return students;
       }
    
       @Override
       public Student getStudent(int rollNo) {
          return students.get(rollNo);
       }
    
       @Override
       public void updateStudent(Student student) {
          students.get(student.getRollNo()).setName(student.getName());
          System.out.println("Student: Roll No " + student.getRollNo() + ", updated in the database");
       }
    }

## Main

    public class DaoPatternDemo {
       public static void main(String[] args) {
          StudentDao studentDao = new StudentDaoImpl();
    
          //print all students
          for (Student student : studentDao.getAllStudents()) {
             System.out.println("Student: [RollNo : " + student.getRollNo() + ", Name : " + student.getName() + " ]");
          }
    
    
          //update student
          Student student =studentDao.getAllStudents().get(0);
          student.setName("Michael");
          studentDao.updateStudent(student);
    
          //get the student
          studentDao.getStudent(0);
          System.out.println("Student: [RollNo : " + student.getRollNo() + ", Name : " + student.getName() + " ]");		
       }
    }
