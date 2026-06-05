# week1oops
oops
//question 1
public interface LibraryUser {
    void registerAccount();
    void requestBook();
}
//question 2,3,4 and 5
public class KidUser implements LibraryUser {
    int age;
    String bookType;

    @Override
    public void registerAccount() {
        if (age < 12) {
            System.out.println("You have successfully registered under a Kids Account");
        } else {
            System.out.println("Sorry, Age must be less than 12 to register as a kid");
        }
    }

    @Override
    public void requestBook() {
        if (bookType.equals("Kids")) {
            System.out.println("Book Issued successfully, please return the book within 10 days");
        } else {
            System.out.println("Oops, you are allowed to take only kids books");
        }
    }
}
// AdultUser.java
public class AdultUser implements LibraryUser {
    int age;
    String bookType;

    @Override
    public void registerAccount() {
        if (age > 12) {
            System.out.println("You have successfully registered under an Adult Account");
        } else {
            System.out.println("Sorry, Age must be greater than 12 to register as an adult");
        }
    }

    @Override
    public void requestBook() {
        if (bookType.equals("Fiction")) {
            System.out.println("Book Issued successfully, please return the book within 7 days");
        } else {
            System.out.println("Oops, you are allowed to take only adult Fiction books");
        }
    }
    // question 6
   public class LibraryInterfaceDemo {
    public static void main(String[] args) {
  
        KidUser kidUser = new KidUser();
        //case 1
        kidUser.age = 10;
        kidUser.registerAccount();

        kidUser.age = 18;
        kidUser.registerAccount();

        kidUser.bookType = "Kids";
        kidUser.requestBook();

        kidUser.bookType = "Fiction";
        kidUser.requestBook();
        // case 2
        AdultUser adultUser = new AdultUser();

        adultUser.age = 5;
        adultUser.registerAccount();

        adultUser.age = 23;
        adultUser.registerAccount();

        adultUser.bookType = "Kids";
        adultUser.requestBook();

        adultUser.bookType = "Fiction";
        adultUser.requestBook();
    }
}
