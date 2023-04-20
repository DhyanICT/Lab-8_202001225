# Lab-8_202001225
<h2> Creating new project and Junit test case </h2>

- I created a new Eclipse project called "Dhyan_202001225" and created packeg named " Lab8_package1".

  ![c1](https://user-images.githubusercontent.com/124245399/233314720-b0c2e1f9-5ece-4036-b507-11d43c944d63.PNG)

- I created a class named "Boa" and paste the given code.

  ![image](https://user-images.githubusercontent.com/124245399/233314647-ace46bc4-4a9d-49bf-9acb-f6593849653e.png)

- I created a JUnit Test case in Eclipse named "BoaTest".

  ![image](https://user-images.githubusercontent.com/124245399/233315845-89d69bc6-fea6-4e7d-a765-d8c16251181a.png)
  
- In test method stubs i selected both isHealthy() and fisrtIncage(int).

  ![image](https://user-images.githubusercontent.com/124245399/233317177-4f784b1c-a1bd-49b2-9e82-8d642ff6e389.png)

<h2> Creating test case for Boa class </h2>

```
public class BoaTest {

  @Test
  public void testFitsInCageWithLargerCage() {
    Boa boa = new Boa("Lucy", 5, "rats");
    assertTrue(boa.fitsInCage(10));
  }

  @Test
  public void testIsHealthyWithoutFavoriteFood() {
    Boa boa = new Boa("Sally", 8, "mice");
    assertFalse(boa.isHealthy());
  }

  @Test
  public void testFitsInCageWithExactLength() {
    Boa boa = new Boa("Charlie", 6, "chicken");
    assertTrue(boa.fitsInCage(6));
  }
  
  @Test
  public void testIsHealthyWithFavoriteFood() {
    Boa boa = new Boa("Bob", 10, "granola bars");
    assertTrue(boa.isHealthy());
  }
  
  @Test
  public void testFitsInCageWithSmallerCage() {
    Boa boa = new Boa("Frank", 4, "eggs");
    assertFalse(boa.fitsInCage(3));
  }
}
```
- The isHealthy() method is tested in the aforementioned test cases using a Boa instance both with and without its favourite food. A Boa instance whose length exactly matches the cage length, a Boa instance whose length is less than the cage length, and a Boa instance whose length is greater than the cage length are all used to test the fitsInCage(int) method.

<h2> Boa class with setup() method </h2>

 ```
 public class BoaTest {

  private Boa jen;
  private Boa ken;

  @Before
  public void setUp() throws Exception {
    jen = new Boa("Jennifer", 2, "grapes");
    ken = new Boa("Kenneth", 3, "granola bars");
  }

  // add additional test methods here
}
```
- As a result of this change, the setUp() method now creates the jen and ken Boa objects, which can be utilised in test procedures. The @Before annotation makes sure that the setUp() method is called before each test method is executed, ensuring that all of the test methods in the class may access the jen and ken objects.

<h2> Adding new method and test method in Boa class </h2>

- below is an updated version of the Boa class with the lengthInInches() method added:
```
public class Boa {
  private String name;
  private int length; // the length of the boa, in feet
  private String favoriteFood;

  public Boa (String name, int length, String favoriteFood){
    this.name = name;
    this.length = length;
    this.favoriteFood = favoriteFood;
  }

  // returns true if this boa constrictor is healthy
  public boolean isHealthy(){
    return this.favoriteFood.equals("granola bars");
  }

  // returns true if the length of this boa constrictor is
  // less than the given cage length
  public boolean fitsInCage(int cageLength){
    return this.length < cageLength;
  }

  // produces the length of the Boa in inches
  public int lengthInInches(){
    return this.length * 12;
  }
}
```


- here's a new test method testLengthInInches() added to the BoaTest class:
```
public class BoaTest {
  private Boa jen;
  private Boa ken;

  @Before
  public void setUp() throws Exception {
    jen = new Boa("Jennifer", 2, "grapes");
    ken = new Boa("Kenneth", 3, "granola bars");
  }

  @Test
  public void testLengthInInches() {
    assertEquals(24, jen.lengthInInches());
    assertEquals(36, ken.lengthInInches());
  }
}
```
- By invoking the lengthInInches() method on two Boa objects (jen and ken) created in the setUp() method and confirming that the returned values are accurate using the assertEquals() method, the testLengthInInches() function evaluates the lengthInInches() method of the Boa class. This method should be executed as a JUnit test, according to the @Test annotation.
The JUnit window should show a green bar after the tests have been run, indicating that each test has been passed.

 
