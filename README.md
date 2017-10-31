# Customer-API
Simple microservice using spring boot 


Business use cases:

1. A consumer may periodically (every 5 minutes) consume the API to enable it (the consumer) to maintain a copy of the provider API's customers (the API represents the system of record)

2. A mobile application used by customer service representatives that uses the API to retrieve and update the customers details

3. Simple extension of the API to support future resources such as orders and products 

Comments:

1. Customer API/customer-api.raml is the RAML spec
2. For usecase1 - enabled spring boot's cache mechanism to return the response more quickly, mainly during no change on the server detected.
3. For usecase2 - The API is designed in such a way to support all the four  CURD operations (Create, Update, Read and Delete) with the help of respective http method (Post, Put, Get and Delete). Moreover in case of update scenario the consumer can pass the specific fields that he/she wants to update. The API is clever enough to update very particular fields instead of replacing the entire customer record. This will ensure the effective usage of network by passing only the relevant data.
4. For usecase3 - The API is currently designed to support orders and products in a simple way, further it can be extended to support major usecases.  

