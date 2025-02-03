
**BDD Scenarios for**  
[[https://coffee-cart.app/](https://www.saucedemo.com/inventory.html)]([https://coffee-cart.app/](https://www.saucedemo.com/inventory.html))


@Feature: Login User

@Positive Scenario: Successful Login
Given
- Користувач знаходиться на сторінці входу
#### When
- Він вводить правильний email і пароль

| Username              | Password      |
|----------------------|--------------|
| standard_user        | secret_sauce |
| locked_out_user      | secret_sauce |
| problem_user        | secret_sauce |
| performance_glitch_user | secret_sauce |
| error_user          | secret_sauce |
| visual_user         | secret_sauce |

- Натискає кнопку `Login`
#### Then
- Він потрапляє на сторінку `All Items`

---

### Negative Scenario: Login Failure with Incorrect Password
#### Given
- Користувач знаходиться на сторінці входу
#### When
- Він вводить правильний email, але неправильний пароль

| Username              | Password |
|----------------------|----------|
| standard_user        | 1        |
| locked_out_user      | 1        |
| problem_user        | 1        |
| performance_glitch_user | 1        |
| error_user          | 1        |
| visual_user         | 1        |

- Натискає кнопку `Login`
#### Then
- Він бачить повідомлення про помилку:  
  `Epic sadface: Username and password do not match any user in this service`

---

### Negative Scenario: Login Failure with Incorrect Username
#### Given
- Користувач знаходиться на сторінці входу
#### When
- Він вводить неправильний email, але правильний пароль

| Username | Password      |
|----------|--------------|
| user     | secret_sauce |

- Натискає кнопку `Login`
#### Then
- Він бачить повідомлення про помилку:  
  `Epic sadface: Username and password do not match any user in this service`

---

## Feature: Verify Product Display in Cart

### Positive Scenario: Add 'Sauce Labs Backpack' to Cart
#### Given
- Користувач знаходиться на сторінці `All Items`
- Кошик порожній
#### When
- Користувач натискає кнопку `Add to cart`
- Користувач натискає кнопку кошика у верхньому правому куті
#### Then
- Відкривається сторінка `Your Cart`
- В кошику відображається товар `Sauce Labs Backpack`

---

## Feature: Prevent Checkout with Empty Cart

### Negative Scenario: Attempt to Place an Order with an Empty Cart
#### Given
- Користувач знаходиться на сторінці `All Items`
- Кошик порожній
#### When
- Користувач натискає кнопку кошика у верхньому правому куті
- Відкривається сторінка `Your Cart`
- У кошику немає товарів
- Користувач натискає кнопку `Checkout`
- Відкривається сторінка `Your Information`
- Користувач заповнює всі поля валідними даними:

| First Name | Last Name | Zip/Postal Code |
|------------|-----------|-----------------|
| Olk        | Olk       | 12300           |

- Користувач натискає кнопку `Continue`
#### Then
- Відкривається сторінка `Overview`
- Відображається повідомлення, що кошик порожній
- Кнопка `Finish` неактивна
