### SDET Interview Question and Answers

Chronological

#### Java coding questions

1. Remove duplicates from the given array of numbers without using Set or stream api

- Input : int[] array = {100, 3, 4, 16, 177, 134, 3, 16}
- Output : {100, 3, 4, 16, 177, 134}
- Approach-1 : Efficient way

```java
import java.util.*;

public class Main {

    public static void main(String[] args) {

        int[] input = {100, 3, 4, 16, 177, 134, 3, 16};

        List<Integer> output = new ArrayList<>();

        for (int num : input) {
            if (!output.contains(num)) {
                output.add(num);
            }
        }

        System.out.println("Output: " + output);
    }
}

```

- Approach-2 : In-Efficient way O(n^2) [I implemented this in interview]

```java
import java.util.*;

public class Main {

    public static void main(String[] args) {

        int[] input = {100, 3, 4, 16, 177, 134, 3, 16};

        List<Integer> output = new ArrayList<Integer>();

        for(int number : input){
            output.add(number);
        }

        for(int i=0; i<output.size(); i++){

		    for(int j=i+1; j<output.size(); j++){

		        if(output.get(i)==output.get(j)){
		            output.remove(j);
		            j--;
		        }
		    }
	    }

		System.out.println("Output : "+output);
    }
}

```

2. Print below pattern

```java
*
* *
* * *
```

- Answer:

```java
public class Main {
    public static void main(String[] args) {
        int n = 3; // Number of rows

        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}

```

3. Given a string contains numbers separated by spaces. Print the sum of the numbers in the string?

- Answer

```java
public class Main {
    public static void main(String[] args) {
        String input = "10 20 30 40 50"; // Example input string containing numbers separated by spaces

        // Split the input string by spaces
        String[] numbers = input.split(" ");

        // Initialize sum
        int sum = 0;

        // Iterate through the array of numbers
        for (String number : numbers) {
            // Convert each substring to an integer and add to the sum
            sum += Integer.parseInt(number);
        }

        // Print the sum
        System.out.println("Sum: " + sum);
    }
}

```

4. Copy one list's elements into another empty list using python

- a = [1,2,3]
- b = []
- output : b = [1,2,3]
- Method 1: Using List Comprehension

```python
a = [1, 2, 3]
b = [x for x in a]
print(b)  # Output: [1, 2, 3]
```

- Method 2: Using the **copy** Method

```python
a = [1, 2, 3]
b = a.copy()
print(b)  # Output: [1, 2, 3]

```

- Method3: Using Slicing

```python
a = [1, 2, 3]
b = a[:]
print(b)  # Output: [1, 2, 3]

```

- Method4: Using the **list** Constructor

```python
a = [1, 2, 3]
b = list(a)
print(b)  # Output: [1, 2, 3]

```

- Method5: Using the **extend** Method

```python
a = [1, 2, 3]
b = []
b.extend(a)
print(b)  # Output: [1, 2, 3]

```

5. Copy one list's elements into another empty list using Java

- Answer:

```java
public class Main {
    public static void main(String[] args) {
        int[] a = {1, 2, 3};
        int[] b = new int[a.length];

        // Copy elements from a to b
        for (int i = 0; i < a.length; i++) {
            b[i] = a[i];
        }

        // Print the outputArray
        System.out.print("b: [");
        for (int i = 0; i < b.length; i++) {
            System.out.print(b[i]);
            if (i < b.length - 1) {
                System.out.print(", ");
            }
        }
        System.out.println("]");
    }
}

```
