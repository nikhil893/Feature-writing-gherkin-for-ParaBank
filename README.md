# feature-writing-in-gherkin-for-amazon
Feature writing in Gherkin for Amazon Website

```gherkin
Feature: My First Feature

  @smoke
  Scenario: Open Browser and Navigate
    Given User Opened the Browser
    When User navigated to the app url
    Then User is able to see application landing page

  @search  @smoke
  Scenario: User is able to Search for a Product
    Given User Opened the Browser and User navigated to the App url
    When User search for a new product
    Then Search result for the product is displayed

  @search
  Scenario: User is able to filter the search based on price
    Given User search for a Product as "Laptop"
    When User enters minimum as "20000" and maximum as "50000" in the filter criteria
    Then User is able to see results with price between "20000" and "50000"

  @product_details  @smoke
  Scenario: User is able to see the product details
    Given User searched for the product
    When User click on any product
    Then User is navigated to the new tab and product details are displayed

  @product_details
  Scenario: User is able to select the quantity and add to cart from Product details page
    Given User is on the product details page
    When User selects the product quantity as 2
    And User clicks add to cart on the page on product details page
    Then Product is added to the cart

  @cart  @smoke
  Scenario: User can view his added items in the cart
    Given User has added multiple products in the cart
    When User navigates to the My Cart Page
    Then User is able to see the list of all the added items with correct quantities as well as price totals is correct

  @cart
  Scenario: User can delete the items in the cart
    Given User has added multiple products in the cart
    And User navigates to the My Cart Page
    When User deletes an item from the cart
    Then Item should be delete and should not appear in the cart item list
    And deleted item amount should be removed from the total cart amount

  @cart 
  Scenario: User can reduce the items quantity in the cart
    Given User has added products with multiple quantity in the cart
    And User navigates to the My Cart Page
    When User reduces an item quantity from the cart
    Then Item should be reduced in the quantity
    And reduced item amount should be re-calculated from the total cart amount

  @cart
  Scenario: User can add the items in the cart
    Given User has added single item with single quantity in the cart
    And User navigates to the My Cart Page
    When User increase the product quantity by 1
    Then Product quantity is increased by 1 and cart total should re-calcualte the total amount

  @smoke @e2e
  Scenario: User is able to order single product with single quantity from the app
    Given User is able to login in the app
    And User is able to search for the product and add the product to the cart with quantity as 1
    And User navigates to my cart and clicks on Buy
    And User selects the address
    When User clicks on Place order with delivery option as "CoD"
    Then Order is placed for the user
    And Order details can be seen in order details page

  @smoke @e2e
  Scenario: User is able to order single product with multiple quantity from the app
    Given User is able to login in the app
    And User is able to search for the product and add the product to the cart with quantity as 2
    And User navigates to my cart and clicks on Buy
    And User selects the address
    When User clicks on Place order with delivery option as "CoD"
    Then Order is placed for the user
    And Order details can be seen in order details page

  @smoke @e2e
  Scenario: User is able to order multiple product with single quantity from the app
    Given User is able to login in the app
    And User is able to search for the product "laptop" and add the product to the cart with quantity as 1
    And User is able to search for the product "mobile" and add the product to the cart with quantity as 1
    And User navigates to my cart and clicks on Buy
    And User selects the address
    When User clicks on Place order with delivery option as "CoD"
    Then Order is placed for the user
    And Order details can be seen in order details page

  @smoke @e2e
  Scenario: User is able to order multiple product with multiple quantity from the app
    Given User is able to login in the app
    And User is able to search for the product "laptop" and add the product to the cart with quantity as 2
    And User is able to search for the product "mobile" and add the product to the cart with quantity as 2
    And User navigates to my cart and clicks on Buy
    And User selects the address
    When User clicks on Place order with delivery option as "CoD"
    Then Order is placed for the user
    And Order details can be seen in order details page






```
