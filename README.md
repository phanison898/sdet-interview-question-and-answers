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
