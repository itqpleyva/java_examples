# java_examples
examples of java concepts such as:

OOP, dependency injection, polimorfism and others


Example 1- dep_Injection is a .jar exported with Spring Framework that contain a little project to show us an example of how to use dependency inyection to improve our code.

in this case we inject in Futbolist.java class, one interface type object, that allow us to have access to the showTeam() method of bouth classes, Barcelona.java and Juventus.java, 

    public class Futbolist {

      private ITeam iteam;

      public Futbolist(ITeam iteam) {
        this.iteam = iteam;
      }
      public void showTeam() {

        iteam.showTeam();
      }
    }
we just create an instance of Futbolist class in App.java, passing as parameter the object of the respective club class Barcelona or Juventus.

    Futbolist m = new Futbolist(new Barcelona());
    Futbolist mm = new Futbolist(new Juventus());
 
run the project and you will see the results.
 
Example 2 helloWorld is a .jar that have one example of the use Use of Spring Container (The Spring container is the core of Spring Framework. The container, use for creating the objects and configuring them. Also, Spring IoC Containers use for managing the complete lifecycle from creation to its destruction. It uses Dependency Injection (DI) to manage components and these objects are called Spring Beans.)

in this example we create a Spring Bean:

    <bean id="mundo" class="com.itqpleyva.bean.Mundo">
            <property name="saludo" value="Hola Mundo!!!"></property>
    </bean>
    
the class Mundo.java has the methods to suppor the modification or access to the atribute saludo

    public class Mundo {

        private String saludo;

        public String getSaludo() {
            return saludo;
        }

        public void setSaludo(String saludo) {
            this.saludo = saludo;
        }
    }
    
In the class App.java we can print a console message with the data stored in the spring bean, to get access to the bean fron this class we can use ApplicationContext, see the class:
  
    import org.springframework.context.support.ClassPathXmlApplicationContext;

    import com.itqpleyva.bean.Mundo;

    public class App {

        public static void main(String[] args) {

            ApplicationContext appContext = new ClassPathXmlApplicationContext("com/itqpleyva/xml/beans.xml");

            Mundo m = appContext.getBean(Mundo.class);

            System.out.println(m.getSaludo());

        }

    }
    
    run the project and you will se the results
