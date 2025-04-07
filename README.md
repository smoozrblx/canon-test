# Description
This is a repository for *Technical Test*.

# Tech Stack
The website is developed with the following technological stack:<br>
- Back-end: [Python 3.11/Django 5.0.10](https://www.djangoproject.com/).<br>
- Front-end: [VueJs 3.3.4](https://vuejs.org/).<br>
- API Framework: [Django Rest Framework 3.15.2](https://www.django-rest-framework.org/)<br>
<br>

### Objective
The goal of this test is to evaluate your ability to integrate a frontend Vue.js application with a Django backend via an API.

### Tasks
- Create a simple UI to manage `Product` items.
- The UI should allow:
  - Listing all products.
  - Creating a new product.
  - Updating an existing product.
  - Deleting a product.
- Use the enpoints to interact with the Django API.
- Implement form validation for product creation and update.
- Display error messages in case of failed API calls.

## API
- Base URL: https://canontestexercise.azurewebsites.net/api/v1/

### Model Product (see the api options for more informations)
- "id": {
   - "type": "integer",
   - "required": false,
   - "read_only": true,
   - "label": "Id"
},
- "product_code": {
   - "type": "string",
   - "required": true,
   - "read_only": false,
   - "label": "Code produit",
   - "max_length": 8
},
- "product_status": {
   - "type": "string",
   - "required": true,
   - "read_only": false,
   - "label": "Statut du produit",
   - "max_length": 50
},
- "product_name": {
   - "type": "string",
   - "required": true,
   - "read_only": false,
   - "label": "Nom du produit",
   - "max_length": 100
},
- "price": {
   - "type": "decimal",
   - "required": true,
   - "read_only": false,
   - "label": "Prix",
   - "max_digits": 10,
   - "decimal_places": 2
},
- "weight": {
   - "type": "float",
   - "required": false,
   - "read_only": false,
   - "label": "Poids (kg)"
},
- "release_date": {
   - "type": "date",
   - "required": true,
   - "read_only": false,
   - "label": "Date de sortie"
},
- "is_available": {
   - "type": "boolean",
   - "required": false,
   - "read_only": false,
   - "label": "Disponible ?"
},
- "meta_created_date": {
   - "type": "datetime",
   - "required": false,
   - "read_only": true,
   - "label": "Date d'insertion"
},
- "meta_entered_by": {
   - "type": "field",
   - "required": false,
   - "read_only": false,
   - "label": "Créé Par"
}

### Note
- `product_status` must be one of theses values : 
  - EN VENTE
  - NOUVEAUTÉ
  - EMBARGO
  - FIN DE VIE
  - OBSOLETE

### Evaluation Criteria
- Code quality and structure.
- Ability to follow best practices in Vue.js.
- UI/UX simplicity and effectiveness.
- Handling of API errors and edge cases.


