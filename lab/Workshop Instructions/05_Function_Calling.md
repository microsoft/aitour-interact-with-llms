# Part 4 - Function Calling

In the previous sections, we have engaged with LLMs through text, image and multimodal prompts. In this section, we will explore another modality - function calling. This allows you to include functions in your requests, and the model will respond with a JSON object containing the function’s arguments. The models are capable of formulating API calls and structuring data outputs based on the functions you provide.

> [!TIP]
> **What is function calling?** GPT-3.5, GPT-4o and GPT-4-turbo models can take user-defined functions as input and generate structured output. The models are capable of formulating API calls and structuring data outputs based on the functions you provide.

The latest versions of gpt-35-turbo and gpt-4 are fine-tuned to work with functions and are able to both determine when and how a function should be called. If one or more functions are included in your request, the model determines if any of the functions should be called based on the context of the prompt. When the model determines that a function should be called, it responds with a JSON object including the arguments for the function.

The models formulate API calls and structure data outputs, all based on the functions you specify. It's important to note that while the models can generate these calls, it's up to you to execute them, ensuring you remain in control.

Working with functions can be broken down into three high-level steps:

- Call the chat completions API with your functions and the user’s input
- Use the model’s response to call your API or function
- Call the chat completions API again, including the response from your function to get a final response

### Updating Prompt Instructions to provide context

First update the Prompt Instructions.

- In this Prompt Instructions explain the goal of the assistant
- Explain the information that needs to be gathered
- Which function to all if all information is gathered

> [!TIP]
> Instructions are similar to system messages in the chat playground.

```text title="Prompt Instructions"
You are an AI assistant that helps people find hotels. 
In the conversation with the user, your goal is to retrieve the required fields for the function search_hotels.
```

### Add your Function to your Tools

A function has three main parameters: name, description, and parameters.

- Name:a name for your function
- Description: The model is to determine when and how to call the function so it's important to give a meaningful description of what the function does.
- Parameters: is a JSON schema object that describes the parameters that the function accepts.

Below is an example of a sample function with the parameters location, price and features:

```json title="function"
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

### Interacting with the model using function calling

Now let's start a conversation with the agent.

Ask:

```text title="User Message"
I'm looking for a hotel in the Netherlands
```

The agent should start asking you about location, price and hotel features and finally call the function and return the properties in JSON format.

## Best Practices for Function Calling

- Define **Clear Function Parameters:** Ensure that each function has a clear and concise description, along with well-defined parameters. This helps the model understand when and how to call the function, reducing ambiguity and improving the acuracy of the model's responses.

- **Error Handling:** Include robust error handling in your functions to manage unexpected inputs or failures gracefully.

- **Security Considerations:** Be mindful of security implications, especially when dealing with sensitive data or actions. Ensure that your functions are secure and do not expose vulnerabilities.

- **Iterative Testing:** Continuously test and refine your functions to ensure they work correctly with the model. This helps identify and fix issues early.

- **Parallel Function Calls:** When using parallel function calls, ensure that the functions are independent and do not interfere with each other.

### Parallel function calling with multiple functions

We can create a parallel function to find local attractions in the area.

First update the prompt instructions with local attractions in the Netherlands:

```
Once you have retrieved the information use tourist_activities to get a list of activities a person can engage in once in the select country.

```

Create a new function referencing the local tourist attractions in the location:

```json title="function"
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

## Bringing it all together

For the Contoso Outdoor Company, we can create a function that searches through the catalog based on specific parameter, that is: product category, outdoor activity and cost of the product.

First we will need to update the system instructions with a description and sample catalog for the different products:

```
You are an AI assistant that helps people find products in the Contoso Outdoor Company’s database. In the conversation with the user, your goal is to retrieve the required fields for the function find_products.
```

Then we can create a function with the parameters category, outdoor and cost.

``` json title="function"
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
        "description": "outdoor category for the item e.g. running, hiking, camping."
      },
      "cost": {
        "type": "integer",
        "description": "maximum cost to be paid by an individual e.g. 200, 20."
      }
    },
    "required": [
      "category", "outdoor", "cost"
    ]
  }
}
```

You can test your functions by asking a question to your model:

```
I need warm jacket.
```

Congratulations! You have now completed the 4th part of the lab and you learnt how to interact with llms using Function Calling. Click next to continue with AI Assistants.
