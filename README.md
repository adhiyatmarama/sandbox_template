# Fancy-todo API

This is the documentation for using FANCY TODO API. The base url for this API is http://localhost:3002
This API is using email validator API

### 1. Register (If you Already have an account, you can skip this part)

* **URL**
  
  /user/register

* **METHOD**
  
  `GET`

* **REQUEST BODY**
  
  Using JSON

  ```javascript
  {
	"first_name": "Adhiyatma",
	"last_name": "Pramayoga",
	"email": "adhiyatma.pramayoga@gmail.com",
	"password": "secretPassword123"
  }
  ```

* **SUCCESS RESPONSE**
  
  * CODE: 200 
  * Content:
  
    ```javascrip
    {
        "id": 16,
        "first_name": "Adhiyatma",
        "last_name": "Pramayoga",
        "email": "adhiyatma.pramayoga@gmail.com",
        "password": "$2b$08$YfyuqhM0Q7zP2WtF9iIZROufOnsV0s4W5Nr7Wh.Eu9xnjAk5AOZc6",
        "updatedAt": "2020-03-07T08:25:50.208Z",
        "createdAt": "2020-03-07T08:25:50.208Z"
    }
    ```

* **ERROR RESPONSE**
  
  * Empty Requirement (empty request body)
    
    *CODE: 400
    *Content:
        
        ```javascript
        {
            "status": 400,
            "error": [
                {
                    "path": "first_name",
                    "type": "Validation error",
                    "msg": "Please input your name"
                },
                {
                    "path": "password",
                    "type": "Validation error",
                    "msg": "Please input the password"
                }
            ]
        }
        ```

  * Email Validation Error
    
    *CODE: 400
    *Content:

        Wrong format email

        ```javascript
        {
            "status": 400,
            "msg": "Invalid format"
        }
        ```

        Email not found

        ```javascript
        {
        "status": 400,
        "msg": "Email not Found"
        }
        ```

