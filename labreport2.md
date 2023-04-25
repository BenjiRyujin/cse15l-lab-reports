**Lab Report 2**

**Part 1**

<img width="785" alt="Screenshot 2023-04-24 at 9 54 48 PM" src="https://user-images.githubusercontent.com/55765860/234177809-41f35012-cea7-4959-ab56-b54cabf0f1ed.png">


<img width="637" alt="Screenshot 2023-04-24 at 10 00 12 PM" src="https://user-images.githubusercontent.com/55765860/234178523-1454d12d-83f6-47f8-8507-579ffd0a0397.png">

The "getPath" method from the URI class returns the path of the given url in the form of a string. The path is what follows after the domain, indicated by the first "/". The "getQuery" method is also called, which takes in the following url after the "?". The string returned by "getQuery" is then split into an array in a field called "parameters". Parameters[1] in this case represents the actual string input that will be added to the message presented on screen. In this first attempt, because the "message" variable was an empty string before, the screen simply presents the string that was typed into the query.


<img width="656" alt="Screenshot 2023-04-24 at 10 00 45 PM" src="https://user-images.githubusercontent.com/55765860/234178593-f946aa9c-49d9-487b-8bc9-aed306eba552.png">

When another string is typed into the query, the same methods specified in the first example run again. However, in this case, "message" is no longer an empty string, but the string that was used in the last example. As a result, the new string presented on the screen carries both the old and new inputs.

**Part 2**

(`@Test
  public void testAverageWithoutLowest(){
    double[] input1 = {2,2,3,4};
    assertEquals(3.0, ArrayExamples.averageWithoutLowest(input1),0);
  }`)
