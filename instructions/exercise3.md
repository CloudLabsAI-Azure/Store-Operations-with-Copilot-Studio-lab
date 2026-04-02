# Exercise 3: Build Workflows for Orders and Tickets

### Estimated Duration: 60 Minutes

## Overview

In this exercise, you will enhance your StoreOps Assistant by building workflows that go beyond static knowledge responses. You will create topics that allow users to place orders and request support, while integrating your agent with Microsoft Dataverse and SharePoint HelpDesk. These additions will let your assistant perform end-to-end operations such as order recording and ticket creation for real-world store operations.

## Objectives

You will be able to complete the following tasks:

- Task 1: Create a topic to record orders in Dataverse

- Task 2: Create a "Support Ticket" topic and integrate with SharePoint HelpDesk

## Task 1: Create a topic to record orders in Dataverse

In this task, you will create a topic that allows users to place product orders using the StoreOps Assistant. The topic will collect details such as the product name, quantity, and delivery preferences. Once the user confirms the order, the assistant will trigger an action to store the order details in a Microsoft Dataverse table. This allows tracking and management of customer orders within your store's database.

1. In Copilot Studio, select the **Topics (1)** tab from the top menu, select **+ Add a topic (2)**, and then select **From blank**.

   ![](./media/st-store-ex3-g1.png)

1. Once you are in the designer, on the **Trigger** node, add the description below.

   ```
   This topic helps user to place orders or buy products
   ```

   ![](./media/st-store-ex3-g2.png)

1. Select **+** to add a new node.

   ![](./media/st-store-ex3-g3.png)

1. From the node options, select **Ask a question**.

   ![](./media/st-store-ex3-g4.png)
   
   >**Note:** In Microsoft Copilot Studio, the "Ask a question" node is used to collect specific information from the user during a conversation. It prompts the user with a question and captures their response, which is then stored in a variable for later use in the flow.

1. In the **Question** node, enter the following text in the message box.

   ```
   Which product would you like to order?
   ```

   ![](./media/st-store-ex3-g5.png)

1. Once done, change the identifier from **Multiple choice Options** to **User's entire response**. Select **> (1)** as shown and select **User's entire response (2)**.

   ![](./media/st-store-ex3-g6.png)

1. Now, select **Var1** as we have to change the variable name.

   ![](./media/st-store-ex3-g7.png)

1. In the **Variable properties** pane, enter **ProductName (1)** under **Variable name**, and then select **Close (2)**.

   ![](./media/st-store-ex3-g8.png)

1. Select **+** to add a new node below the **Question** node.

   ![](./media/st-store-ex3-g9.png)

1. From the node options, select **Add a condition**.

   ![](./media/st-store-ex3-g10.png)

1. For condition the agent will check the product that user shared is present in the list or catalogue or not, for now you will be adding a sample list directly as condition.

1. In the **Condition** node, select **Select a variable (1)** and choose **ProductName (2)**.

   ![](./media/st-store-ex3-g11.png)

1. In the **Condition** node, select the dropdown **(1)** and choose **in (2)**.

   ![](./media/st-store-ex3-g12.png)

1. In the **Condition** node, enter the following list of products in the value field.

   ```
   Tailwind Sneakers, Performance Hoodie, All-Weather Jacket, Pro-Grip Running Shorts, Trailblazer Backpack, Hydration Water Bottle, Endurance Sports Socks, Reflective Safety Vest, Galaxy Fitness Tracker, UltraLight Yoga Mat
   ```

   ![](./media/st-store-ex3-g13.png)

1. Under **All other conditions**, select **+** to add a new node.

   ![](./media/st-store-ex3-g14.png)

1. From the node options, select **Send a message**.

   ![](./media/st-store-ex3-g15.png)

1. In the **Message** node, enter the following text.

   ```
   The product is not available, please look for other products we have!
   ```

   ![](./media/st-store-ex3-g16.png)

1. Below the **Message** node, select **+** to add a new node.

   ![](./media/st-store-ex3-g17.png)

1. Once done, add one more node below that. From the list, select **Topic management (1)** and select **Go to step (2)**.

   ![](./media/st-store-ex3-g18.png)

1. Once after selecting that option, you have to select a node so that the flow will be navigated to that particular step directly.

1. Select the first **Question** node to select product as the Go to Step node.

   ![](./media/st-store-ex3-g19.png)

1. Once done, the flow looks like this.

   ![](./media/st-store-ex3-g20.png)

1. As the Other conditions are configured, now you have to continue building the flow further.

1. Under the **Condition** node, select **+** to add a new node.

   ![](./media/st-store-ex3-g21.png)

1. From the node options, select **Ask a question**.

   ![](./media/st-store-ex3-g22.png)

1. In the **Question** node, enter the following text.

   ```
   Please specify the quantity you require
   ```

   ![](./media/st-store-ex3-g23.png)

1. Under **Identify**, select **Multiple choice options (1)** and choose **Number (2)**.

   ![](./media/st-store-ex3-g24.png)

1. Now, select **Var1** as we have to change the variable name.

   ![](./media/st-store-ex3-g25.png)

1. In the **Variable properties** pane, enter **Quantity (1)** under **Variable name**, and then select **Close (2)**.

   ![](./media/st-store-ex3-g26.png)

1. Select **+** to add a new node.

   ![](./media/st-store-ex3-g27.png)

1. From the node options, select **Ask a question**.

   ![](./media/st-store-ex3-g28.png)

1. In the **Question** node, enter the following text.

   ```
   Please provide your name
   ```

   ![](./media/st-store-ex3-g29.png)

1. Under **Identify**, select **Multiple choice options (1)** and choose **User's entire response (2)**.

   ![](./media/st-store-ex3-g30.png)

1. Under **Save user response as**, select **Var1** to rename the variable so the user's name can be stored for later use in the flow.

   ![](./media/st-store-ex3-g31.png)

1. In the **Variable properties** pane, enter **UserName (1)** under **Variable name**, and then select **Close (2)**.
   ![](./media/st-store-ex3-g32.png)

1. Select **+** to add a new node.

   ![](./media/st-store-ex3-g33.png)

1. From the node options, select **Ask a question**.

   ![](./media/st-store-ex3-g34.png)

1. In the **Question** node, enter the following text to collect the delivery details.

   ```
   Please provide your delivery address
   ```

   ![](./media/st-store-ex3-g35.png)

1. Under **Identify**, select **Multiple choice options (1)** and choose **User's entire response (2)**.

   ![](./media/st-store-ex3-g36.png)

1. Under **Save user response as**, select **DeliveryAddress (1)**, enter **DeliveryAddress (2)** under **Variable name**, and then select **Close (3)**.

   ![](./media/st-store-ex3-g37.png)

1. From the top menu, select **Save** to save the topic.

   ![](./media/st-store-ex3-g38.png)

1. In the **Save your topic** dialog, enter the following name for the topic, and then select **Save (2)**.

   ```
   Place Orders
   ```

   ![](./media/st-store-ex3-g39.png)

1. Now that you have successfully created the flow to collect the order details, you need to create an agent flow (formerly known as Action) to add these order details to the Dataverse table.

## Task 2: Define an Agent Flow to Insert Order Details into Dataverse

In this task, you will create an action that inserts the collected order details, such as customer name, product name, and delivery address into a Dataverse table. This Agent Flow will be triggered by the topic you created earlier and will handle the data insertion into the appropriate table within Microsoft Dataverse.

1. From the left navigation pane, select **Flows (1)** and then choose **New agent flow (2)** to create a flow that will store order details in Dataverse.

   ![](./media/st-store-ex3-g40.png)

1. In the **Add a trigger** pane, search for **when an agent calls the flow (1)** and select **When an agent calls the flow (2)**.

   ![](./media/st-store-ex3-g41.png)

   > **Note:** After searching, you may need to scroll down to locate the **When an agent calls the flow** option in the results.

1. In the **When an agent calls the flow** node, select **Add an input** to add input parameters.

   ![](./media/st-store-ex3-g42.png)

1. Under **Choose the type of user input**, select **Text**.

   ![](./media/st-store-ex3-g43.png)

1. In the **When an agent calls the flow** node, enter the following input name under **Text (1)**, and then select **Add an input (2)**.

   ```
   UserName
   ```

   ![](./media/st-store-ex3-g44.png)

1. Under **Choose the type of user input**, select **Text**.

   ![](./media/st-store-ex3-g45.png)

1. In the **When an agent calls the flow** node, add the following input names so the flow can receive the values collected from the topic.

   ```
   ProductName
   ```

   ```
   DeliveryAddress
   ```

   ![](./media/st-store-ex3-g46.png)

   >**Note:** Here you will just be creating reference variables, as you will pass the actual variables further in this task.

1. In the **When an agent calls the flow** node, select **Add an input** to add another parameter.

   ![](./media/st-store-ex3-g47.png)

1. Under **Choose the type of user input**, select **Number**.

   ![](./media/st-store-ex3-g48.png)

1. Provide the following name as the **Input name**.

   ```
   Quantity
   ```

   ![](./media/ex3img37.png)

1. Once completed, the variables will look like this.

   ![](./media/st-store-ex3-g49.png)

1. Select **+** to add the next action to the flow, where you will configure the **Dataverse** operation.

   ![](./media/st-store-ex3-g50.png)

1. In the **Add an action** pane, search for **Microsoft Dataverse (1)** and then select **See more (2)**.

   ![](./media/st-store-ex3-g51.png)

1. From the **Microsoft Dataverse** actions list, select **Add a new row**.

   ![](./media/st-store-ex3-g52.png)

1. In the **Create a new connection** pane, enter the following value for **Connection name (1)**, ensure **Oauth (2)** is selected under **Authentication Type**, and then select **Sign in (3)**.

   ```
   Microsoft Dataverse
   ```

   ![](./media/st-store-ex3-g53.png)

   > **Note:** If the sign-in pop-up does not appear, check your browser address bar and allow pop-ups for **copilotstudio.microsoft.com**, then select **Done** and try signing in again.

1. In the **Pick an account** window, select the lab user account to sign in.

   ![](./media/st-store-ex3-g55.png)

1. In the **Confirmation required** page, select **Allow access** to grant permissions for the **Microsoft Dataverse** connection.

   ![](./media/st-store-ex3-g56.png)

1. In the **Add a new row** action, select **Order** in the **Table name** field.

   ![](./media/st-store-ex3-g57.png)

1. In the **Add a new row** action, expand **Advanced parameters (1)** and select **OrderID (2)** to add the field to the action.

   ![](./media/st-store-ex3-g58.png)

   > **Note:** If **OrderID** already appears by default in the action, you can directly configure it without selecting it from **Advanced parameters**.

1. In the **OrderID (1)** field, select **fx (2)** to add an expression for generating a unique order identifier.

   ![](./media/st-store-ex3-g59.png)

1. In the expression editor, enter the following expression **(1)** to generate a **Globally Unique Identifier (GUID)** for the order, and then select **Add (2)**.

   ```
   guid()
   ```

   ![](./media/st-store-ex3-g60.png)

1. In **Advanced parameters (1)**, expand the list and select

   - **CustomerName**
   - **DeliveryAddress**
   - **ProductName**
   - **Quantity**
   - **Status**

      ![](./media/st-store-ex3-g61.png)

1. In the **CustomerName (1)** field, select the **dynamic content icon (2)** to insert the value from the flow inputs.

   ![](./media/st-store-ex3-g62.png)

1. From the **Dynamic content** pane, select **UserName** to populate the **CustomerName** field.

   ![](./media/st-store-ex3-g63.png)

1. Repeat the same steps for other parameters **(1)** and select **Pending (2)** as the value for the **Status** field.

   ![](./media/st-store-ex3-g64.png)

1. From the top-right corner, select **Publish** to save the agent flow.

   ![](./media/st-store-ex3-g65.png)

1. On the **Overview (1)** tab, select **Edit (2)** to modify the agent flow details.

   ![](./media/st-store-ex3-g69.png)

1. In the **Details** pane, enter the following text in the **Flow name (1)** field, and then select **Save (2)**.

   ```
   Dataverse
   ```

   ![](./media/st-store-ex3-g70.png)

1. From the left navigation pane, select **Agents (1)** and then select your agent, **StoreOps Assistant (2)**.

   ![](./media/st-store-ex3-g66.png)

1. Select the **Topics (1)** tab from the top menu, and then select the **Place Orders (2)** topic.

   ![](./media/st-store-ex3-g67.png)

1. Select **+** to add a new node below the **Question** node.

   ![](./media/st-store-ex3-g68.png)

1. From the node options, select **Add a tool (1)** and then choose **Dataverse (2)** to integrate the agent flow into your topic.

   ![](./media/st-store-ex3-g71.png)

1. In the **Action** node, select the **... (1)** icon for the **UserName** parameter and choose the **UserName (2)** variable from the list.

   ![](./media/st-store-ex3-g72.png)

1. Repeat the same process for the **ProductName (1)** parameter and select the **ProductName (2)** variable.

   ![](./media/st-store-ex3-g73.png)

1. Repeat the same process for the **DeliveryAddress (1)** parameter and select the **DeliveryAddress (2)** variable.

   ![](./media/st-store-ex3-g74.png)

1. Repeat the same process for the **Quantity (1)** parameter and select the **Quantity (2)** variable.

   ![](./media/st-store-ex3-g75.png)

1. Select **+** to add a new node below the **Action** node.

   ![](./media/st-store-ex3-g76.png)

1. From the node options, select **Send a message**.

   ![](./media/st-store-ex3-g77.png)

1. In the **Message** node, enter the following text.

   ```
   Your order has been placed!
   ```

   ![](./media/st-store-ex3-g78.png)

1. From the top menu, select **Save** to save the topic.

   ![](./media/st-store-ex3-g79.png)

1. Now use the **Test** area in the right to validate the working of the flow.

1. Provide the prompts as given below and check the flow of the agent:

   - ```
     I want to place an order
     ```

     ![](./media/st-store-ex3-g80.png)
     
     >The agent will reply with a question to get the product details.

   - ```
     Galaxy Fitness Tracker
     ```

     ![](./media/st-store-ex3-g81.png)

     >The agent will ask a question to get the quantity of the order.
   
   - ```
     1
     ```

     ![](./media/st-store-ex3-g82.png)

     >The agent will ask to provide UserName

   - ```
     John
     ```

     ![](./media/st-store-ex3-g83.png)

     >Next, the agent will ask for delivery address.

   - ```
     1st Street, California
     ```
     
     ![](./media/st-store-ex3-g84.png)

     >Now the Action will run. It may take few seconds once done, you will get the acknowledgement.

     ![](./media/st-store-ex3-g85.png)

1. Now, to verify the creation of record inside the dataverse table, navigate back to power apps portal.

1. Once you are in the Power Apps portal, select **Tables (1)** from the left menu, and from the list, select the **Order (2)** table.

   ![](./media/st-store-ex3-g86.png)

1. Now, you can see that a record has been added with the details that you provided.

   ![](./media/st-store-ex3-g87.png)

1. You have successfully created a flow with an Action to manage order placements.

## Task 2: Create a "Support Ticket" topic and integrate with SharePoint HelpDesk

In this task, you will build a topic that lets users request support by creating a service ticket. The topic will gather information like the issue description and subject. Once the data is collected, the agent will connect to the SharePoint IT HelpDesk site and create a corresponding ticket in the Tickets list. This integration handles ticket creation without manual steps, keeping everything within the Microsoft 365 ecosystem.

1. You will now create a topic that integrates with the SharePoint IT HelpDesk site you set up earlier.

1. From the left navigation pane, select **Agents (1)** and then select your agent, **StoreOps Assistant (2)**.

   ![](./media/st-store-ex3-g66.png)

1. In Copilot Studio, select the **Topics (1)** tab from the top menu, select **+ Add a topic (2)**, and then select **From blank**.

   ![](./media/st-store-ex3-g1.png)

1. On the **Trigger** node, enter the following text in the **Describe what the topic does** field.

   ```
   This topic helps user to create tickets and raise their queries
   ```

   ![](./media/st-store-ex3-g88.png)

1. Select **+** below the **Trigger** node to add a new node.

   ![](./media/st-store-ex3-g89.png)

1. From the node options, select **Ask a question**.

   ![](./media/st-store-ex3-g90.png)

1. In the **Question** node, enter the following text in the message box.

   ```
   Kindly provide the subject for the ticket
   ```

   ![](./media/st-store-ex3-g91.png)

1. Under **Identify**, select **Multiple choice options (1)** and choose **User's entire response (2)**.

   ![](./media/st-store-ex3-g92.png)

1. Under **Save user response as**, select **Var1 (1)**, enter **Subject (2)** under **Variable name**, and then select **Close (3)**.

   ![](./media/st-store-ex3-g93.png)

1. Once done, select **+ (1)** to add a new node. From the list, select **Ask a question (2)**.

   ![](./media/st-store-ex3-g94.png)

1. In the **Question** node, enter the following text in the message box.

   ```
   Please provide a detailed description on the ticket
   ```

   ![](./media/st-store-ex3-g95.png)

1. From the top menu, select **Save** to save the topic.

   ![](./media/st-store-ex3-g96.png)

1. In the **Save your topic** dialog, enter the following name in the **Name your topic (1)** field, and then select **Save (2)**.

   ```
   Ticket Creation
   ```

   ![](./media/st-store-ex3-g97.png)

1. From the left navigation pane, select **Flows (1)** and then choose **+ New agent flow (2)**.

   ![](./media/st-store-ex3-g98.png)

1. In the **Add a trigger** pane, search for **when an agent calls the flow (1)** and select **When an agent calls the flow (2)**.

   ![](./media/st-store-ex3-g41.png)

   > **Note:** After searching, you may need to scroll down to locate the **When an agent calls the flow** option in the results.

1. In the **When an agent calls the flow** node, select **Add an input** to add input parameters.

   ![](./media/st-store-ex3-g42.png)

1. Under **Choose the type of user input**, select **Text**.

   ![](./media/st-store-ex3-g43.png)

1. In the **When an agent calls the flow** node, enter the following input name under **Text (1)**, and then select **Add an input (2)**.

   ```
   Subject
   ```

   ![](./media/st-store-ex3-g99.png)

1. Under **Choose the type of user input**, select **Text**.

   ![](./media/st-store-ex3-g100.png)

1. In the **When an agent calls the flow** node, enter the following input name under **Text (1)**, and then select **+ (2)**.

   ```
   Description
   ```

   ![](./media/st-store-ex3-g101.png)

   >**Note:** Here you will just be creating reference variables, as you will pass the actual variables further in this task.

1. Select **+** to add the next action to the flow, where you will configure the **SharePoint** operation.

1. In the **Add an action** pane, search for **SharePoint (1)** and then select **See more (2)**.

1. From the **SharePoint** actions list, select **Create item**.

1. In the **Create a new connection** pane, enter the following value for **Connection name (1)**, and then select **Sign in (2)**.

   ```
   SharePoint HelpDesk
   ```

   > **Note:** If the sign-in pop-up does not appear, check your browser address bar and allow pop-ups for **copilotstudio.microsoft.com**, then select **Done** and try signing in again.

1. In the **Pick an account** window, select the lab user account to sign in.

1. In the **Confirmation required** page, select **Allow access** to grant permissions for the **SharePoint** connection.

1. In the **Create item** action, under **Site Address**, from the dropdown select the IT HelpDesk site you created. If no values are shown in the dropdown, then manually enter the site address that you copied earlier.

   > **Note:** The Site Address should be in the format: `https://cloudlabssandbox.sharepoint.com/sites/Store-OP-<inject key="Deployment ID" enableCopy="false"></inject>`

1. Under **List Name**, select **Tickets**.

1. From the **Advanced Parameters** list, select **Title**, **Issue Description**, and **Priority Value**.

1. For the **Title** parameter, select the **Dynamic content** option and choose **Subject** from the trigger's input variables.

1. For the **Issue Description** parameter, select the **Dynamic content** option and choose **Description** from the trigger's input variables.

1. For the **Priority Value** parameter, select **High** from the dropdown.

   > **Note:** Leave the **Status** value as **New** (default).

1. Now, you have successfully set up your agent flow. Select **Publish** from the top-right corner to save the flow.

   ![](./media/st-store-ex3-g105.png)

1. On the flow page, ensure you are on the **Overview (1)** tab and select **Edit (2)** from the **Details** section.

   ![](./media/st-store-ex3-g106.png)

1. In the **Details** pane, enter the following name in the **Flow name (1)** field and then select **Save (2)**.

   ```
   SharePoint HelpDesk
   ```

1. From the left navigation pane, select **Agents (1)** and then select your agent, **StoreOps Assistant (2)**.

   ![](./media/st-store-ex3-g66.png)

1. From the top navigation menu, select **Topics (1)** and then choose the **Ticket Creation (2)** topic from the list.

   ![](./media/st-store-ex3-g108.png)

1. In **Action** node, select **+** below the **Description** question node to add a new node.

   ![](./media/st-store-ex3-g109.png)

1. From the node options, select **Add a tool (1)** and then choose **SharePoint HelpDesk (2)** to integrate the ticket creation flow.

1. Under **Power Automate inputs**, select the **... (1)** icon next to the **Subject (String)** field and choose the **Subject (2)** variable from the list.

   ![](./media/st-store-ex3-g111.png)

1. Under **Power Automate inputs**, select the **... (1)** icon next to the **Description (String)** field and choose the **Description (2)** variable from the list.

   ![](./media/st-store-ex3-g112.png)

1. Select **+** below the SharePoint HelpDesk action node and choose **Send a message**.

1. In the **Message** node, enter the following text in the message box.

   ```
   Thank you, your ticket has been successfully submitted.
   ```

   ![](./media/st-store-ex3-g114.png)

1. From the top menu, select **Save** to finalize the changes to your topic.

   ![](./media/st-store-ex3-g115.png)

1. Now use the **Test** area in the right to validate the working of the flow.

1. In the **Test your agent** pane, enter the following message in the chat box **(1)** and select the **Send** icon **(2)**.

   ```
   I want to create a ticket
   ```

   ![](./media/st-store-ex3-g116.png)

1. The agent will prompt you to provide a subject for the ticket. Enter the following text into the chat box **(1)** and select the **Send** icon **(2)**.

   ```
   Refund Not Received
   ```

   ![](./media/st-store-ex3-g117.png)

1. Again the agent will ask a question to get a description on the ticket. Provide the below description:

   ```
   I returned an order and requested for a refund . However, I have not yet received the refunded amount.
   The expected refund timeline has passed, and I would appreciate it if you could look into this matter. Please let me know if any additional information is required from my side.
   ```

   ![](./media/st-store-ex3-g118.png)

1. In the chat window, if prompted, select **Open connection manager** to verify and configure your credentials for the SharePoint integration.

   ![](./media/st-store-ex3-g119.png)

1. On the **Manage your connections** page, locate the **SharePoint** connection and select **Connect**.

1. On the **Create or pick connections** page, confirm that the **SharePoint** connection is selected and then select **Submit**.

1. Verify that the **Status** now shows as **Connected**.

1. Return to the chat window and select **Retry (1)** to trigger the ticket creation again. You will see a confirmation message stating that your ticket has been successfully submitted **(2)**.

   ![](./media/st-store-ex3-g123.png)

1. Navigate back to the **SharePoint IT HelpDesk** site and open the **Tickets** list. You can see that a new ticket with the subject **Refund Not Received** has been created.

1. To finalize all changes and make the agent live, navigate back to **Copilot Studio** and select **Publish** from the top-right corner of the page.

   ![](./media/st-store-ex3-g126.png)

1. On the **Publish this agent** dialog box, review the information and then select **Publish** to make your agent and its recent changes available to users.

   ![](./media/st-store-ex3-g127.png)

<validation step="09f5e08a-c2db-4bd9-add0-435e23d74659" />
 
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task. 
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help.

## Summary

In this exercise, you enhanced your StoreOps Assistant by building workflows that extended beyond static knowledge responses. You created topics that allowed users to place orders and request support, while integrating your agent with Microsoft Dataverse and SharePoint HelpDesk. These additions let your assistant perform end-to-end operations such as order recording and ticket creation for real-world store operations.

### You have successfully completed this exercise, please continue to next one >>
