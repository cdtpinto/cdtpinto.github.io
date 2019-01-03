## Buse & Weimer Metric

Contrary to the other readability formulas implemented in Readability Checker, B&W metric was developed to evaluate the readability of small code snippets.

Its authors conducted a study among 120 students, where they presented some code snippets ranging from 4 to 11 lines of code. The average number of lines of code was 7.7.

These code snippets didn't include a full class definition, nor an entire method.

## Implementation

In order to be able to use this metric to calculate the readability of entire Java files, Readability Checker uses the following approach:

1. Load a Java file
2. Split code of the file in blocks of 8 lines of code
3. Calculate readability for each block of code (using tool developed by the metric authors)
4. Calculate the average readability of all the code blocks

The average readability of every code block in a Java file is the final readability value of that file.

## Example

```java
package example;

public class Example {

    private static boolean isPrime(int num) {
        if (num == 2) {
            return true;
        }
        if (num < 2 || num % 2 == 0) {
            return false;
        }
        for (int i = 3; i * i <= num; i += 2) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }

}

```

This example would be splitted in three blocks of code:

* First block from lines 1 to 8 -> `package example;` to `}` with readability value 0.99
* Second block from lines 9 to 16 -> `if (num < 2 || num % 2 == 0) {` to `}` with readability value 0.67
* Third block from lines 17 to 20 -> `return true;` to `}` with readability value 0.99

The average value is 0.88, thus that is the readability value for the presented code.
