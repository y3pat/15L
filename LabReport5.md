Part 1: 


Student : Hi! I'm unsure why my J-unit test is not working for reversing in place  as the tests passed before. Why is it working for half the array but not the rest.


<img width="1117" alt="Screen Shot 2024-03-13 at 1 08 08 AM" src="https://github.com/y3pat/15L/assets/129999149/e9270c0f-5e79-452e-a16c-7904970436ed">

I am guessing that there is something wrong with the indexes but I'm not super sure. 

Tutor: Hey, what was the test you tried earlier? What are the differences with that and your current result? The answer is in the last part of your question regarding why only a certain part of the array gets reversed. 

Student: I tried it with one value and my test passed. However, I realise now that by the time we got to the last element, changing it ot he frist one meant the value was not being changed. I fixed this by only going to half the array length as by then the whole array is reversed already. Thank you so much! Here is the j-unit output of the test working: 

<img width="1117" alt="Screen Shot 2024-03-13 at 1 06 52 AM" src="https://github.com/y3pat/15L/assets/129999149/6a3c475d-6e42-40e3-be9e-0316740fa388">


Contents of files before fixing bug :

Array Examples: 

```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

```

ArrayTests:
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 ,4,5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5,4,3}, input1);
	}
}
```


Contents of file after fixing the bug: 


```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for (int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
}

```
ArrayTests:
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 ,4,5};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5,4,3}, input1);
	}
}
```
File Structure: 

<img width="357" alt="Screen Shot 2024-03-13 at 1 10 55 AM" src="https://github.com/y3pat/15L/assets/129999149/4b8d13f9-637a-436a-ad33-aa7dc6480711">

Lab3Main
  ArrayExamples.java
  ArrayTests.java

Part 2: 
I didn't realise how an autograder worked. It was very interesting to think about all the differnet situations we need to consider and the amount of work needed. I always wondered what happened
to my code when I submitted it on gradescope and I now have a deeper understanding of it. I've also gotten super familiar with the comand line which was something I was scared of before. All the skill demos and labs truly helped me become more comfortable and this was a really useful class. 
