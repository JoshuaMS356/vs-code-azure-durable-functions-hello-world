## Azure Durable Functions Hello World

This is a sample Azure Durable Functions project that you can run in Visual Studio Code.

Please follow the instructions to run it locally:

**1. Clone the project**


**2. Install Azure Functions Cross Platform Tools (more info here http://bit.ly/2ftaOIC) by running the following command (you will need Node.js 8.5 and later):**

```javascript

npm i -g azure-functions-core-tools@core 

```

**3. Navigate the to folder and add Durable Functions Extenstion by running the following command:**

```javascript
func extensions install -p Microsoft.Azure.WebJobs.Extensions.DurableTask -v 1.0.0-beta

```
**4. Start local Azure Storage Emulator v5.2 or later**  

**5. Modify the contents of your local.settings.json file to look similar to:**

```javascript

{
  "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "UseDevelopmentStorage=true",
    "Storage": "UseDevelopmentStorage=true"
  }
}

```

**6. Start the project by running the following command in the folder of your function app:**

```javascript

func host start 

```

**7. In Postman or with cURL call the endpoint provided by Azure Functions Tools:**

```javascript

curl -X POST http://localhost:7071/api/orchestrators/HelloSequence

```

**8. You can check the progress of your function by calling "statusQueryGetUri" endpoint provided in the response similar to:** 

```javascript

url -X GET 'http://localhost:7071/runtime/webhooks/DurableTaskExtension/instances/9c71ff5ff9f34e4f82f882c795bb20fa?taskHub=DurableFunctionsHub&connection=Storage&code=xuqaAlxP%2F%2FjlrBxU%2FL8kE5jjzMzhHysVVUucYItg6rBPJvAAIetd%2FA%3D%3D'
  
```

**9. Great! You are now able to run Azure Durable Functions in VS Code! Congratulations!!!***
