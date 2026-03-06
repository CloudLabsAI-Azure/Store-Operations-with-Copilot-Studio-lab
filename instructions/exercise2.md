# Exercise 2: Create Store‑Operations Agent in Copilot Studio

### Estimated Duration: 45 Minutes

## Overview

In this exercise, you will create a Copilot Studio agent that will serve as the foundation for your store operations assistant. You will define the agent’s purpose by assigning it a name and description, and connect it to key knowledge sources such as the product catalog, store policy documents, and website content. These steps will enable your agent to deliver relevant, AI-powered responses based on indexed information.

## Objectives

You will be able to complete the following tasks:

- Task 1: Creating a store-operations agent in Copilot Studio

- Task 2: Adding knowledge sources to the agent

## Task 1: Creating a store-operations agent in Copilot Studio

In this task, you will create a new agent in Microsoft Copilot Studio by defining its name, description, and basic configuration settings. This agent will serve as the base for enabling intelligent store operations.

1. Navigate back to Copilot Studio page from the browser.

1. From **Environment (1)**, expand **Supported environments (2)** and select **ODL_User <inject key="Deployment ID"/>'s Environment (3)** to ensure you are in the ODL environment.

   ![](./media/st-store-gs-g2.png)

1. From the left navigation pane, select **Agents (1)** and then choose **Create blank agent (2)**.

   ![](./media/st-store-ex2-g1.png)

1. Wait until the **Getting things ready...** process completes and the agent configuration page loads.

   ![](./media/st-store-ex2-g2.png)

1. Wait until the message **Your agent has been provisioned.** appears on the **Overview** page.

   ![](./media/st-store-ex2-g3.png)

1. On the **Overview** page, select **Edit**.

   ![](./media/st-store-ex2-g4.png)

1. Enter the agent name in the **Name (1)** field, add the description in the **Description (2)** box, then click **Save (3)** to apply the changes.

   | Field | Value |
   |-------|-------|
   | Name | `StoreOps Assistant` |
   | Description | `StoreOps Assistant is your intelligent store operations companion. It helps staff quickly find products, understand store policies, place orders, and create support tickets, all through conversational AI. Integrated with Dataverse, Freshworks, and knowledge sources, this assistant streamlines everyday retail workflows with speed and accuracy.` |

   ![](./media/st-store-ex2-g5.png)

1. Click **Edit** to update the agent instructions.

   ![](./media/st-store-ex2-g6.png)

1. Enter the agent instructions in the **Instructions (1)** box, then click **Save (2)** to apply the changes.

   ```
   You are an AI-powered assistant designed to support store operations staff. Help staff with:
   - Searching for products from the catalog using natural language
   - Providing accurate answers using connected knowledge sources such as store policies and website content
   - Assisting in placing orders and logging them in Dataverse
   - Creating and tracking support tickets in Freshworks when issues arise
   - Answering general store operations questions

   Always respond in a clear, friendly, and professional tone. Use concise language and provide helpful follow-up suggestions when appropriate. If a request is unclear, ask clarifying questions before proceeding.
   ```

   ![](./media/st-store-ex2-g7.png)

1. You have successfully created the StoreOps Assistant. In the next steps of this lab, you will enhance it further by adding knowledge sources and advanced features.

## Task 2: Adding knowledge sources to the agent

In this task, you will connect knowledge sources such as the product catalog, policy documents, and store website content to your agent, allowing it to provide AI-powered answers using Retrieval-Augmented Generation (RAG).

1. Click **+ Add knowledge** to add data and resources to the agent.

   ![](./media/st-store-ex2-g8.png)

1. In the next pane, click on **select to browse** option as shown and in the pop up window to select files, navigate to `C:\datasets\Store-Operations-with-Copilot-Studio-lab-datasets\Fabrikam Returns Policy for Customers` file.

   ![](./media/ex2img5.png)

1. In the next pane, review that the **Fabrikam Returns Policy for Customers (1)** file is selected and click on **Add to agent (2)**.

   ![](./media/copil-g-10.png)

1. Once done, again click on **+ Add knowledge**.

   ![](./media/ex2img8new.png)

1. In the next pane, select **Dataverse** as knowledge source.

   ![](./media/ex2img14.png)

1. From the list, search and select **Order** and **Product** tables. Click on **Add to agent**.

   ![](./media/copil-g-11.png)

   >**Note:** If you are seeing **Product Record** table, instead of **Product **, please proceed with the **Product Record** Table.

   >**Note:** If you are seeing **Order Record** table, instead of **Order**, please proceed with the **Order Record** Table.

1. Once done, again click on **+ Add knowledge**.

   ![](./media/ex2img8new.png)

1. In the next pane, select **Public Websites** as knowledge source.

   ![](./media/ex2img17.png)

1. For **Public website link** add `https://prod.fabrikam.com` and click on **Add**.

   ![](./media/ex2img24.png)

   >Note: This is a sample E-Commerce website from Microsoft.

1. Once done, click on **Add to agent** in the next pane.

   ![](./media/copil-g-12.png)

1. You have now successfully added all the necessary data as a knowledge source for this agent.

1. Select **Overview (1)** tab from top menu, scroll down to **Knowledge** and make **Allow the AI to use its own general knowledge** option as **Disabled (2)**.

   ![](./media/ex2img26.png)

1. To test if the agent is ingested with knowledge or not, use the right message box to test the agent with some sample prompts given below:

   - `what all products are available in inventory?`
   - `List out all the previous orders with the product name?`

     ![](./media/ex2img22.png)

     ![](./media/ex2img23.png)

<validation step="a705bde5-f070-4276-959d-11df80a6d264" />
 
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

## Summary

In this exercise, you created a Copilot Studio agent that served as the foundation for your store operations assistant. You defined the agent’s purpose by assigning it a name and description, and connected it to key knowledge sources such as the product catalog, store policy documents, and website content. These steps enabled the agent to deliver relevant, AI-powered responses based on indexed information.

### You have successfully completed this exercise, please continue to next one >>
