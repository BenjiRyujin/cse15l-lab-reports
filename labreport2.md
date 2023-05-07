**Lab Report 2**

**Part 1**

<img width="785" alt="Screenshot 2023-04-24 at 9 54 48 PM" src="https://user-images.githubusercontent.com/55765860/234177809-41f35012-cea7-4959-ab56-b54cabf0f1ed.png">


<img width="637" alt="Screenshot 2023-04-24 at 10 00 12 PM" src="https://user-images.githubusercontent.com/55765860/234178523-1454d12d-83f6-47f8-8507-579ffd0a0397.png">

The "getPath" method from the URI class returns the path of the given url in the form of a string. The path is what follows after the domain, indicated by the first "/". The "getQuery" method is also called, which takes in the following url after the "?". The string returned by "getQuery" is then split into an array in a field called "parameters". Parameters[1] in this case represents the actual string input that will be added to the message presented on screen. In this first attempt, because the "message" variable was an empty string before, the screen simply presents the string that was typed into the query.


<img width="656" alt="Screenshot 2023-04-24 at 10 00 45 PM" src="https://user-images.githubusercontent.com/55765860/234178593-f946aa9c-49d9-487b-8bc9-aed306eba552.png">

When another string is typed into the query, the same methods specified in the first example run again. However, in this case, "message" is no longer an empty string, but the string that was used in the last example. As a result, the new string presented on the screen carries both the old and new inputs.

**Part 2**
For the testAverageWithoutLowest method, there would be an unexpected outcome when an array had two lowest values of the same size. The method failed the test below.
```
@Test
  public void testAverageWithoutLowest(){
    double[] input1 = {2,2,3,4};
    assertEquals(2.75, ArrayExamples.averageWithoutLowest(input1),0);
  }
```
When the test was run, the following message would be reported:

```
benjiryujin@MacBook-Pro-90 lab3 % java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ArrayTests
JUnit version 4.13.2
.E..
Time: 0.012
There was 1 failure:
1) testAverageWithoutLowest(ArrayTests)
java.lang.AssertionError: expected:<2.75> but was:<3.0>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:555)
        at org.junit.Assert.assertEquals(Assert.java:685)
        at ArrayTests.testAverageWithoutLowest(ArrayTests.java:29)

FAILURES!!!
Tests run: 3,  Failures: 1
```

On the other hand, arrays where the lowest values were unique (where there would not be any multiple lowest values) reported expected outcomes. 

```
@Test
  public void testAverageWithoutLowest(){
    double[] input2 = {2,3,4,5};
    assertEquals(4.0, ArrayExamples.averageWithoutLowest(input2),0);
  }
```

Below is the code for the "testAverageWithoutLowest" method before it was fixed.

```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```

Below is the code after it was fixed.

```
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    int sum = 0;
    int count = 0;
    for(int i = 0; i<arr.length; i++){
      if(lowest == arr[i]){
        if(count ==0){
          count+=1;
          continue;
        }
      }
      sum += arr[i];
    }
    return sum / (arr.length - 1);
  }
```
This fix addresses the issue because adding a "count" variable ensures that the "lowest" number will only be ignored once while calculating the mean in the end. If "count" does not equal 0, indicating that the lowest number has already been ignored while calculating the sum, then although the number may match the lowest number, it is still added to the sum to be divided.

In week 2, it was the first time I had interacted with servers from the coding side. More specifically I learned about how URI's are a class that hold various types of information such as URLs, and how interfaces and allow us to easily digest and access certain parts of URLs such as paths or queries based on specific methods. Familiar methods such as `split` also come into play when taking in things such as queries.


  
