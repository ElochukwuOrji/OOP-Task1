# Online Food Ordering System

## Description
This system allows customers to browse restaurant menus, place orders, and provide feedback. Restaurants can manage their menu items and order statuses.

## UML Diagram
The UML class diagram can be found in the (https://lucid.app/lucidchart/11f1e990-8a12-441d-8847-554b3d4874d7/edit?viewport_loc=-596%2C-254%2C2220%2C1082%2C-cQKF1MZmMB4&invitationId=inv_357d00b4-d168-4c22-9f61-d6d17a507ca4).

## Code Implementation
The source code are

// Define the Restaurant class

class Restaurant {

  // Static properties
  
  static totalRestaurants = 0;

  // Constructor for Restaurant instances
  
  constructor(restaurantId, name) {
  
    this.restaurantId = restaurantId; // Unique ID for the restaurant
    
    this.name = name; // Restaurant name
    
    Restaurant.totalRestaurants++; // Increment total restaurants
    
    this.menu = []; // Initialize menu
  
  }

  // Method to add a menu item
  
  addMenuItem(item) {
  
    this.menu.push(item);
    
    console.log(`Menu item ${item} added to ${this.name}.`);
  
  }

  // Method to remove a menu item
  
  removeMenuItem(item) {
  
    const index = this.menu.indexOf(item);
    
    if (index > -1) {
    
      this.menu.splice(index, 1);
      
      console.log(`Menu item ${item} removed from ${this.name}.`);
    
    } else {
    
      console.log(`Menu item ${item} not found in ${this.name}.`);
    
    }
  
  }

}

// Define the Customer class

class Customer {

  // Static property
  
  static totalCustomers = 0;

  // Constructor for Customer instances

  constructor(customerId, name) {
  
    this.customerId = customerId; // Unique ID for the customer
    
    this.name = name; // Customer name
    
    Customer.totalCustomers++; // Increment total customers
    
    this.orderHistory = []; // Initialize order history
  
  }

  // Method to place an order
  
  placeOrder(order) {
  
    this.orderHistory.push(order);
    
    console.log(`${this.name} has placed an order: ${order}.`);
  
  }

  // Method to view order history
  
  viewOrderHistory() {
  
    console.log(`${this.name}'s Order History: ${this.orderHistory.join(', ')}`);
  
  }

}

// Example Usage

const restaurant1 = new Restaurant("R001", "Pasta Palace");

const customer1 = new Customer("C001", "Alice Smith");

// Adding menu items to the restaurant

restaurant1.addMenuItem("Spaghetti");

restaurant1.addMenuItem("Fettuccine");

// Customer actions

customer1.placeOrder("Spaghetti");

customer1.viewOrderHistory(); 

## Screenshots

Screenshots of the code execution is

Menu item Spaghetti added to Pasta Palace.

Menu item Fettuccine added to Pasta Palace.

Alice Smith has placed an order: Spaghetti.

Alice Smith's Order History: Spaghetti
