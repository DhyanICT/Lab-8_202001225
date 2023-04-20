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
  public void testIsHealthyWithFavoriteFood() {
    Boa boa = new Boa("Bob", 10, "granola bars");
    assertTrue(boa.isHealthy());
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
  public void testFitsInCageWithLargerCage() {
    Boa boa = new Boa("Lucy", 5, "rats");
    assertTrue(boa.fitsInCage(10));
  }

  @Test
  public void testFitsInCageWithSmallerCage() {
    Boa boa = new Boa("Frank", 4, "eggs");
    assertFalse(boa.fitsInCage(3));
  }
}
```
