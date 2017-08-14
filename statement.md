```java runnable
// { autofold
import java.util.Arrays;
import java.util.List;

class User {
    public int id;
    public String name;

    User(int id, String name) {
        this.id = id;
        this.name = name;
    }
    
    public String toString() {
        return "{ id: " + id + ", name: " + name + " }";
    }
}

public class Main {

public static List<User> getUsers() {
    return Arrays.asList(
        new User(1, "Ali"),
        new User(2, "Bobby"),
        new User(3, "Charlie"),
        new User(4, "Dora")
    );
}

public static void main(String[] args) throws Exception {

// }

// Method 1: basic structures
List<Integer> integers = Arrays.asList(1, 2, 3, 4, 5);
int integerToFind = 6;
boolean integerExists = integers.contains(integerToFind);
System.out.println("6 is the list: " + integerExists);

// Method 2: complex structures
List<User> users = getUsers();
String userToFind = "Bobby";
boolean userExists = users.stream().anyMatch(user -> userToFind.equals(user.name));
System.out.println("Bobby is in the list: " + userExists);

// Method 3: find the element that matches the condition
User bobby = users.stream()
    .filter(user -> userToFind.equals(user.name))
    .findFirst()
    .orElse(null);
System.out.println("Bobby: " + bobby);

// { autofold

}

}

// }
```
