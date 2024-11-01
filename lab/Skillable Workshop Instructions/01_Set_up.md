# Get started

> [!TIP]
> What is **Azure AI Studio**? Azure AI Studio is designed for developers to build generative AI applications on an enterprise-grade platform. Developers can interact with their projects code-first via the Azure AI SDK, explore, build, test, and deploy AI models using cutting-edge tooling, and collaborate in a secure environment. The platform supports transforming proof of concepts into production-ready solutions with continuous monitoring and refinement.

## Sign in to Windows
As a first step, login into the lab Virtual Machine by using these credentials:
- Username: will already be set to Admin.
- Password: enter +++@lab.VirtualMachine(Win11Base23B-W11-22H2).Password+++ and click.

> [!TIP]
>  First time using **Skillable?** The green "T" (e.g., +++Admin+++) indicates values that are automatically input for you at the current cursor location in VM, with one click. This reduces your effort and minimizes input errors.

## Sign in to Azure AI Studio
   
For this workshop we will be working on Azure AI Studio, especially focusing on the playground feature. 

1. In the Desktop, click on **Microsoft Edge** browser.
2. Type +++https://ai.azure.com+++ on the search box to access Azure AI Studio. The browser will open a new tab with the Azure AI Studio Homepage as shown in the following image.

![Homepage of Azure AI Studio](./Images/ai-studio-homepage.png)

## Navigating Azure AI Studio

1. Let's start by clicking on **Sign In**, you can find the sign in link in the top right of the window, and entering the following credentials when prompted for the login credentials:
    -  Email: +++@lab.CloudPortalCredential(User1).Username+++
    -  Password: +++@lab.CloudPortalCredential(User1).Password+++

    Now that we are logged in, we can start navigating around the platform. 

<!-- ![Azure AI Studio logged in homepage](./Images/ai-studio-hubmanagement.jpg) -->

2. Locate the **Workshop AI Hub** in the list of available hubs. Click on the project associated to the hub to access its settings and resources.

![Hub management tab](./Images/ai-studio-hubmanagement-hub.jpg)

<!-- ## Hub Homepage

You will notice a set of elements once we have logged in and land on the Hub Homepage.

![Hub Homepage](./Images/ai-studio-hub-homepage.jpg)


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

-->

## Project

## Project Overview

On this page, we can see an overview of our Azure AI Studio Project. This includes:
- **Project Name and Description**: The name of the project and a short description of the Azure AI Studio Project we are in.
- **Quick Refereence**: A collection of various properties such as the Project's connection string, its location, resource group, etc. 
- **Endpoints and keys**: Azure AI Studio allows for multiple resources to be connected to it, expanding its features and functionality. Resources such as Azure OpenAI, Azure AI Search and Azure AI Servicse further increase the capabilities of our Project, and grant us access to deployments such as LLMs or functionalities such as vector search.  Here we can find useful information such as *API endpoints and keys* and documentation.
- **Recent work and tutorials**: Under this, your recent work is highlighted with additional learning resources and tutorials to help you get started.

### Navigation Bar

You will notice the navigation bar has updated with new tabs, which represent functionalities tied to our project.

We have two new sections:
-  The first section remains the same and now include **Project Playgrounds**.
- **Build and Customize**: This includes useful opportunities to expand your project's reach, such as ***working in Code*** by running a cloud compute, **agents**, access to [***Prompt Flow***](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow), and the ability to carry ***Fine Tuning*** on your deployments.
- **Assess and Improve:** this includes development of ***Evaluations*** for your models, **tracing** to debug your flows and **content filters** to add guardrails to prompt inputs and completion outputs.
- **My assets**: Here you can add complimentary elements to the project, with resources such as ***Data***, ***Indexes***, ***models and endpoints*** and ***Web apps*** to be used as part of your work.
- **Management Center:** location to manage all you  hub and project details and resources.

For this lab we will focus on using the **Playgrounds** and **Agents**. Navigate to the Playgrounds and move on to the next section.

## Playgrounds

You will notice we have four options for our **Playground**. Each option represents a different approach to interacting and using AI models, which can be tailored to our specific needs.

We will be carrying most of our work in these Playgrounds, but namely in the following three:

- **Chat Playground**
- **Images Playground**
- **Real-time audio playground**
- **healthcare playground**: `<placeholder on what it does>` we will not be focussing on this in our workshop today

### Chat Playground

Within the playground section, navigate to the **Chat playground** and select **Try the Chat Playground.** This feature allows you to engage with and test various AI models in a conversational format.

![Image of Azure AI Studio Playground Chat Mode](./Images/ai-studio-playground.jpg)

1. **Setup Deployment**: This section allows us to change between our deployed models.
1. **System Message Box**: Here is where we enter instructions for the model, previous to the user interaction.
1. **Add your data**: Azure AI Studio supports providing the deployed models with external data, allowing for better search and context.
1. **Parameters**: This tab contains the models detailed settings, such as temperature.
1. **Chat Box**: The chat box is where we will see our interactions with the model in the form of chat messages.
1. **Prompt Box**: This is where we type the prompts we want to send to the model.

### Images Playground

Navigate back to Playgrounds, navigate to the **Image playground** and select **Try the Image Playground.** This option allows you to work with image generation

![Image of Azure AI Studio Playground Images Mode](./Images/ai-studio-image-playground.jpg)

1. **Deployments**: In this drop-down we are able to choose the model to prompt for image generation. These models, just like the chat ones, come from our deployments.
1. **Prompt Box**: Similar to the chat playground's box, this is where the models get their input from the user. In the case of images, descriptions of what we want to generate.
1. **Results Box**: Finally, here is where the generated images are displayed.

### Real-time audio playground

Navigate back to Playgrounds, navigate to the **Real-time audio playground** and select **Try the Real-time audio Playground.** This feature allows you to engage with and test various AI models in a audio conversational format.

![Image of Azure AI Studio Playground Real time audio mode](./Images/ai-studio-real-time-audio-playground.jpg)

1. **Deployment**: This section allows us to change between our deployed models.
1. **Server turn detection**: Determines if the server should utilize voice activity detection (VAD) to identify when a user has finished speaking.
1. **Model instructions Box**: Here is where we enter instructions for the model, previous to the user interaction.
1. **Choose a voice**: Gpt-4o-audio offers a variety of voices to choose from with unique accents or tonal capabilities tailored to your liking.
1. **Server turn detection**: These are parameters used in voice detection to help improve the model capabilities to improve efficiency and performance.
1. **Parameters**: This tab contains the models detailed settings, such as temperature and max response.
1. **Prompt Button**: Similar to the chat playground's box, this is where the models get their input from the user. 

## Agents 

``error: invalid subscription``

In the Navigation bar, select **Agents**. This feature provides you with the tools to build, test, and customize AI-driven assistants.

![Image of Azure AI Studio Playground Assistants Mode](./Images/ai-studio-assistants-playground.jpg)

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

- **Tools**: Under tools in the Assistants Playground you will find file search, code interpreter and functions.
- **File Search**: Here you can access your files you have uploaded. Each assistant can have at most 1 vector store attached to it.
- **Code interpeter**: Code Interpreter allows the Assistants API to write and run code in a sandboxed execution environment. 
- **Functions**: This allows you to describe the structure of functions to an Assistant and then return the functions that need to be called along with their arguments..

## Ready to start

That covers the necessary setup and basics of Azure AI Studio. We will now move forward to begin interacting with the models. 

5. Return to the  **playgrounds** navigate to the **Chat playground** and select **Try the Chat Playground.**  In the instructions tab, Click Next to proceed to Part 1: Text Generation


>[!alert] Return to the  **Chat** under **project playground** and click Next in the instructions to proceed to Part 1: Text Generation

Click **Next** to advance to the Text Generation section.