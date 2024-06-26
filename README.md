### SDET Interview Question and Answers

Chronological Order

#### Java coding interview questions which asked for the role of SDET

### 1. UST Global

**1. Round-4 (Managerial):-** Remove duplicates from the given array of numbers without using Set or stream api

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

- Approach-2 : In-Efficient way O(n^2)

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

**1. Round-3 (L3 - Technical):-** Print below pattern

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

**2. Round-2 (L2 - Technical):-** Q1) Copy one list's elements into another empty list using python

- a = [1,2,3] # input
- b = [] # empty list
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

Q2) Copy one list's elements into another empty list using Java

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

**3. Round-1 (L1 - Technical):-** Given a string contains numbers separated by spaces. Print the sum of the numbers in the string?

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

### 2. Synechron

**1. Round-1 (L1 - Technical):-**

- Given a string containing duplicate words. Print each word along with number of times it's repeated
- Input = "automation is very good automation is very nice";
- Output = automation=2 is=2 very=2 good=1 nice=1
- Solution:

```java
import java.util.*;

public class Main
{
	public static void main(String[] args) {
		String input = "automation is very good automation is very nice";

		// split using space
		String[] words = input.split(" ");

		// copy to list
		List<String> wordList = new ArrayList<String>();
		for(String word : words){
		    wordList.add(word);
		}

		//count repeated words
		int count = 1;

		// output
		StringBuilder output = new StringBuilder();

		//loop through words
		for(int i=0; i<wordList.size(); i++){
		    for(int j=i+1; j<wordList.size(); j++){
		        if(wordList.get(i).equals(wordList.get(j))){
		            count++;
		            wordList.remove(j);
		            j--;
		        }
		    }
		    output.append(wordList.get(i)+"="+count+" ");
		    count = 1;
		}
		System.out.print(output.toString().trim());
	}
}
```

**2. Round-2 (L2 - Technical):-**

- Check whether the given string is palindrom or not
- Input : "madam"
- Output : Palindrom
- Solution:

```java
import java.util.Scanner;

public class Main
{
    	public static void main(String[] args) {

         System.out.print("Enter any string: ");
    	    String input = new Scanner(System.in).next();

    	    StringBuilder reverse = new StringBuilder();

    	    for(int i=input.length()-1; i>=0; i--){
    	        reverse.append(input.charAt(i));
    	    }

    	    if(input.equals(reverse.toString())){
    	        System.out.print(input+" is Palindrom");
    	    }else{
    	        System.out.print(input+" is not Palindrom");
    	    }
    	}
}
```
