# Supermarket 

## Overview

This Solidity smart contract, named "Supermarket," is designed to manage product quantities in a supermarket setting. It allows an administrator to set and update the stock quantities for different products. Additionally, it provides a mechanism for processing customer orders while ensuring that the requested quantities do not exceed the available stock.

## Smart Contract Details

### State Variables

- `administrator`: The address of the administrator who has the authority to manage product quantities.
- `productSums`: A mapping from product IDs to their respective quantities in stock.

### Constructor

The contract constructor sets the deployer's address as the administrator upon contract creation.

### Modifiers

- `onlyAdministrator`: A modifier that restricts certain functions to be callable only by the administrator.

### Functions

1. **`setProductSum`**
   - **Access:** `external`
   - **Modifier:** `onlyAdministrator`
   - **Purpose:** Allows the administrator to set or update the quantity of a specific product.

2. **`processOrder`**
   - **Access:** `external`
   - **Purpose:** Processes customer orders by reducing the stock quantity of a product. It ensures that the requested quantity is greater than or equal to 20 and does not exceed the available stock.

## Usage

1. **Deployment:**
   - Deploy the smart contract to the Ethereum blockchain. The deployer becomes the administrator.

2. **Setting Product Quantities:**
   - Call the `setProductSum` function to set or update the stock quantities for different products.

   ```solidity
   function setProductSum(uint256 productId, uint256 quantity) external onlyAdministrator {
       // Implementation details
   }
   ```

3. **Processing Orders:**
   - Customers can call the `processOrder` function to place orders, ensuring that the requested quantity is within the available stock limits.

   ```solidity
   function processOrder(uint256 productId, uint256 requestedSum) external {
       // Implementation details
   }
   ```

## Security Considerations

- The `onlyAdministrator` modifier ensures that only the designated administrator can modify product quantities.
- The `processOrder` function includes checks to prevent orders for quantities below 20 and orders exceeding available stock.

## License

This smart contract is released under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

Nitish C T

Pendulct@gmail.com
