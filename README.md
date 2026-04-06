# The-Resume-API
Built a serverless Resume API using AWS Lambda, API Gateway, and DynamoDB. Handles real-time data retrieval and view tracking while showcasing scalable, event-driven architecture with zero idle cost.

**Step 1: Setting Up the Database (DynamoDB)**
I started by creating a DynamoDB table to store my resume data. Instead of using a traditional structured database,
where I worked with a flexible NoSQL setup where I defined a simple primary key (ID) and added fields like name, skills, and views.
One challenge here was adjusting to the idea of a schema-less database and choosing the right data types.
This step helped me understand how DynamoDB stores data and why it’s a great fit for fast, scalable, serverless applications.

![1  Creating Dynamo DB Table](https://github.com/user-attachments/assets/0405694c-8957-4e0c-88b8-59091eb91299)
![2  Dynamo DB Table Created](https://github.com/user-attachments/assets/25636b0d-ca4d-4a50-bf01-d5dcb1e28bae)


**Step 2: Building the Logic (AWS Lambda)**
Next, I created a Lambda function using Python to handle incoming requests. This function updates the view count each time the API is called and retrieves my resume data from DynamoDB.
Working with Boto3 and DynamoDB expressions took some getting used to, especially when updating values and formatting responses correctly.
This step really showed me how powerful serverless compute can be—code only runs when needed, with no servers to manage.

![Lambda](https://github.com/user-attachments/assets/d20f2754-5dd4-4907-9220-1339b527e06a)
![7  Lambda code](https://github.com/user-attachments/assets/d5e907e9-1106-4d29-ada1-f9b00f467451)
![2  Dynamo DB Table Created](https://github.com/user-attachments/assets/7b6a021b-5e9b-4288-b2d9-d7f65784d9d3)
![3  Creating an Item](https://github.com/user-attachments/assets/c8ef4b09-869e-43b4-a010-7341f7a249df)


**Step 3: Managing Permissions (IAM)**
At this stage, I had to connect my Lambda function to DynamoDB securely. Initially, the function couldn’t access the database,
which led me to configure IAM roles and permissions.
This helped me understand how AWS handles security between services and the importance of granting only the permissions required.
It’s a small step, but critical for building secure cloud applications.

![IAM](https://github.com/user-attachments/assets/c7d960ab-7c62-47e1-afed-adac3d1044f3)


**Step 4: Creating the API (API Gateway)**
To make the project accessible, I used API Gateway to create a public endpoint that triggers the Lambda function.
This is what allows users (or a frontend app) to interact with the API.
Setting this up came with some challenges—especially dealing with CORS errors—but it gave me a better understanding of how frontend and backend systems communicate in real-world applications.

![9  API](https://github.com/user-attachments/assets/26ef5ad4-a4a6-4b59-bde2-e45593808a41)

**Step 5: Testing Everything Together**
Finally, I tested the API by calling the endpoint in a browser. 
Seeing the resume data returned successfully—and the view counter increasing on each refresh—was the moment everything clicked.
Debugging across multiple services was challenging, but it helped me learn how to troubleshoot distributed systems and validate end-to-end functionality.

![8  raw api data](https://github.com/user-attachments/assets/6682f29c-6f5a-4f5e-83bc-609c20de32e4)

**Overall Takeaway**
This project gave me hands-on experience building a fully serverless application using AWS.
It combines storage, compute, security, and API layers into a scalable and cost-efficient solution that only runs when needed.
