# Store Operations with Microsoft Copilot Studio

### Overall Estimated Duration : 3 Hours

## Overview

This hands‑on lab guides participants through building and automating a smart store‑operations agent using Microsoft Copilot Studio. Participants will explore ingesting and indexing product catalogs, policy documents, website content and service‑desk data while leveraging AI models like text embeddings, language models and generative AI. The lab will cover customizing knowledge topics and automating workflows for product search, order placement, Dataverse logging and ServiceNow ticket creation. Additionally, participants will learn to publish their finished agent to custom channels such as Microsoft Teams or a web portal.

## Objective

Learn to build and automate a smart store‑operations agent using Microsoft Copilot Studio, leveraging AI models like text embeddings, language models, and generative AI. By the end of this lab, you will:

- **Setting up Pre-Requisites for Store operations Agent:** Understand how to set up your Power Platform tenant, enable the Copilot Studio free trial, and configure Azure AI and Dataverse permissions.

- **Create Store‑Operations Agent in Copilot Studio:** Get insights on spinning up a new Copilot Studio agent, assigning it a name and description, and connecting initial knowledge sources (product catalog, policy docs, website content).

- **Build Advanced AI Workflows for Orders & Tickets:** Understand how to extend your agent with retrieval‑augmented prompts, configure actions to record orders in Dataverse, and integrate ServiceNow to auto‑create support tickets.

- **Deploy & Publish Your Agent to Microsoft Teams:** Get insights on packaging and publishing your completed agent into a Teams channel, then validating end‑to‑end functionality—product lookup, order placement, and ticket creation—directly within Teams.

## Pre-requisites

Participants should have the following prerequisites:

- **Familiarity with Azure Resources:** Basic understanding of Azure services and the Azure portal for managing cloud resources.

- **Knowledge of Copilot Studio:** Familiarity with Copilot Studio and its capabilities for building AI-driven solutions.

## Architecture

The architecture enables end‑to‑end store operations automation by seamlessly ingesting, processing, indexing, and interacting with multiple data sources in Copilot Studio. Product catalogs, policy documents, and website content are ingested as Knowldege source. Workflow actions—such as placing orders in Dataverse and opening tickets in ServiceNow are wired into the agent via Copilot Studio’s action framework. Finally, the fully indexed, action‑enabled agent is published into a Microsoft Teams channel  delivering intuitive, conversational store‑operations support directly where your staff already collaborate.

## Architecture Diagram

![](./media/arch-v2.png)

## Explanation of Components

The architecture for this lab involves several key components:

- **Copilot Studio:** Facilitates user interaction by connecting to Azure AI Search for Q&A and other workflows. It provides an intuitive interface for leveraging indexed data and AI capabilities in real-time.

- **ServiceNow:** Manages support and exception workflows by exposing ticket‑creation and incident‑management APIs. The Copilot Studio agent invokes ServiceNow actions to automatically open, update, and track service tickets based on user requests or operational alerts.

- **Dataverse:** Acts as the centralized, low‑code data backend for transactional records. It stores order entries, inventory updates, and other structured data; the Copilot Studio agent uses Dataverse actions to create, read, update, and delete records as part of automated store‑operations workflows.

## Getting Started with Lab

Welcome to Store Operations with Microsoft Copilot Studio Hands-On-Lab! , We've prepared a seamless environment for you to explore and learn. Let's begin by making the most of this experience.

### Accessing Your Lab Environment

Once you're ready to dive in, your virtual machine and Lab guide will be right at your fingertips within your web browser.

![](./media/gs1.png)

### Exploring Your Lab Resources

To get a better understanding of your Lab resources and credentials, navigate to the Environment tab.

![](./media/gs2.png)

### Utilizing the Split Window Feature

For convenience, you can open the Lab guide in a separate window by selecting the Split Window button from the Top right corner

![](./media/gs3.png)

### Managing Your Virtual Machine

Feel free to start, stop, or restart your virtual machine as needed from the Resources tab. Your experience is in your hands!

![](./media/gs4.png)

## Let's Get Started with Azure Portal

1. In the JumpVM, click on **Azure portal** shortcut of Microsoft Edge browser which is created on desktop.

   ![](./media/gs-8.png)

1. On the **Sign into Microsoft Azure** tab, you will see the login screen. Enter the provided email or username, and click **Next** to proceed.

   - Email/Username: <inject key="AzureAdUserEmail"></inject>

     ![](./media/gs-6.png)

1. Now, enter the following password and click on **Sign in**.

   - Password: <inject key="AzureAdUserPassword"></inject>

     ![](./media/gs-7.png)

     >**Note:** If you see the Action Required dialog box, then select Ask Later option.
     
1. If you see the pop-up **Stay Signed in?**, click No.

1. If you see the pop-up **You have free Azure Advisor recommendations!**, close the window to continue the Lab.

1. If a **Welcome to Microsoft Azure** popup window appears, click **Cancel** to skip the tour.

## Support Contact

The CloudLabs support team is available 24/7, 365 days a year, via email and live chat to ensure seamless assistance at any time. We offer dedicated support channels tailored specifically for both learners and instructors, ensuring that all your needs are promptly and efficiently addressed.Learner Support Contacts:

- Email Support: cloudlabs-support@spektrasystems.com
- Live Chat Support: https://cloudlabs.ai/labs-support

Now, click on the **Next** from lower right corner to move on next page.

![](./media/gs-5.png)

## Happy Learning!!
