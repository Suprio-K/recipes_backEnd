🍽️ Recipes App – Backend

This is the backend service for the Recipes App, built using Node.js, Express.js, and MongoDB (Mongoose).
It provides a RESTful API to create, read, update, and delete recipes and follows the MVC architecture.

The backend is deployed on Render and uses MongoDB Atlas as the database.

🚀 Live API URL
https://recipes-backend-uyny.onrender.com

🛠 Tech Stack

Node.js

Express.js

MongoDB Atlas

Mongoose

Postman (API testing & documentation)

📁 Project Structure
recipes-backend/
│── controllers/
│   └── recipeController.js
│
│── models/
│   └── Recipe.js
│
│── routes/
│   └── recipeRoutes.js
│
│── config/
│   └── db.js
│
│── app.js
│── server.js
│── package.json
│── .env
│── README.md

⚙️ Environment Variables

Create a .env file in the root directory:

PORT=5000
MONGO_URI=your_mongodb_atlas_connection_string

▶️ Running the Project Locally
1️⃣ Install dependencies
npm install

2️⃣ Start development server
npm run dev


Server will run at:

http://localhost:5000

📌 API Endpoints
1️⃣ Create a Recipe

POST /api/recipes

Request Body (JSON):

{
  "title": "Chicken Biryani",
  "ingredients": ["Rice", "Chicken", "Spices"],
  "instructions": "Cook rice and chicken separately, then mix.",
  "cookingTime": 45
}


Response:

{
  "_id": "65f123abc456",
  "title": "Chicken Biryani",
  "ingredients": ["Rice", "Chicken", "Spices"],
  "instructions": "Cook rice and chicken separately, then mix.",
  "cookingTime": 45,
  "createdAt": "2025-02-09T10:30:00Z"
}

2️⃣ Get All Recipes

GET /api/recipes

Response:

[
  {
    "_id": "65f123abc456",
    "title": "Chicken Biryani",
    "ingredients": ["Rice", "Chicken", "Spices"],
    "instructions": "Cook rice and chicken separately, then mix.",
    "cookingTime": 45
  }
]

3️⃣ Get Recipe By ID

GET /api/recipes/:id

Example:

/api/recipes/65f123abc456


Response:

{
  "_id": "65f123abc456",
  "title": "Chicken Biryani",
  "ingredients": ["Rice", "Chicken", "Spices"],
  "instructions": "Cook rice and chicken separately, then mix.",
  "cookingTime": 45
}

4️⃣ Update a Recipe

PUT /api/recipes/:id

Request Body:

{
  "title": "Veg Biryani",
  "cookingTime": 40
}


Response:

{
  "_id": "65f123abc456",
  "title": "Veg Biryani",
  "ingredients": ["Rice", "Chicken", "Spices"],
  "instructions": "Cook rice and chicken separately, then mix.",
  "cookingTime": 40
}

5️⃣ Delete a Recipe

DELETE /api/recipes/:id

Response:

{
  "message": "Recipe deleted successfully"
}

❗ Error Handling

400 – Validation errors (missing fields)

404 – Recipe not found

500 – Internal server error

Example:

{
  "message": "Recipe validation failed: cookingTime is required"
}

📮 Postman Documentation

All APIs are tested and documented using Postman, including:

Sample requests

Sample responses

Error cases

🌍 Deployment

Backend Hosting: Render

Database: MongoDB Atlas

📌 License

This project is open-source and intended for learning and assessment purposes only.
