# Example of manual test cases for testing https://www.saucedemo.com/


## Test 01 - The purchased item is displayed in the cart

**📃 Description:** Verify the added product is displayed in the cart

**🏷️ Tags:** Smoke, Positive

**🗝️ Preconditions:**
the Cart is empty

**👣 Steps:**
- User login to the system
- Select the ‘All Items’ page
- Select the ‘Sauce Labs Backpack’ item
- Click the ‘Add to Card’ button
- Click the bucket button in the upper right corner
  
**💡 Expected Results:**
Verify that the ‘Sauce Labs Backpack’ item displayed in the cart


## Test 02 - The purchased item can be removed from the cart

**📃 Description:** Verify the added product can be removed from the cart

**🏷️ Tags:** Smoke, Positive

**🗝️ Preconditions:**
the Cart is empty

**👣 Steps:**
- User login to the system
- Select the ‘All Items’ page
- Select the ‘Sauce Labs Bike Light’ item
- Click the ‘Add to Card’ button
- Click the bucket button in the upper right corner
- On the ‘Your Cart’ page click the ‘Remove’ button 

**💡 Expected Results:**
- Verify that the ‘Sauce Labs Bike Light’ item was removed from the card
- Verify the cart is empty


##  Test 03 - The purchased item can be removed from the main page

**📃 Description:** Verify the added product can be removed from the ‘All Items’ page

**🏷️ Tags:** Smoke, Positive

**🗝️ Preconditions:**
the Cart is empty

**👣 Steps:**
- User login to the system
- Select the ‘All Items’ page
- Select the ‘Sauce Labs Bike Light’ item
- Click the ‘Add to Card’ button
- On the ‘Sauce Labs Bike Light’ item ‘Add to Card’ button was changed to the ‘Removed’
- On the ‘Sauce Labs Bike Light’ item click the ‘Remove’ button


**💡 Expected Results:**
- Verify that the ‘Sauce Labs Bike Light’ item was removed from the card
- Verify the cart is empty
- On the ‘Sauce Labs Bike Light’ item button ‘Removed’ was changed to the ‘Removed’ ‘Add to Card’



## Test 04 - Purchase completed

**📃 Description:** Verify the order was completed

**🏷️ Tags:** Smoke, Positive

**🗝️ Preconditions:**
the Cart is empty

**👣 Steps:**
- User login to the system
- Select the ‘All Items’ page
- Select the ‘Sauce Labs Bike Light’ item
- Click the ‘Add to Card’ button
- Click the bucket button in the upper right corner
- On the ‘Your Cart’ page click the ‘Checkout’ button
- On the ‘Your Information’ page fills in the valid data in the fields
| First Name      | Olk   |
| Last Name       | Olk   |
| Zip/Postal Code | 12300 |
- Clicks the ‘Continue’ button
- On the ‘Overview’ page click the ‘Finish’ button


**💡 Expected Results:**
- Verify the message about successful purchase ‘Thank you for your order!‘ is displayed
- Verify that the ‘Sauce Labs Bike Light’ item was removed from the card
- Verify the cart is empty
