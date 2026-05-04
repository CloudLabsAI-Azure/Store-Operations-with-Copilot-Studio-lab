# Store Operations with Microsoft Copilot Studio

### Overall Estimated Duration : 3 Hours

## Overview

This hands-on lab guides participants through building and automating a store operations agent using Microsoft Copilot Studio. Participants will explore ingesting and indexing product catalogs, policy documents, website content and servicedesk data. The lab covers customizing knowledge topics and automating workflows for product search, order placement, Dataverse logging, and SharePoint HelpDesk ticket creation. Additionally, participants will learn to publish their finished agent to channels such as Microsoft Teams or a web portal.

## Objective

Learn to build and automate a store operations agent using Microsoft Copilot Studio, using AI models like text embeddings, language models, and generative AI. By the end of this lab, you will:

- **Setting up Pre-Requisites for Store operations Agent:** Set up your Power Platform tenant, enable the Copilot Studio free trial, configure Dataverse permissions, and create a SharePoint IT HelpDesk site for ticket management.

- **Create Store-Operations Agent in Copilot Studio:** Create a new Copilot Studio agent, assign it a name and description, and connect initial knowledge sources (product catalog, policy docs, website content).

- **Build Advanced AI Workflows for Orders & Tickets:** Extend your agent with retrieval-augmented prompts, configure actions to record orders in Dataverse, and integrate SharePoint HelpDesk to auto-create support tickets.

- **Deploy & Publish Your Agent to Microsoft Teams:** Publish your completed agent into a Teams channel, then validate end-to-end functionality including product lookup, order placement, and ticket creation directly within Teams.

## Pre-requisites

Participants should have the following prerequisites:

- **Familiarity with Azure Resources:** Basic understanding of Azure services and the Azure portal for managing cloud resources.

- **Knowledge of Copilot Studio:** Familiarity with Copilot Studio and its capabilities for building AI-driven solutions.

## Architecture

The architecture enables end-to-end store operations automation by ingesting, processing, indexing, and interacting with multiple data sources in Copilot Studio. Product catalogs, policy documents, and website content are ingested as knowledge sources. Workflow actions like placing orders in Dataverse and creating tickets in SharePoint HelpDesk are configured in the agent via Copilot Studio's action framework. Finally, the agent is published into a Microsoft Teams channel, providing conversational store operations support where your staff already collaborate.

## Architecture Diagram

![](./media/store-ops-archi-v2.png)

## Explanation of Components

The architecture for this lab involves several key components:

- **Copilot Studio:** Handles user interaction by connecting to Azure AI Search for Q&A and other workflows. It provides an interface for using indexed data and AI capabilities in real-time.

- **SharePoint HelpDesk:** Manages support and incident workflows using the SharePoint IT HelpDesk site template. The Copilot Studio agent uses the SharePoint connector to automatically create, track, and manage support tickets in the Tickets list based on user requests or operational alerts.

- **Dataverse:** Acts as the centralized, low-code data backend for transactional records. It stores order entries, inventory updates, and other structured data. The Copilot Studio agent uses Dataverse actions to create, read, update, and delete records as part of automated store operations workflows.

## Getting Started with Lab

Welcome to Store Operations with Microsoft Copilot Studio Hands-On-Lab! We've prepared an environment for you to explore and learn. Let's begin by making the most of this experience.

### Accessing Your Lab Environment

Once you're ready to dive in, your virtual machine and Lab guide will be right at your fingertips within your web browser.

![](./media/gs1.png)

### Exploring Your Lab Resources

To get a better understanding of your Lab resources and credentials, navigate to the Environment tab.

![](./media/gs2.png)

### Utilizing the Split Window Feature

For convenience, you can open the Lab guide in a separate window by selecting the **Split Window** button from the top-right corner.

![](./media/gs3.png)

### Managing Your Virtual Machine

Feel free to start, stop, or restart your virtual machine as needed from the Resources tab. Your experience is in your hands!

![](./media/gs4.png)

## Let's Get Started with Power Apps Portal

1. In the JumpVM, select the **Microsoft Edge** browser shortcut on the desktop.

   ![](./media/zgr-gt.png)

1. Open a new browser tab and navigate to the Power Apps portal by entering the following URL:

   ```
   https://make.powerapps.com/
   ```

1. On the **Sign into Microsoft** tab, enter the following email **(1)** in the email field, and then select **Next (2)** to proceed.

   - Email: **<inject key="AzureAdUserEmail"></inject>**

     ![](./media/gs-lab3-g2.png)

1. On the **Enter Temporary Access Pass** screen, enter the following **Temporary Access Pass**, and then select **Sign in (2)**.

   - Temporary Access Pass: **<inject key="AzureAdUserPassword"></inject>**

     ![](./media/gs-lab3-g3.png)
     
1. If you see the pop-up **Stay Signed in?**, select **No**.

   ![](./media/gs-4.png)

1. If the **Welcome to Power Apps** pop-up appears, leave the default country/region selection and select **Get started**.

   ![](./media/gs-travel-g1.png)

1. You have now successfully logged in to the Power Apps portal. Keep the portal open.

   ![](./media/gs-5.png)

   > **Note:** We are signing in to the Power Apps portal because it automatically assigns a Developer license, which is required to create and use a Developer environment in the next steps.

1. In the Power Apps portal, select **Tables (1)** from the left menu and select **Create a database (2)**.

   ![](./media/ex3img71.png)

   >**Note:** If you are not able to see **Create Database** option and you are able to see some tables already, please continue from **Step 10**.

1. In the new pane for creating a new database, select **Create my Database**.

   ![](./media/ex3img72up.png)

1. Once done, select **Create with Excel or .CSV file**.

   ![](./media/st-store-ex1-g2.png)

1. In the pop-up window to create an environment, select **Create**. This will create a new Power Platform developer environment.

   > **Note:** If you see a message stating you don’t have permission to create here, wait for a few minutes and refresh the page, as it may take some time for the environment to be ready.
   
1. If you are directly navigated to the **Upload an Excel or .CSV file pane**, please cancel the process.

1. Open a new browser tab and navigate to the Power Platform admin center by entering the following URL:

   ```
   https://admin.powerplatform.microsoft.com
   ```

1. In the **Power Platform admin center**, select **Manage (1)**, choose **Environments (2)**, and then select **ODL_User <inject key="DeploymentID" enableCopy="false"/>'s Environment (3)**.

   ![](./media/uppowadminimg1.png)

   >Note: If you’re unable to see any environments, it may still be getting created in the background. This is expected behavior in Power Platform. Please wait 15–20 minutes and refresh the page to view the environment.

1. On the environment page, select **See all** under **S2S apps**.

   ![](./media/pro-activ-gg-g3.png)

1. In the next pane, select **+ New app user**.

   ![](./media/uppowadminimg3.png)

1. In the **Create a new app user** pane, under **App**, select **+ Add an app**.

   ![](./media/pro-activ-gg-g4.png)

1. In the **Add an app from Microsoft Entra ID** pane, enter the URL provided below in the search box **(1)**, select the app from the results **(2)**, and then select **Add (3)**.

   ```
   https://cloudlabssandbox.onmicrosoft.com/cloudlabs.ai/
   ```

   ![](./media/pro-activ-gg-g5.png)

1. Under Business Unit, click on the text input field to view the available options, and then select any one of the listed business units.

   ![](./media/pro-activ-gg-g6.png)

1. Next to **Security roles**, select the **Edit** icon.

   ![](./media/pro-activ-gg-g7.png)

1. In the **Sync Permissions** pane, select **System Administrator (1)**, and then select **Save (2)**.

   ![](./media/pro-activ-gg-g8.png)

1. In the pop-up window, select **Save**.

   ![](./media/pro-activ-gg-g9.png)

1. Review all the details and select **Create**.

   ![](./media/pro-activ-gg-g10.png)

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to assist you at any time. We offer dedicated support channels for both learners and instructors, ensuring that all your needs are promptly addressed. Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, select **Next** in the lower-right corner to move to the next page.

## Happy Learning!!

