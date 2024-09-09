# Get started

> [!TIP]
> What is **Azure AI Studio**? Azure AI Studio is designed for developers to build generative AI applications on an enterprise-grade platform. Developers can interact with their projects code-first via the Azure AI SDK, explore, build, test, and deploy AI models using cutting-edge tooling, and collaborate in a secure environment. The platform supports transforming proof of concepts into production-ready solutions with continuous monitoring and refinement.

## Prerequisites

To complete the lab, you will need:

- An Azure subscription - [Create one for free.](https://azure.microsoft.com/free/cognitive-services?WT.mc_id=aiml-132569-bethanycheum)
- An Azure OpenAI resource with [GPT-4o and DALL.E 3 model supported in a supported region.](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models#assistants-preview?WT.mc_id=aiml-132569-bethanycheum)

## Deploying your resources

In this workshop we will be working with Azure AI Studio. First, you will need to deploy the necessary resources using the steps below:

1. Click the deploy to Azure button to deploy your resources: [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Faitour-interact-with-llms%2Fmain%2Flab%2FWorkshop%20Instructions%2Fassets%2FAITour24_WKR540_Template.json)

2. In the tab that you just opened sign in to your Azure account.

3. Once signed in, you will be redirected to create resources based on the custom template. Create a new Resource Group and name it: **interact-with-llms**. 

4. Next in the **Unique Suffix** field, add any unqiue four letters. Once done, click **Review and Create** button to create your resources

> [!NOTE]
> Deployment of the resources will take ~2-3 minutes to complete.

5. For this workshop we will be working on Azure AI Studio, especially focusing on the playground feature. Once your deployment is complete, in your browser, navigate to Azure AI Studio by visiting the link [https://ai.azure.com](https://ai.azure.com?WT.mc_id=aiml-132569-bethanycheum)


## Navigating Azure AI Studio

![Azure AI Studio logged in homepage](./Images/ai-studio-login-homepage.png)

1. To begin, navigate to the left-hand sidebar where you will find the **Management** section. Under this section, select **All Hubs.** This action will lead you to a centralized area where all available resources and tools are displayed, giving you an overview of your current hub connections. 
2. Next, locate the **WRK540 AI Hub** in the list of available hubs. It is listed under the **"Name"** column. Click on this hub to access its settings and resources.

![Hub management tab](./Images/ai-studio-hubmanagement-hub.jpg)

3. You will be redirected to the Hub Homepage.

![Hub Homepage](./Images/ai-studio-hub-homepage.jpg)

You will notice a set of elements once we have logged in and land on the Hub Homepage.

### Navigation Panel

On the left side of the screen you will see a navigation panel with a group of different tabs.

- **Current Hub, Hub Overview and All Projects**: This tab provides access to the Hub Overview, and a list of all the projects within the Hub.
- **Get Started**: 
    - *Model Catalog*: The model catalog showcases the available models inside Azure AI Studio. You can click and expand on each model for in-depth description of usage and other details.
    - *Model Benchmarks*: Here you can compare benchmarks across models and datasets available, with charts on accuracy, similarity, fluency, coherence, etc.
    - *Prompt Catalog*: The prompt catalog provides sample prompts for a myriad of common use cases, which can be used to further understand how a model works, and can be customized for specific scenarios.
    - *AI Services*: In the AI Services tab you can see a list of Azure AI Services available, along with demos, use cases and more.

> [!NOTE]
> Azure AI Studio hosts some of the most popular foundation models provided by companies such as Microsoft, Open AI, Hugging Face, Meta and Mistral.

- **Playgrounds**: The Playgrounds represent a fast and accessible way to interact with the models.
- **Shared Resources**: This tab provides access to the resources connected or shared by the AI Hub. Here you can access resources such as the model Deployments, connections to other services, compute instances available in the Hub, user access and content filters applied to our models.

### 2. Hub Overview

On this page, we can see an overview of our Azure AI Studio Hub. This includes the following:

- **Projects**: A project is a resource within Azure AI Studio that grants us access to most of the platform's features, such as the **Playgrounds**. You will notice we have a project created already. This is intentional and we will be working with it in the upcoming sections.
- **Description**: A short description of the Azure AI Studio Hub we are in.
- **Hub Properties**: A collection of various properties such as the Hub's name, its location, resource group, etc. Here we can find useful information such as *API endpoints and keys* and the *subscription's quota*.
- **Connected Resources**: Azure AI Studio allows for multiple resources to be connected to it, expanding its features and functionality. Resources such as Azure AI Search, or in our case, Azure AI Service further increase the capabilities of our Hub, and grant us access to deployments such as LLMs or functionalities such as vector search.
- *Users**: Allows us to grant access to collaborators or applications that may need to use the services within the Hub.

## Project Overview

1. Now, under the **Projects** section, locate the existing project. Click on this project to move forward and access the detailed project environment. 
 
 >[!alert] Click on the existing project to move forward.
 
 ![image showing where to click to access a project](./Images/ai-studio-click-project.png)

The Project overview page is very similar to the Hub Overview, except the details are tied to the project instead of the Hub that hosts it. 

### Navigation Bar

You will notice the navigation bar has updated with new tabs, which represent functionalities tied to our project. The **Get Started** section remains the same, and **Playgrounds** are expanded to include other versions.

We have two new sections:
- **Tools**: This includes useful opportunities to expand your project's reach, such as ***working in VS Code*** by running a cloud compute, access to [***Prompt Flow***](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow), development of ***Evaluations*** for your models and the ability to carry ***Fine Tuning*** on your deployments.
- **Components**: Here you can add complimentary elements to the project, with resources such as ***Data***, ***Indexes***, ***Deployments*** and ***Content Filters*** to be used as part of your work.

For this lab we will focus on using the **Playgrounds**. Click on the Chat Playground and move on to the next section.

## Project Playgrounds

You will notice we have four options for our **Playground**. Each option represents a different approach to interacting and using AI models, which can be tailored to our specific needs.

We will be carrying most of our work in these Playgrounds, but namely in the following two:

- **Chat Playground**
- **Images Playground**
- **Assistants Playground**

> [!NOTE]
> There is also playground modes designed for various type of scenarios, such as Assistants, Completions and others.

### Chat Playground

Within the Project playground section, navigate to the available tools and select **Chat.** This feature allows you to engage with and test various AI models in a conversational format.

![Image of Azure AI Studio Playground Chat Mode](./Images/ai-studio-playground.jpg)

1. **Deployment**: This section allows us to change between our deployed models.
1. **System Message Box**: Here is where we enter instructions for the model, previous to the user interaction.
1. **Add your data**: Azure AI Studio supports providing the deployed models with external data, allowing for better search and context.
1. **Parameters**: This tab contains the models detailed settings, such as temperature.
1. **Chat Box**: The chat box is where we will see our interactions with the model in the form of chat messages.
1. **Prompt Box**: This is where we type the prompts we want to send to the model.

### Images Playground

In the Project playground section, locate and select **Images.** This option allows you to work with image generation

![Image of Azure AI Studio Playground Images Mode](./Images/ai-studio-image-playground.jpg)

1. **Deployments**: In this drop-down we are able to choose the model to prompt for image generation. These models, just like the chat ones, come from our deployments.
1. **Prompt Box**: Similar to the chat playground's box, this is where the models get their input from the user. In the case of images, descriptions of what we want to generate.
1. **Results Box**: Finally, here is where the generated images are displayed.

### Assistants Playground

In the Project playground section, select **Assistants**. This feature provides you with the tools to build, test, and customize AI-driven assistants.

![Image of Azure AI Studio Playground Assistants Mode](./Images//ai-studio-assistants-functions-playground.jpg)

1. **Deployments**: In this drop-down we are able to choose the model to prompt for image generation. These models, just like the chat ones, come from our deployments.
1. **Assistant Name**: Here you can give your assistant a name.
1. **Prompt**: Here is where we enter instructions for the model, previous to the user interaction.
1. **Tools**: Here is where you get additional tools to customize your assistant including functions, file search and code interpreter
1. **Parameters**: This tab contains the models detailed settings, such as temperature.
1. **Prompt Box**: Similar to the chat playground's box, this is where the models get their input from the user. 
1. **Results Box**: Finally, here is where the generated images are displayed.

#### Tools in the Assistant Playground

Within the Assistants section, navigate to the **Tools** tab. This area provides access to various utilities that can enhance and extend the capabilities of your assistant.

![Image of Azure AI Studio Playground Assistants Mode](./Images/ai-studio-assistants-functions-playground.jpg)

1. **Tools**: Under tools in the Assistants Playground you will find file search, code interpreter and functions.
1. **File Search**: Here you can access your files you have uploaded. Each assistant can have at most 1 vector store attached to it.
1. **Code interpeter**: Code Interpreter allows the Assistants API to write and run code in a sandboxed execution environment. 
1. **Functions**: This allows you to describe the structure of functions to an Assistant and then return the functions that need to be called along with their arguments..

## Ready to start

That covers the necessary setup and basics of Azure AI Studio. We will now move forward to begin interacting with the models.

Return to the  **Chat** under **project plaground** and click Next in the instructions to proceed to Part 1: Text Generation

>[!alert] Go back to the **Chat Playground** and move to [Part 1: Text Generation](./02_Text_Generation.md)
