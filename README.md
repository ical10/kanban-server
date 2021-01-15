# kanban-server
This webapp helps you create nice organisations with kanban board.

Below are the list of the API calls.

**Show Tasks**
----

* **URL**
  /tasks

* **Method:** 
  `GET`

*  **URL Params**

    None

* **Data Params**

    None

* **Success Response:**
  
    * **Code:** 200 <br />
    **Content:** `[
    {
        "id": 11,
        "title": "define models",
        "category": "Completed",
        "description": "define proper tables of each model",
        "createdAt": "2021-01-15T10:34:52.387Z",
        "updatedAt": "2021-01-15T10:34:52.387Z",
        "UserId": 13
    },
    {
        "id": 12,
        "title": "create a plan",
        "category": "Todo",
        "description": "define your plan to build an app",
        "createdAt": "2021-01-15T10:34:52.387Z",
        "updatedAt": "2021-01-15T10:34:52.387Z",
        "UserId": 14
    },
    {
        "id": 13,
        "title": "learn a framework",
        "category": "Doing",
        "description": "using Vue.js for front-end",
        "createdAt": "2021-01-15T10:34:52.387Z",
        "updatedAt": "2021-01-15T10:34:52.387Z",
        "UserId": 12
    },
    {
        "id": 14,
        "title": "testing app",
        "category": "Todo",
        "description": "validations and user testing",
        "createdAt": "2021-01-15T10:34:52.387Z",
        "updatedAt": "2021-01-15T10:34:52.387Z",
        "UserId": 13
    },
    {
        "id": 15,
        "title": "design mockup",
        "category": "Completed",
        "description": "go to dribbble",
        "createdAt": "2021-01-15T10:34:52.387Z",
        "updatedAt": "2021-01-15T10:34:52.387Z",
        "UserId": 14
    },
    {
        "id": 16,
        "title": "join a seminar",
        "category": "Todo",
        "description": "go to webdevfest",
        "createdAt": "2021-01-15T10:34:52.387Z",
        "updatedAt": "2021-01-15T10:34:52.387Z",
        "UserId": 12
    },
    {
        "id": 17,
        "title": "prepare seeders",
        "category": "Doing",
        "description": "search google for dummy data",
        "createdAt": "2021-01-15T10:34:52.387Z",
        "updatedAt": "2021-01-15T10:34:52.387Z",
        "UserId": 13
    },
    {
        "id": 18,
        "title": "amplify your skills",
        "category": "Backlog",
        "description": "build your rank on edabit",
        "createdAt": "2021-01-15T10:34:52.387Z",
        "updatedAt": "2021-01-15T10:34:52.387Z",
        "UserId": 14
    }
    ]`
 
* **Error Response:**

  * **Code:** 500 Internal Server Error <br />
    **Content:** `{ message: "Internal server error." }`

* **Sample Call:**

    `localhost:5001/tasks`

* **Notes:**

    None

**Create Task**
----

* **URL**
  /tasks

* **Method:** 
  `POST`

*  **URL Params**

    None

* **Data Params**
    
    **Content:** `{ 
    title: "add more associations",
    description: "creating more association with Organisations",
    }
    `

* **Success Response:**
  
    * **Code:** 200 OK <br />
    **Content:** `{
    "createdTask": {
        "id": 28,
        "title": "add more associations",
        "description": "creating more association with Organisations",
        "category": null,
        "UserId": 14,
        "updatedAt": "2021-01-15T16:59:04.902Z",
        "createdAt": "2021-01-15T16:59:04.902Z"
    }
    }
    `

* **Error Response:**

  * **Code:** 500 Internal Server Error <br />
    **Content:** `{ message: "Internal server error." }`

* **Sample Call:**

    `localhost:5001/tasks`

* **Notes:**

    None

**Show Task by id**
----

* **URL**
  /tasks/:id

* **Method:** 
  `GET`

*  **URL Params**

    `id=[integer]`

* **Data Params**
    
    None

* **Success Response:**
  
    * **Code:** 200 OK <br />
    **Content:** `{
    "id": 12,
    "title": "create a plan",
    "category": "Todo",
    "description": "define your plan to build an app",
    "createdAt": "2021-01-15T10:34:52.387Z",
    "updatedAt": "2021-01-15T10:34:52.387Z",
    "UserId": 14
    }`

* **Error Response:**

  * **Code:** 404 Not Found <br />
    **Content:** `{ message: "Error: not found."}`
    
    OR

  * **Code:** 500 Internal Server Error <br />
    **Content:** `{message: "Internal server error."}`


* **Sample Call:**

    `localhost:5001/tasks/1`

* **Notes:**

    None

**Update Task by id**
----

* **URL**
  /tasks/:id

* **Method:** 
  `PUT`

*  **URL Params**

    `id=[integer]`

* **Data Params**
    
    **Content:** `{ 
    title: "learn Vue-cli",
    description: "using Vue-cli for faster development"
    }
    `

* **Success Response:**
  
    * **Code:** 200 OK <br />
    **Content:** `{
    id: 1,
    title: "learn Vue-cli",
    description: "using Vue-cli for faster development",
    }
    `

* **Error Response:**

  * **Code:** 401 Not Authorized <br />
    **Content:** `{message: No access"}`

    OR

  * **Code:** 500 Internal Server Error <br />
    **Content:** `{message: "Internal server error."}`


* **Sample Call:**

    `localhost:5001/tasks/1`

* **Notes:**

    None

**Update a field in Task by id**
----

* **URL**
  /tasks/:id

* **Method:** 
  `PATCH`

*  **URL Params**

    `id=[integer]`

* **Data Params**
    
    **Content:** `{ 
    category: 'Todo'
    }
    `

* **Success Response:**
  
    * **Code:** 200 OK <br />
    **Content:** `{
    category: "Todo"
    }
    `

* **Error Response:**

  * **Code:** 401 Not Authorized <br />
    **Content:** `{message: No access"}`
    
    OR

  * **Code:** 500 Internal Server Error <br />
    **Content:** `{message: "Internal server error."}`


* **Sample Call:**

    `localhost:5001/tasks/1`

* **Notes:**

    None


**Delete Task by id**
----

* **URL**
  /tasks/:id

* **Method:** 
  `DELETE`

*  **URL Params**

    `id=[integer]`

* **Data Params**
    
    None

* **Success Response:**
  
    * **Code:** 200 OK <br />
    **Content:** `{
    message: "Task successfully deleted."
    }
    `

* **Error Response:**

  * **Code:** 500 Internal Server Error <br />
    **Content:** `{message: "Internal server error."}`


* **Sample Call:**

    `localhost:5001/tasks/1`

* **Notes:**

    None

