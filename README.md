
---

### Project Overview:
This is a basic **RESTful API** designed for managing support tickets. It provides the essential functionality needed to perform Create, Read, Update, and Delete (CRUD) operations on tickets, built using **Node.js** and **MongoDB**.

#### Key Features:
- **Create Ticket**: Submit a new ticket for tracking.
- **Read Tickets**: Retrieve all tickets or a specific ticket by ID.
- **Update Ticket**: Modify details of an existing ticket.
- **Delete Ticket**: Remove a ticket from the system.

---

### Technologies Used:
- **Node.js**: The server-side JavaScript runtime.
- **Express.js**: A web framework to simplify API development.
- **MongoDB**: A NoSQL database used for storing ticket data.
- **Mongoose**: An ODM (Object Data Modeling) library for MongoDB to model and manage data.
- **Postman** (optional): A tool used for API testing.

---

### Setup Instructions:

#### Prerequisites:
- **Node.js** and **npm** installed locally.
- Access to **MongoDB**, either through a local instance or a MongoDB Atlas cluster.

#### Steps to Set Up Locally:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/ticket-management-system.git
   cd ticket-management-system
   ```

2. **Install project dependencies**:
   ```bash
   npm install
   ```

3. **Configure environment variables**:
   - Create a `.env` file at the root of the project with the following values:
     ```env
     PORT=3000
     MONGO_DB_URI=mongodb+srv://priyansh:priyansh@cluster0.wewnn.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0
     ```

4. **Start the server**:
   ```bash
   npm start
   ```

---

### API Documentation:

#### 1. Base URL
- The API runs at `http://localhost:3000/api/tickets`.

#### 2. Available Endpoints:

1. **Create a Ticket**

   - **Method**: `POST`
   - **Endpoint**: `/api/tickets`
   - **Request Body**:
     ```json
     {
       "title": "Ticket Title",
       "description": "Detailed description of the issue.",
       "status": "Open",
       "priority": "Medium"
     }
     ```
   - **Response**:
     ```json
     {
       "_id": "66f057e8f88e753b93f515b1",
       "title": "Ticket Title",
       "description": "Detailed description of the issue.",
       "status": "Open",
       "priority": "Medium",
       "createdBy": "User",
       "assignedTo": null,
       "createdAt": "2024-09-22T17:46:16.922Z",
       "updatedAt": "2024-09-22T17:46:16.922Z",
       "__v": 0
     }
     ```

2. **Retrieve All Tickets**

   - **Method**: `GET`
   - **Endpoint**: `/api/tickets`
   - **Response**:
     ```json
     [
       {
         "_id": "66f057e8f88e753b93f515b1",
         "title": "Ticket Title",
         "description": "Detailed description of the issue.",
         "status": "Open",
         "priority": "Medium",
         "createdBy": "User",
         "assignedTo": null,
         "createdAt": "2024-09-22T17:46:16.922Z",
         "updatedAt": "2024-09-22T17:46:16.922Z",
         "__v": 0
       }
     ]
     ```

3. **Retrieve a Single Ticket**

   - **Method**: `GET`
   - **Endpoint**: `/api/tickets/:id`
   - **Response**:
     ```json
     {
       "_id": "66f057e8f88e753b93f515b1",
       "title": "Ticket Title",
       "description": "Detailed description of the issue.",
       "status": "Open",
       "priority": "Medium",
       "createdBy": "User",
       "assignedTo": null,
       "createdAt": "2024-09-22T17:46:16.922Z",
       "updatedAt": "2024-09-22T17:46:16.922Z",
       "__v": 0
     }
     ```

4. **Update a Ticket**

   - **Method**: `PUT`
   - **Endpoint**: `/api/tickets/:id`
   - **Request Body**:
     ```json
     {
       "title": "Updated Title",
       "description": "Updated description of the issue.",
       "status": "Closed",
       "priority": "High"
     }
     ```
   - **Response**:
     ```json
     {
       "_id": "66f057e8f88e753b93f515b1",
       "title": "Updated Title",
       "description": "Updated description of the issue.",
       "status": "Closed",
       "priority": "High",
       "createdBy": "User",
       "assignedTo": null,
       "createdAt": "2024-09-22T17:46:16.922Z",
       "updatedAt": "2024-09-22T17:54:11.861Z",
       "__v": 0
     }
     ```

5. **Delete a Ticket**

   - **Method**: `DELETE`
   - **Endpoint**: `/api/tickets/:id`
   - **Response**:
     ```json
     {
       "message": "Ticket successfully deleted."
     }
     ```
     - If the ticket is not found, it will return:
     ```json
     {
       "message": "Ticket not found."
     }
     ```

---