# Canon Product Management UI

## Description
This is a front-end UI for managing `Product` items, built with **Vue.js** and connected to a provided **Django back-end**. The UI includes features for viewing, filtering, sorting, creating, updating, and deleting products.

## Features Implemented
### 1. **Displaying the List of Products**
   - The UI fetches a list of all products from the backend via an API call to the `/product/` endpoint. The products are displayed in a table format with pagination for easier navigation.

### 2. **Filtering Products**
   - Users can filter products by their **status** (e.g., `EN VENTE`, `NOUVEAUTÉ`, `EMBARGO`, `FIN DE VIE`, `OBSOLETE`). A dropdown filter is provided, which sends the selected filter as a query parameter to the API request.

### 3. **Sorting by Product Name and Product Code**
   - I implemented sorting functionality for the product list, where users can click buttons to sort by **name** or **product code**.
   - The sorting is applied by appending a query parameter (`?ordering=product_name` or `?ordering=-product_code`) to the API request.

### 4. **Searching for Products**
   - A search bar is available for users to search products by name or product code. The search query is sent to the API endpoint as a query parameter.
   - To improve performance, I implemented **debouncing** on the search input to avoid making multiple API calls while typing.

### 5. **Creating a New Product**
   - A form is provided to create new products, with fields like product name, product code, and product status.
   - The form validates input to ensure all required fields are filled and that the product status is one of the predefined options.
   - Upon successful form submission, a POST request is made to the `/product/` endpoint to create a new product.

### 6. **Updating an Existing Product**
   - An edit button next to each product allows users to modify existing product details.
   - Clicking the edit button opens a modal pre-filled with the product data, where the user can change the details and submit the updated data.
   - A PUT request is sent to the `/product/{id}/` endpoint to update the product.

### 7. **Deleting a Product**
   - A delete button is provided for each product, allowing users to remove products from the list.
   - Deleting a product triggers a DELETE request to the `/product/{id}/` endpoint.

## API Integration
The front-end communicates with the API at the following base URL:  
**`https://canontestexercise.azurewebsites.net/api/v1/`**

### Product Status Values
When creating or updating products, the `product_status` must be one of the following values:
- `EN VENTE`
- `NOUVEAUTÉ`
- `EMBARGO`
- `FIN DE VIE`
- `OBSOLETE`

## Issues Encountered
### 1. **CORS Issues in Development**
   - While developing locally, I encountered **CORS** (Cross-Origin Resource Sharing) issues when attempting to make API requests from `localhost` to the provided API.
   - To resolve this, you can use a **proxy** or install a browser extension like **CORS Unblock** to bypass these restrictions during development.

### 2. **500 Internal Server Error on Search**
   - When making a search request to the `/product/` endpoint with a query parameter, I received a `500 Internal Server Error`.
   - To understand the error better, I checked the backend call stack, which revealed issues related to how the search query is processed. For more information, here is an example call taht fails: **`https://canontestexercise.azurewebsites.net/api/v1/product/?search=test`**.

### 3. **Other Functionalities**
   - The remaining features, such as creating, updating, deleting, and sorting products, work as intended without any issues.
   - Validation is in place for the product creation and update forms to ensure that all required fields are properly filled.

## How to Run the Application

### 1. **Clone the Repository**
   - Clone this repository to your local machine using:
     ```
     git clone <repository-url>
     ```

### 2. **Run app.html**
   - Open `app.html` using a web server like Live Server.
