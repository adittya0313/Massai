# Massai
class Item {
    constructor(id, name, quantity, price) {
        this.id = id;
        this.name = name;
        this.quantity = quantity;
        this.price = price;
    }
}

// Inventory Management Functions
// Add Item
function addItem(inventory, item) {
    inventory.push(item);
}

// Update Item
function updateItem(inventory, id, newDetails) {
    const item = inventory.find(item => item.id === id);
    if (item) {
        Object.assign(item, newDetails);
    } else {
        console.log(`Item with id ${id} not found.`);
    }
}

// Delete Item
function deleteItem(inventory, id) {
    const index = inventory.findIndex(item => item.id === id);
    if (index !== -1) {
        inventory.splice(index, 1);
    } else {
        console.log(`Item with id ${id} not found.`);
    }
}

// Get Item
function getItem(inventory, id) {
    return inventory.find(item => item.id === id);
}

// Print Inventory
function printInventory(inventory) {
    console.log('Inventory:');
    inventory.forEach(item => {
        console.log(`ID: ${item.id}, Name: ${item.name}, Quantity: ${item.quantity}, Price: ${item.price}`);
    });
}

// Example Usage
const inventory = [];

// Adding items
addItem(inventory, new Item(1, 'Laptop', 10, 999.99));
addItem(inventory, new Item(2, 'Mouse', 50, 25.99));

// Updating an item
updateItem(inventory, 1, { quantity: 8, price: 899.99 });

// Getting an item
const item = getItem(inventory, 2);
console.log('Retrieved Item:', item);

// Deleting an item
deleteItem(inventory, 2);

// Printing inventory
printInventory(inventory);
