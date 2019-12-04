# java_examples
examples of java concepts such as:

OOP, dependency injection, polimorfism and others


1- dep_Injection is a .jar exported with Spring Framework that contain a little project to show us an example of how to use dependency inyection to improve our code.

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
 
