# Part 3 - Multimodal interfaces

By now we have interacted with LLMs using a single modality: inputting text and receiving either text or images. However, multimodal interfaces are becoming increasingly popular, as they allow users to interact with models using multiple modalities, such as text, images, and speech, thus facilitating human-computer interactions. In this section, we will explore how to use multimodal interfaces to interact with GPT-4o.


> [!TIP]
> **GPT-4o** is a multimodal model that incorporates both natural language processing and visual understanding. It is able to process as input a combination of text and images, and generate an output which is relevant to both modalities.

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

1. In Project playground section, on the left-hand navigation bar, navigate to the available tools and select **Chat.** 
2. In the chat text box, click on the attachment icon to upload a local image.

![Uploading image as input](./Images/upload_image_icon.png)

3. Select the [*contoso_outdoor_ecommerce_sketch_notes.jpg*](./Images/contoso_outdoor_ecommerce_sketch_notes.jpg) image. 

    ![Contoso Ecommerce Website UI](./Images/contoso_outdoor_ecommerce_sketch_notes.jpg).

    This image represents a sketch of our Contoso Outdoor e-commerce website we want to build. We will use this image as input to GPT-4o to gather information from the image, and later generate a code snippet for the website, using the sketch as a reference.

4. Once you have uploaded the file, try these prompts to start interacting with the image:

    ```How many products are shown in the homepage below?```


    ```What is the name of the company?```


    ```What is the most expensive product?```

## Generate a code snippet for the website UI from an image

Next, we will prompt the model to generate a code snippet for the website using the sketch as a reference.
1. Go to the **Parameters** tab and set the *Max Response* to 4000.
1. Go back to the text field in the chat window and add the text below to instruct the model on how to use the image input:

    ```
    Generate the html and bootstrap code to implement the UI of the Contoso Outdoor Company e-commerce landing page, based on the hand-drawn sketches in the image.
    ```

1. The outcome should provide a basic layout for the landing page of Contoso Outdoor Company. It includes placeholders for product descriptions, which you can populate with the text and image artifacts created throughout part 1 and 2.

If you want to view the code syntax is correct and what the template looks like:
1. Launch the Visual Studio Code (VS Code) application on your Virtual Machine.
2. In the top menu bar, click on File. From the dropdown menu, choose New File. This will open a pop up in your VS Code.

![alt text](./Images/image.png)
3. In the pop up, enter ``website.html`` as the file name, then click **Create New File**. It will open up File Explorer, click on **Create File** to create and save your new file.
4. Copy the HTML code you have generated. Paste this code into the newly created website.html file in VS Code.
5. In the top-right corner of the VS Code interface, find and click the **Open Preview to the Side button.** This button often looks like a split-screen icon or might be labeled as **Open Preview**.
6. The preview pane will open on the side, displaying the rendered output of your HTML code.

![Preview website code in VS Code](./Images/vs-code-view-html.png)


## Apply Prompt Tuning

If you are not satisfied with the result you got in the previous step, you can apply some prompt tuning techniques to improve the quality of the generated code. In fact, the prompt you have used to instruct the model in the previous step already contains some prompt engineering best practices, such as *placing the image before the text* and specifying the *output format*. However, you can try to further refine the prompt to get better results.

> [!NOTE]
> If the model indicates an inability to perform the task, you can **handle the refusal** by requesting explanations for generated responses and what kind of information it misses to compete the task.

>[!alert] Select the System Message tab. In the window titled "Give the model instructions and context" clear the information and replace it with the following and then choose Apply Changes. 

```
## Task
You are a web designer for the Contoso Outdoor Company e-commerce website. Your goal is to generate the website code snippets for the homepage GUI.
```

In addition, let's modify the previous query, by breaking down the instructions into smaller steps. This will help the model to better understand the task and generate more accurate results. Clear the chat history. Upload the picture again and send the following text to the chat interface:

```
You will generate the website GUI template for the homepage of the e-commerce website.
Instructions:
1. Use the provided image to extract the layout, the sections, and the e-commerce products names and prices
2. Use html and bootstrap as output format
3. Add placeholders for products images
```

Copy the new HTML, navigate back to **Visual Studio Code** and replace the old html with the new one. Notice any differences? Feel free to adjust the code template according to the final design you wish to achieve.

## Next Steps

Congratulations! You have now completed the 3rd part of the lab and you learnt how to interact with multimodal models. 

Move to [Part 4: Azure AI Assistants](./05_AI_Assistants.md)