### SDET Interview Question and Answers

1. <details>

   <summary>Find the frequency of each element in the array</summary>

   ```yml
   - Description: Print the frequency of each element in the array in a single line separated by space
   - Array type: Integer
   - How: Enter the array of elements through Command Line
   ```

   ```java
    import java.util.Map;
    import java.util.LinkedHashMap;
    import java.util.Arrays;

    public class Main {
        public static void main(String[] args) {

            String[] stringArray = args;
            Integer[] intArray = Arrays.stream(args).map(Integer::valueOf)toArray(Integer[]::new);
            Character[] charArray = args[0].chars().mapToObj(c->(char)c).toArray(Character[]::new);

            Util<Integer> util = new Util<>(array);
            util.printFrequencyOfElement();
        }
    }

    class Util<T> {

        T[] array;

        Util(T[] array) {
        	this.array = array;
        }

        void printFrequencyOfElement() {
        	Map<T,Integer> map = new LinkedHashMap<>();
        	for(T element : array) {
        		map.put(element, map.getOrDefault(element, 0) + 1);
        	}

        	for(Map.Entry<T, Integer> entry : map.entrySet()) {
        		System.out.println(entry.getKey()+"="+entry.getValue());
        	}
        }

    }
   ```

</details>

If when we need to perform comparison operation between elements of an array, then follow the below approach

**Approach:-1**

```java

import java.util.List;
import java.util.ArrayList;

public class Main {

 public static void main(String[] args){

      // this is input array. what ever type it is
     int[] input = {100,2,56,124,52,67,423,7,102,2,124,33,67,52};

     List<Integer> list = new ArrayList<Integer>();
     for(Integer i : input){
         if(!list.contains(i)){
              list.add(i);
         }
     }

     System.out.print(list);
 }
}

```

**Approach:-2**

```java

import java.util.List;
import java.util.ArrayList;

public class Main {

    public static void main(String[] args){

         // this is input array. what ever type it is
        int[] input = {100,2,56,124,52,67,423,7,102,2,124,33,67,52};

        List<Integer> list = new ArrayList<Integer>();
        for(Integer i : input){
            list.add(i);
        }

        for(int i=0; i<list.size(); i++){
            for(int j=i+1; j<list.size(); j++){
                if(list.get(i)==list.get(j)){
                    list.remove(j);
                    j--;
                }
            }
        }

        System.out.print(list);

    }

}

```

Chronological Order

#### Java coding interview questions which asked for the role of SDET

### 1. Qentelli

**1. Round-1 (Technical - L1):-**

- Q1) Verify given number is Palindrome or not
- Q2) Remove special characters from the string

  **Hard way**

  ```java

  public class Main {

      public static void main(String[] args) {

          String input = "hgwddg&134^je234hbwhedeytr65R$%RbVYdtdr37VHF65*^&%vs12";

          StringBuilder output = new StringBuilder();

          for(char c : input.toCharArray()){
              if(Character.isDigit(c) || Character.isLetter(c)){
                  output.append(c);
              }
          }

          System.out.print(output.toString());
      }
  }

  ```

  **Easy way**

  ```java

  public class Main {

      public static void main(String[] args) {

          String input = "hgwddg&134^je234hbwhedeytr65R$%RbVYdtdr37VHF65*^&%vs12";

          String output = input.replaceAll("[^a-zA-Z0-9]","");

          System.out.print(output);
      }
  }

  ```

**2. Round-2 (Technical - L3):-**

- Q1) Remove duplicate characters from the string
- Q2) Given a string containing words separated by space. Now, reverse the each word without changing it's initial position (Ex: input = "my name is phani"; output= "ym eman si inahp";)

**3. Round-3 (Client round):-**

- Q1) Given a string, now, place each character in ascending order

  **Hard way**

  ```java
  import java.util.*;

  public class Main {

      public static void main(String[] args) {

          String input = "Phani";

          char[] array = input.toLowerCase().toCharArray();

          for(int i=0; i<array.length-1; i++){
              for(int j=0; j<array.length-i-1; j++){
                  if(((int) array[j]) > ((int) array[j+1])){
                      char temp = array[j];
                      array[j] = array[j+1];
                      array[j+1] = temp;
                  }
              }
          }

          System.out.print(new String(array));
      }
  }

  ```

  **Easy way**

  ```java
  import java.util.*;

  public class Main {

      public static void main(String[] args) {
          String input = "Phani";

          char[] array = input.toLowerCase().toCharArray();

          Arrays.sort(array);

          String output = new String(array);

          System.out.print(output);
      }
  }

  ```

- Q2) Create a Java class for above problem and ask the input from the user and print it

---

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
