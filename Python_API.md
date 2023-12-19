# Python Application Programming Interface (API)
Let's explore some Python API examples that are beginner-friendly. 
These examples will demonstrate how to use APIs (Application Programming Interfaces) to interact with external services or data sources.


### 1. Making a Simple HTTP GET Request
Using the `requests` library to fetch data from a public API.
```python
import requests

response = requests.get('https://jsonplaceholder.typicode.com/posts/1')
print(response.json())
```

### 2. Parsing JSON from an API Response
Handling JSON data returned from an API.
```python
import requests

response = requests.get('https://jsonplaceholder.typicode.com/posts/1')
data = response.json()

print(data['title'])
```

### 3. Sending Data with POST Request
Using POST to send data to an API.
```python
import requests

payload = {'title': 'foo', 'body': 'bar', 'userId': 1}
response = requests.post('https://jsonplaceholder.typicode.com/posts', data=payload)

print(response.json())
```

### 4. Handling Query Parameters in GET Request
Passing query parameters in a GET request.
```python
import requests

params = {'userId': 1}
response = requests.get('https://jsonplaceholder.typicode.com/posts', params=params)

print(response.json())
```

### 5. Error Handling for API Responses
Error handling for unsuccessful API responses.
```python
import requests

response = requests.get('https://jsonplaceholder.typicode.com/posts/1')

if response.status_code == 200:
    print(response.json())
else:
    print("Failed to retrieve data", response.status_code)
```

### 6. Uploading Files using POST Request
Sending files using the POST method.
```python
import requests

files = {'file': open('example.txt', 'rb')}
response = requests.post('https://httpbin.org/post', files=files)

print(response.json())
```

### 7. Using Headers with Requests
Sending custom headers with a request.
```python
import requests

headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN'}
response = requests.get('https://api.example.com/data', headers=headers)

print(response.json())
```

### 8. Working with RESTful API
Performing CRUD operations with a REST API.
```python
import requests

# Create
response = requests.post('https://jsonplaceholder.typicode.com/posts', data={'title': 'New Post'})

# Read
response = requests.get('https://jsonplaceholder.typicode.com/posts/1')

# Update
response = requests.put('https://jsonplaceholder.typicode.com/posts/1', data={'title': 'Updated Post'})

# Delete
response = requests.delete('https://jsonplaceholder.typicode.com/posts/1')
```

### 9. Using OAuth2 for API Authentication
Handling OAuth2 authentication (simplified example).
```python
import requests

# Assuming you have received the access token after OAuth2 flow
access_token = 'YOUR_ACCESS_TOKEN'
headers = {'Authorization': f'Bearer {access_token}'}
response = requests.get('https://api.example.com/protected_resource', headers=headers)

print(response.json())
```

### 10. Working with Websockets
Using `websocket-client` library for real-time data.
```python
from websocket import create_connection

ws = create_connection("ws://echo.websocket.org")
ws.send("Hello World")
result = ws.recv()
print("Received:", result)
ws.close()
```

These examples cover various aspects of working with APIs in Python. Before running them, ensure that you have the necessary libraries installed (`requests`, `websocket-client`). Also, keep in mind that APIs often require authentication, and you should handle your credentials securely.
