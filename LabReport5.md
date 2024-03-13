Part 1: 


Student : Hi! I'm unsure why my J-unit test is not working for reversing in place  as the tests passed before. Why is it working for half the array but not the rest.


<img width="1117" alt="Screen Shot 2024-03-13 at 1 08 08 AM" src="https://github.com/y3pat/15L/assets/129999149/e9270c0f-5e79-452e-a16c-7904970436ed">

I am guessing that there is somethign wrong with the indexes but I'm not super sure. 

Tutor: Hey, what was the test you tried earlier? What are the differences with that and your current result? The answer is in the last part of your question regarding why only a 
certain part of the array gets reversed. 

Student: I tried it with one value and my test passed. However, I realise now that by the time we got to the last element, changing it ot he frist one meant the value was not being changed. 
I fixed this by only going to half the array length as by then the whole array is reversed already. Thank you so much! Here is the j-unit output of the test working: 

<img width="1117" alt="Screen Shot 2024-03-13 at 1 06 52 AM" src="https://github.com/y3pat/15L/assets/129999149/6a3c475d-6e42-40e3-be9e-0316740fa388">


Contents of files before fixing bug :

Array Examples: 

``

public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

}

``

Contents of file after fixing the bug: 

`` 
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

`` 
