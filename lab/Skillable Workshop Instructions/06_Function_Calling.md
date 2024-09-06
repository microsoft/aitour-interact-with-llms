# Part 5 - Function Calling

In this section, we will explore another modality we can interact with LLMs - function calling. This allows you to include functions in your requests, and the model will respond with a JSON object containing the function’s arguments. The models are capable of formulating API calls and structuring data outputs based on the functions you provide.

> [!TIP]
> **What is function calling?** GPT-3.5, GPT-4o and GPT-4-turbo models can take user-defined functions as input and generate structured output. The models are capable of formulating API calls and structuring data outputs based on the functions you provide.

The latest versions of gpt-35-turbo and gpt-4 are fine-tuned to work with functions and are able to both determine when and how a function should be called. If one or more functions are included in your request, the model determines if any of the functions should be called based on the context of the prompt. When the model determines that a function should be called, it responds with a JSON object including the arguments for the function.

The models formulate API calls and structure data outputs, all based on the functions you specify. It's important to note that while the models can generate these calls, it's up to you to execute them, ensuring you remain in control.

Working with functions can be broken down into three high-level steps:

- Call the chat completions API with your functions and the user’s input
- Use the model’s response to call your API or function
- Call the chat completions API again, including the response from your function to get a final response

### Updating Prompt Instructions to provide context

1. Start by clicking on the **Assistants** Playground. Here you will see the different components of the Playground. In the **Deployments** section, ensure you select **gpt-4o** model. 

1. First we will clear some of the changes we had previously made. Navigate to **Prompt** and clear the Instructions. Next, navigate to the **Tools** tab and remove the **Contoso_Sales_Revenue.csv** file we uploaded. Lastly, on the top left of the chat window, select **CLear Chat**.

2. Next, update the Assistant **instruction**.

  - In the Prompt Instructions explain the goal of the assistant
  - Explain the information that needs to be gathered
  - Which function to call if all information is gathered

  > [!TIP]
  > Instructions are similar to system messages in the chat playground.

3. Navigate to the **Prompt** tab and copy the following instructions into the Instructions textbox.

  ```
  You are an AI assistant that helps people find hotels. 
  In the conversation with the user, your goal is to retrieve the required fields for the function search_hotels.
  ```

### Add your Function to your Tools

A function has three main parameters: name, description, and parameters.

- Name:a name for your function
- Description: The model is to determine when and how to call the function so it's important to give a meaningful description of what the function does.
- Parameters: is a JSON schema object that describes the parameters that the function accepts.

You can add your function as follows:

1. In the Assistants Playground, navigate to the **Tools** tab, you should see an option labeled **Add Function**. Click on this option to create a new function.
2. A pop up window will appear where you can input the necessary details for your new function. In the pop up window, copy the following function: 

  ```
  {
      "name": "search_hotels",
      "description": "Retrieves hotels from the search index based",
      "parameters": {
            "type": "object",             
            "properties": {
                  "location": {
                      "type": "string",
                      "description": "The location of the hotel (i.e. Seattle, WA)"
                  },
                  "price": {
                      "type": "number",
                      "description": "The maximum price for the hotel"
                  },
                  "features": {
                      "type": "string",
                      "description": "A comma separated list of features (i.e. beachfront, free wifi, etc.)"
                  }
              },
            "required": ["location","price","features"]
        }
  }
  ```

3. Click the "Save" button to add the function to your Assistant.

4. In the text box in the chat area, try the following prompt

  ```
  I'm looking for a hotel in the Netherlands
  ```

5. The agent should start asking you about location, price and hotel features and finally call the function and return the properties in JSON format.

![chat conversation with the model to output structured json](./Images/ai-studio-function-calling-chat.jpg)

>[!alert] Before moving on with the next section, click on the **Clear Chat** button to clear the message history.

## Best Practices for Function Calling

- Define **Clear Function Parameters:** Ensure that each function has a clear and concise description, along with well-defined parameters. This helps the model understand when and how to call the function, reducing ambiguity and improving the acuracy of the model's responses.

- **Error Handling:** Include robust error handling in your functions to manage unexpected inputs or failures gracefully.

- **Security Considerations:** Be mindful of security implications, especially when dealing with sensitive data or actions. Ensure that your functions are secure and do not expose vulnerabilities.

- **Iterative Testing:** Continuously test and refine your functions to ensure they work correctly with the model. This helps identify and fix issues early.

- **Parallel Function Calls:** When using parallel function calls, ensure that the functions are independent and do not interfere with each other.

### Parallel function calling with multiple functions

We can create a parallel function to find local attractions in the area.

1. First update the prompt instructions to include the tourist attractions function:

  ```
  Once you have retrieved the information use tourist_activities to get a list of activities a person can engage in once in the select country.
  ```

2. Create a new function referencing the local tourist attractions in the location:

  ```
  {
    "name": "tourist_activities",
    "description": "Determine activities a tourist can take part in",
    "parameters": {
      "type": "object",
      "properties":{
        "location": {
          "type": "string",
          "description": "location the tourist will be in e.g. Amsterdam, Berlin."
        },
        "activity": {
          "type": "string",
          "description": "activity the tourist would want to engage in e.g. going to the beach, visiting historical sites etc."
        }
      },
      "required": [
        "location", "activity"
      ]
    }
  }
  ```

3. Try the following prompt:

  ```What activities can I engage in while in Amsterdam?```

  You will receive a structured output.

>[!alert] Before moving on with the next section, click on the **Clear Chat** button to clear the message history.

## Bringing it all together

For the Contoso Outdoor Company, we can create a function that searches through the catalog based on specific parameter, that is: product category, activity and cost of the product.

First we will need to update the instructions with a description and sample catalog for the different products. Replace the existing instructions with:

```
You are an AI assistant that helps people find products in the Contoso Outdoor Company’s database. In the conversation with the user, your goal is to retrieve the required fields for the function find_products.
```

>[!alert] Before moving on with the next part, delete the existing functions we had created.

1. Create a new function called **find_products** with the parameters category, activity and cost. 

  ```
  {
    "name": "find_products",
    "description": "Finds products based on a user needs.",
    "parameters": {
      "type": "object",
      "properties": {
        "category": {
          "type": "string",
          "description": "an item category such as a jacket, tent or boots"
        },
        "activity": {
          "type": "string",
          "description": "activity category for the item e.g. running, hiking, camping."
        },
        "cost": {
          "type": "integer",
          "description": "maximum cost to be paid by an individual e.g. 200, 20."
        }
      },
      "required": [
        "category", "activity", "cost"
      ]
    }
  }
```

2. To test the function we have added, try the prompt below:

  ```I need a warm jacket.```

3. The agent should start asking you about activity category and maximum budget then finally call the function and return the properties in JSON format.

## Next Steps

Congratulations! You have now completed the 5th part of the lab and you learnt how to interact with LLMs using Function Calling. 

Click **Next** to advance to the Summary section of the workshop.