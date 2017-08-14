```java runnable
// { autofold
import java.util.Arrays;
import java.util.List;

public class Main {

public static void main(String[] args) throws Exception {

// }

// Method 1: basic structures
List<String> strings = Arrays.asList("1", "2", "3", "4", "5");
boolean isIncluded = strings.contains("6");
System.out.println("6 is the list: " + isIncluded);

// Method 2: complex structures
List<User> users = getUsers();
String userToFind = "Bobby";
boolean userExists = users.stream().anyMatch(user -> userToFind.equals(user.name));
System.out.println("Bobby is in the list: " + userExists);

//{ autofold

}

public static List<User> getUsers() {
    return Arrays.asList(
        new User("Ali"),
        new User("Bobby"),
        new User("Charlie"),
        new User("Dora")
    );
}

}

class User {
    public String name;

    User(String name) {
        this.name = name;
    }
}

//}
```
