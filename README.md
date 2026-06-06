# week1oops

// 1. Define the Interface
interface LibraryUser {
    void registerAccount();
    void requestBook();
}

// 2. KidUser Class
class KidUser implements LibraryUser {
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
        if ("Kids".equalsIgnoreCase(bookType)) {
            System.out.println("Book Issued successfully, please return the book within 10 days");
        } else {
            System.out.println("Oops, you are allowed to take only kids books");
        }
    }
}

// 3. AdultUser Class
class AdultUser implements LibraryUser {
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
        if ("Fiction".equalsIgnoreCase(bookType)) {
            System.out.println("Book Issued successfully, please return the book within 7 days");
        } else {
            System.out.println("Oops, you are allowed to take only adult Fiction books");
        }
    }
}

// 4. The LibraryInterfaceDemo
public class LibraryInterfaceDemo {
    public static void main(String[] args) {
        
        // --- Test Case #1: KidUser ---
        System.out.println("--- KidUser Test Case ---");
        KidUser kid = new KidUser();
        
        kid.age = 10;
        kid.registerAccount();
        kid.age = 18;
        kid.registerAccount();

        kid.bookType = "Kids";
        kid.requestBook();
        kid.bookType = "Fiction";
        kid.requestBook();

        System.out.println(); 

        // --- Test Case #2: AdultUser ---
        System.out.println("--- AdultUser Test Case ---");
        AdultUser adult = new AdultUser();
        
        adult.age = 5;
        adult.registerAccount();
        adult.age = 23;
        adult.registerAccount();
        
        adult.bookType = "Kids";
        adult.requestBook();
        adult.bookType = "Fiction";
        adult.requestBook();
    }
}
