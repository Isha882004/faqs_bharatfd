# FAQ Management System

A Node.js/Express-based FAQ management system with multilingual support, rich text editing, and a REST API. The system provides automatic translation into Hindi and Bengali, offering a seamless experience for managing FAQ content across multiple languages.
### **Features**
- ✅ **FAQ Creation & Management** Create and manage FAQs with rich text editing.
- ✅ **Automatic Translation**  Automatic translation of FAQs to Hindi and Bengali using Google Translate API.
- ✅ **REST API** Provides programmatic access to FAQ data, allowing for easy integration.
- ✅ **Admin Interface** Preview translations and manage FAQ content via the admin interface.
- ✅ **Real-Time Translation Status Indicators**.
- ✅ **Caching** with Redis for improved performance.
- ✅ **Test Coverage** to ensure reliability.
- ✅ **Dockerized Deployment** for easy setup and portability.

### **Tech Stack**
- **Node.js**: JavaScript runtime used for building the API and backend logic.
- **Express.js**: Web framework for building the API and managing routing.
- **MongoDB**: NoSQL database used for storing FAQ data.
- **Redis**: Caching system for improved performance and faster translation access.
- **Google Translate API**: Automatic translation to support multilingual FAQs.
- **Mocha & Chai**: Testing frameworks for unit and integration testing.
- **Docker**: Containerization for simplified deployment.
---

## 📂 Project Structure
```plaintext
faq-backend/
├── config/
│   ├── db.js               # Database connection
│   ├── redis.js            # Redis configuration
├── controllers/
│   ├── faqController.js    # FAQ handling logic
├── middlewares/
│   ├── authMiddleware.js   # Authentication middleware (if applicable)
──   models/
│   ├── faq.js              # FAQ schema
├── routes/
│   ├── faqRoutes.js        # API routes for FAQ
├── service/
│   ├── translationService.js # Google Translate integration
├── utils/
│   ├── cache.js            # Cache logic (Redis)
│   ├── errorHandler.js     # Error handling middleware
├── app.js                  # Express app configuration
├── tests/
│   ├── faq.test.js         # Unit tests for FAQ API
├── .env                    # Environment variables (sensitive data)
├── .gitignore              # Git ignore file
├── Dockerfile              # Dockerfile for containerization
├── package.json            # Dependencies and scripts
└── README.md               # Documentation
└── server.js               # Entry point for the server

---

## 🛠️ Installation & Setup

Follow these steps to set up the project on your local machine.

### **Prerequisites**
Ensure you have the following installed:
- **Node.js & npm**: Download and install from [here](https://nodejs.org/)
- **Redis** (for caching): Install Redis from [here](https://redis.io/download)

### **Steps to Run Locally**

1. **Clone the repository**  
   First, clone the repository to your local machine:
   ```sh
   git clone https://github.com/your-repo/faqs_bharatfd.git
cd faqs_bharatfd

   ```

2. **Install dependencies**  
   Install the required dependencies:
   ```sh
   npm install
   ```

3. **Set up environment variables**  
   Create a `.env` file in the root directory of the project.  
   Add necessary configurations such as database connection, Redis URL, and API keys. Example:
   ```env
   MONGO_URI=mongodb://127.0.0.1:27017/faqs
   REDIS_URL=redis://localhost:6379
   GOOGLE_TRANSLATE_API_KEY=your-api-key-here
    ```
4. **set up redis**  
   Make sure Redis is installed and running. The app will connect to Redis for caching.  
   You can start Redis by running:
   ```sh
   redis-server
   ```

5. **Start the application**  
   After setting up the environment, you can start the application:
   ```sh
   npm start
   ```
   The app should now be running locally on `http://localhost:8000`.

6. **Run tests**  
   If you want to run the tests to ensure everything is working correctly, use:
   ```sh
   npm test
   ```

---

## 📡 API Endpoints
### **Base URL**
```
http://localhost:8000/api/faqs/
```

### **Endpoints**

#### **Fetch FAQs**
```sh
GET /api/faqs/           # Fetch FAQs in English (default)
GET /api/faqs/?lang=hi   # Fetch FAQs in Hindi
GET /api/faqs/?lang=bn   # Fetch FAQs in Bengali
```

#### **Create a FAQ**
```sh
POST /api/faqs/
Content-Type: application/json
{
question "what is django?"
answer "<p>django is a high-level python web framework..<p>"
question_hi"Django क्या है?"
createdAt 2025-02-01T15:43:20.537+00:00
updatedAt 2025-02-01T15:43:20.537+00:00
__v: 0
}
```

#### **Update a FAQ**
```sh
PUT /api/faqs/:id
Content-Type: application/json
{
    "answer": "Updated answer for Django."
}
```

#### **Delete a FAQ**
```sh
DELETE /api/faqs/:id
```
---
```
