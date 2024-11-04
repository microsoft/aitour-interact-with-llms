# Part 3 - Multimodal interfaces

By now we have interacted with LLMs using a single modality: inputting text and receiving either text or images. However, multimodal interfaces are becoming increasingly popular, as they allow users to interact with models using multiple modalities, such as text, images, and speech, thus facilitating human-computer interactions. In this section, we will explore how to use multimodal interfaces to interact with gpt-4o-mini and gpt-4o-realtime-preview.


> [!TIP]
> **gpt-4o-mini** is a multimodal model that incorporates both natural language processing and visual understanding. It is able to process as input a combination of text and images, and generate an output which is relevant to both modalities.

**gpt-4o-realtime-preview** supports low-latency, "speech in, speech out" conversational interactions. It is a great fit for use cases involving live interactions between a user and a model, such as customer support agents, voice assistants, and real-time translators.

## Best Practices

- **Contextual specificity**: Adding context to the scenario at hand gives the model a better understanding of an appropriate output. This level of specificity aids in focusing on relevant aspects and avoiding extraneous details.​

- **Task-oriented prompts**: Focusing on a specific task helps the model to develop the output while taking that perspective into consideration.​

- **Define output format**: Clearly mention the desired format for the output, such as markdown, JSON, HTML, etc. You can also suggest a specific structure, length, or specific attributes about the response.​

- **Handling refusals**: When the model indicates an inability to perform a task, refining the prompt can be an effective solution. More specific prompts can guide the model towards a clearer understanding and better execution of the task. Some tips to keep in mind:​
    - Request explanations for generated responses to enhance transparency in the model's output​
    - If using a single-image prompt, place the image before the text​
    - Ask the model to describe the image in detail first and complete your specific task from the description​

- **Prompt Tuning**: Try prompt tuning techniques that we explored for text generation scenarios such as:​
    - Breaking down requests (e.g. chain of thoughts)​
    - Adding examples (e.g. few-shot learning)​

## Interacting with the model using an Image

1. Navigate to the  **playgrounds** and select **Try the Chat Playground**
2. In the chat text box, click on the attachment icon to upload a local image.

![Uploading image as input](./Images/upload_image_icon.png)

3. Select the [](./Images/*) image.
4. Once you have uploaded the file, try these prompts to start interacting with the image:

```What is on the image?```

```What is the house made of?```

```Does the house have a swimming pool?```

## Answer questions based on image

Answer the questions on the image.


## Apply Prompt Tuning

If you are not satisfied with the result you got in the previous step, you can apply some prompt tuning techniques to improve the quality of the generated code. In fact, the prompt you have used to instruct the model in the previous step already contains some prompt engineering best practices, such as *placing the image before the text* and specifying the *output format*. However, you can try to further refine the prompt to get better results.

> [!NOTE]
> If the model indicates an inability to perform the task, you can **handle the refusal** by requesting explanations for generated responses and what kind of information it misses to compete the task.

>[!alert] Select the System Message tab. In the window titled "Give the model instructions and context" clear the information and replace it with the following and then choose Apply Changes. 

Create a tagline and short description for this rental home advertisement.
    - The first picture is from the home
    - The other pictures are from sights nearby
    - In the description use the features of the house and make the ad more compelling with the sights. 
    - Do not talk about features not visible in the images.
    - If you have information about the location of the images, use that information in the description

5. Navigate back to the chat playground and generate a product catalog of the Contoso Outdoor company, using the following prompt:

`` Generate a product catalog of the Contoso Outdoor company based on the image``

6. Copy the catalog generated.

## Real time-audio interactions

By integrating the ``gpt-4o-realtime-preview `` model, users can interact with the website using voice commands, making the shopping experience more engaging and accessible.

1. Navigate to the **Real-time audio playground** and set the deployment to ``gpt-4o-realtime-preview``

2. Update the model instructions with products of the Contoso Outdoor Company by **pasting** the product catalog you just copied into the **Give the model instructions and context box**

3. Interact with the model by clicking on the **start listening** button, ask the model questions on the different products and recommendations:

`` What jacket can I buy for the winter``

`` Suggest a tent I can use to go hiking``

`` What about a tent I can use for the winter?``

## Next Steps

Congratulations! You have now completed the 3rd part of the lab and you learnt how to interact with multimodal models. 

Click **Next** to advance to the Azure AI Assistants section.