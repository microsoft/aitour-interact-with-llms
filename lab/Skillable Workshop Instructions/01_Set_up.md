# Get started

> [!TIP]
> What is **Azure Azure AI Foundry**? Azure AI Foundry is the ultimate platform for innovators to create the future. It offers a comprehensive suite of Azure AI capabilities and tools to design, customize, and manage AI applications and agents. It's seamlessly integrated with the world's most loved developer tools, including GitHub, Visual Studio, and Copilot Studio. Azure AI Foundry empowers developers and IT admins to bring their AI visions to life with ease and efficiency.

## Sign in to Windows
As a first step, login into the lab Virtual Machine using the following credentials:
- Username: already set to Admin.
- Password: enter +++@lab.VirtualMachine(Win11Base23B-W11-22H2).Password+++ and click.

> [!TIP]
>  First time using **Skillable?** The green "T" (e.g., +++Admin+++) indicates values that are automatically input for you at the current cursor location in VM, with one click. This reduces your effort and minimizes input errors.

## Sign in to Azure AI Foundry portal
   
In this workshop we will be working on Azure AI Foundry portal, focusing especially on the playground feature. 

1. On the Desktop, click on **Microsoft Edge** browser. Navigate to the second browser tab which will be showing the Azure AI Foundry portal homepage as shown in the following image.

![Homepage of Azure AI Foundry](./Images/aifoundry-homepage.jpeg)

## Navigating Azure AI Foundry portal

1. Start by clicking **Sign In**, you can find the sign in link in the top right of the window, and enter the following credentials when prompted for the login credentials:
    -  Email: +++@lab.CloudPortalCredential(User1).Username+++
    -  Password: +++@lab.CloudPortalCredential(User1).Password+++

    Now that we are logged in, we can start navigating around the platform. 

2. Locate the **Workshop AI Hub** in the list of available hubs. **Click on the project** with the hub to access its settings and resources.

![Hub management tab](./Images/aifoundry-hub-navigation.jpeg)

## Project

![project overview tab](./Images/aifoundry-project-overview.jpeg)

### Project Overview

On this page, we can see an overview of our Azure AI Foundry portal Project. This includes:
- **Project Name and Description**: The name of the project and a short description of the Azure AI Foundry portal Project we are in.
- **Project details**: A collection of various properties such as the Project's connection string, its location, resource group, etc. 
- **Endpoints and keys**: Azure AI Foundry portal allows for multiple resources to be connected to it, expanding its features and functionality. Resources such as Azure OpenAI, Azure AI Search and Azure AI Services further enhance the capabilities of our Project, granting us access to deployments such as LLMs or functionalities such as vector search.  Here we can find useful information such as *API endpoints and keys* and documentation.
- **Recent resources and tutorials**: Under this, your recent resources is highlighted with additional learning resources and tutorials to help you get started.

### Navigation Bar

You will notice the navigation bar has updated with new tabs, which represent functionalities tied to our project.

![project navigation bar](./Images/aifoundry-project-navigation.jpeg)

We have two new sections:
1.  The first section includes _Playgrounds_ to interact with the models, _Overview_ which provides a general overview of your project, _Model Catalog_ which showcases the available models inside Azure AI Foundry, and _AI Services_ where you can see a list of Azure AI Services available along with demos, use cases and more.
1. **Build and Customize**: This includes useful opportunities to expand your project's reach, such as _working in Code_ by running a cloud compute, access to [_Prompt Flow_](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow), and the ability to carry _Fine Tuning_ on your deployments.
1. **Assess and Improve:** this includes development of _Evaluations_ for your models, _tracing_ to debug your flows and _content filters_ to add guardrails to prompt inputs and completion outputs.
1. **My assets**: Here you can add additional elements to the project, with resources such as _Data_, _Indexes_, _models and endpoints_ and _Web apps_ to be used as part of your work.
1. **Management Center:** a location to manage all you  hub and project details and resources.

For this lab we will focus on using the **Playgrounds**, navigate to the Playgrounds and move on to the next section.

## Playgrounds

You will notice we have different options for our **Playground**. Each option represents a different approach to interacting and using AI models, which can be tailored to our specific needs.

We will be doing most of our work in these Playgrounds, but namely in the following:

1. **Chat Playground**
1. **Images Playground**
1. **Real-time audio playground**
1. **Agents playground**

![Image of Azure AI Foundry Playgrounds](./Images/aifoundry-playgrounds.jpeg)

### Chat Playground

Within the playground section, navigate to the **Chat playground** and select **Try the Chat Playground.** This feature allows you to engage with and test various AI models in a conversational format.

![Image of Azure AI Foundry Playground Chat Mode](./Images/aifoundry-chat-playground.jpeg)

1. **Deployment**: This section allows us to change between our deployed models.
1. **System Message Box**: Here is where we enter instructions for the model, previous to the user interaction.
1. **Add your data**: Azure AI Foundry portal supports providing the deployed models with external data, allowing for better search and context.
1. **Parameters**: This tab contains the models detailed settings, such as temperature.
1. **Chat Box**: The chat box is where we will see our interactions with the model in the form of chat messages.
1. **Prompt Box**: This is where we type the prompts we want to send to the model.

### Images Playground

Navigate back to Playgrounds, select the **Image playground** and click **Try the Image Playground.** This option allows you to work with image generation

![Image of Azure AI Foundry Playground Images Mode](./Images/aifoundry-image-playground.jpeg)

1. **Deployments**: In this drop-down we are able to choose the model to prompt for image generation. These models, just like the chat ones, come from our deployments.
1. **Prompt Box**: Similar to the chat playground's box, this is where the models get their input from the user. In the case of images, descriptions of what we want to generate.
1. **Results Box**: Finally, here is where the generated images are displayed.

### Real-time audio playground

Navigate back to Playgrounds, then select the **Real-time audio playground** and click **Try the Real-time audio Playground.** This feature allows you to engage with and test various AI models in an audio conversational format.

![Image of Azure AI Foundry Playground Real time audio mode](./Images/aifoundry-real-time-audio.jpeg)

1. **Deployment**: This section allows us to change between our deployed models.
1. **Server turn detection**: Determines if the server should utilize voice activity detection (VAD) to identify when a user has finished speaking.
1. **System Message Box**: Here is where we enter instructions for the model, previous to the user interaction.
1. **Choose a voice**: gpt-4o-realtime offers a variety of voices to choose from with unique accents or tonal capabilities tailored to your liking.
1. **Server turn detection**: additional parameters to help optimize the model's efficiency and performance by improving voice activity detection.
1. **Parameters**: This tab contains the models detailed settings, such as temperature and max response.
1. **Prompt Button**: Similar to the chat playground's box, this is where the models get their input from the user. 

## Agents playground

In the Navigation bar, select **Agents**. This feature provides you with the tools to build, test, and customize AI-driven agents.

![Image of Azure AI Foundry Playground Agents Mode](./Images/agents-playground-pt1.jpeg)

Once you _create your first Agent_ you will see the UI components as follows:
1. **Agent id and name:** Here you can give your Agent a name.
1. **Deployment**: In this drop-down we are able to choose the model to prompt for image generation. These models, just like the chat ones, come from our deployments.
1. **Instructions Box:** Here is where we enter instructions for the model, previous to the user interaction.

![](Images/agents-playground-pt2.jpeg)

4. **Knowledge:** Knowledge gives the agent access to data sources for grounding responses.
1. **Actions:** Enhance the agent's capabilities by allowing it to run various tools at runtime.
1. **Model settings**: This tab contains the models detailed settings, such as temperature and Top P.
1. **Prompt Box:** Similar to the chat playground's box, this is where the models get their input from the user. 

## Ready to start

That covers the necessary setup and basics of Azure AI Foundry portal . We will now move forward to begin interacting with the models. 

- Navigate to the  **playgrounds** select the **Chat playground** and click **Try the Chat Playground.**  
- In the _instructions tab_, Click Next to proceed to Part 1: Text Generation

Click **Next** to proceed to the Text Generation section.