# PagerDuty + Kumologica Integration Benefits

* Connect and create incidents in PagerDuty from a serverless compute with zero coding.
* Create incidents based on the events from different enterprise systems integrated using Kumologica.
* Notify on-call responders based on alerts sent from Kumologica flow.
* Send enriched event data from Kumologica flow based on the rule condition that triggered the event.
* Incidents status are synchronized between PagerDuty and any enterprise system using webhook in PagerDuty and nodes in Kumologica.


# How it Works

* Kumologica PagerDuty node is triggered to create an incident based on the flow logic which is visually designed using Kumologica designer. 
* Flow logic decides the incident severity and status. 
* The flow logic takes input from enterprise system which checks the condition and triggers the PagerDuty node. These enterprise systems are connected using Kumologica supported nodes. 


# Requirements

1. PagerDuty integration requires [Admin base](https://support.pagerduty.com/docs/user-roles) role in PagerDuty to create a [service](https://support.pagerduty.com/docs/services-and-integrations#section-events-API-v2) and retrieve the associated **integration key** or **routing key**. The routing key is used by Kumologica PagerDuty node for authorization and to trigger the PagerDuty service to create an incident.
2. [Download](https://kumologica.com/download.html) and [install](https://docs.kumologica.com/docs/guide/GettingStarted.html#installation) Kumologica Designer.

# Support

If you need help with this integration, please contact on **support@kumologica.com** or **contact@kumologica.com**. 

# Integration Walkthrough

## In PagerDuty

### Integrating With a PagerDuty Service
1. From the **Configuration** menu, select **Services**.
2. There are two ways to add an integration to a service:
   * **If you are adding your integration to an existing service**: Click the **name** of the service you want to add the integration to. Then, select the **Integrations** tab and click the **New Integration** button.
   * **If you are creating a new service for your integration**: Please read our documentation in section [Configuring Services and Integrations](https://support.pagerduty.com/docs/services-and-integrations#section-configuring-services-and-integrations) and follow the steps outlined in the [Create a New Service](https://support.pagerduty.com/docs/services-and-integrations#section-create-a-new-service) section, selecting **Event API v2** as the **Integration Type** in step 4. Continue with the ***Event API v2***  section (below) once you have finished these steps.
3. Enter an **Integration Name** in the format `monitoring-tool-service-name` (e.g.  ***Kumologica***-Shopping-Cart) and select  ***Event API v2***  from the Integration Type menu.
4. Click the **Add Integration** button to save your new integration. You will be redirected to the Integrations tab for your service.
5. An **Integration Key** will be generated on this screen. Keep this key saved in a safe place, as it will be used when you configure the integration with  ***Kumologica***  in the next section.
![](https://pdpartner.s3.amazonaws.com/ig-template-copy-integration-key.png)

## In ***Kumologica***

There are two ways to add PagerDuty node to Kumologica flow:

### To install the node from designer

* Go to `Add more nodes` option on the palette section of the designer.
* Check for the PagerDuty node and click install.
* Once installed, the designer is required to be restarted.

### To install the node from CLI

Go to your project workspace where you can see your package.json file.
Run the below give npm command.

`npm i @kumologica/kumologica-contrib-pagerduty`

***Verify installation***

Once installed, the PagerDuty node will visible under ***Platforms*** category in the pallette. 

### How to configure the PagerDuty node

1. Drag and drop the PagerDuty node from the pallette to the canvas. 
2. Wire the node to the appropriate section of your flow where the triggering of PagerDuty node is expected in order to create the incident.
![](https://playground.kumologica.com/PagerDutyFlow.png)
3. Double click the PagerDuty node to open the ***Settings***. 
4. On the setting, provide the `Integration Key` generated in the Step 5 of PagerDuty service creation to the `Routing Key` property field of PagerDuty node.
5. Provide rest of the property fields according to the incident details and status as per business requirement.
![](https://playground.kumologica.com/PagerDutyNodeConfig.png)

For more details related to the node properties use the following [link](https://docs.kumologica.com/docs/references/PagerDuty.html)

# How to Uninstall

### In Kumologica

Use the following command to uninstall the PagerDuty node from the flow.

`npm uninstall @kumologica/kumologica-contrib-pagerduty`

### In PagerDuty

1. From the ***configuration*** menu, select Services.
2. Click the **name** of the service you have used for integration.
3. On the service, go to integration tab and select the gear icon of ***Events API V2***.
4. Click on `Delete Integration`.