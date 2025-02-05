```gherkin
@Positive
## Feature: Login user
Scenario: Successful login
  Given the user is on the login page
  When the user enters the correct email and password:
    | Username               | Password     |
    | standard_user          | secret_sauce |
    | locked_out_user        | secret_sauce |
    | problem_user           | secret_sauce |
    | performance_glitch_user| secret_sauce |
    | error_user             | secret_sauce |
    | visual_user            | secret_sauce |
  And the user clicks the "Login" button
  Then the user lands on the "All Items" page



@Negative
## Feature: User can’t login to the system
Scenario: Login error with incorrect Password
  Given the user is on the login page
  When the user enters the correct username but the incorrect password:
    | Username               | Password |
    | standard_user          |     1    |
    | locked_out_user        |     1    |
    | problem_user           |     1    |
    | performance_glitch_user|     1    |
    | error_user             |     1    |
    | visual_user            |     1    |
  And the user clicks the "Login" button
  Then the user sees the error message "Epic sadface: Username and password do not match any user in this service"



@Negative
## Feature: User can’t Login to the system
Scenario: Login error with incorrect username
  Given the user is on the login page
  When the user enters an incorrect username and a correct password:
    | Username  | Password     |
    | user      | secret_sauce |
  And the user clicks the "Login" button
  Then the error message "Epic sadface: Username and password do not match any user in this service" is displayed



@Positive
## Feature: Verify whether the added product is displayed in the cart
Scenario: Buy a "Sauce Labs Backpack" from the "All Items" page
  Given the user is on the "All Items" page
  And the cart is empty
  When the user clicks the "Add to cart" button
  And the user clicks the bucket button in the upper right corner
  Then the "Your Cart" page is opened
  And the cart contains the item "Sauce Labs Backpack"



@Negative
## Feature: Verify that an order cannot be placed with an empty cart
Scenario: Place an order without adding the product to the cart
  Given the user is on the "All Items" page
  And the cart is empty
  When the user clicks the bucket button in the upper right corner
  Then the "Your Cart" page is opened
  And the cart has no items
  When the user clicks on the "Checkout" button
  Then  the "Your Information" page is opened
  When the user fills in the valid data in the fields:
    | First Name      | Olk   |
    | Last Name       | Olk   |
    | Zip/Postal Code | 12300 |  
  And the user clicks the "Continue" button
  Then the "Overview" page is opened
  And the system displays a message that the cart is empty
  And the "Finish" button should be disabled
```