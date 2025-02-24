---
title: Expose Your App to the Portal Service on Cloud Foundry
description: Create a launchpad module in SAP Web IDE to make your SAP Fiori app available for use in the Portal.
auto_validation: true
time: 20
tags: [ tutorial>beginner, topic>sapui5, products>sap-cloud-platform, topic>html5, topic>sapui5, products>sap-cloud-platform-for-the-cloud-foundry-environment, products>sap-fiori, products>sap-web-ide]
primary_tag: products>sap-cloud-platform-portal
---

## Details
### You will learn
  - How to enable the SAP Fiori Launchpad Site extension, allowing you to add a launchpad module to your MTA project
  - How to add the launchpad module to your MTA project
  - How to configure the launchpad module
  - How to add your SAP Fiori app to the launchpad and make it available to add to a Portal site

In this tutorial, you're going to configure a launchpad module and add it to your MTA project. You will then build and deploy your project, which now includes the launchpad module together with your SAP HTML5 module, into your Cloud Foundry space.

---


[ACCORDION-BEGIN [Step 1: ](Enable SAP Fiori launchpad SAP Web IDE extension)]

1. In SAP Web IDE Full-Stack, click **Preferences** in the side panel.

    ![Select Preferences](6_select_preferences.png)

2. Select **Extensions** in the side panel, enter `portal` as a search term, and locate the **SAP Fiori Launchpad Site** feature.  Turn it **ON** and **Save** your changes.

    ![Define extensions](7_extensions.png)

3. Refresh SAP Web IDE in the confirmation message.

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](Add the launchpad module to your multi-target application project)]

1. Navigate to the **Development** area in SAP Web IDE and right click your `mta_FioriDemo` project to add a new **SAP Fiori Launchpad Site Module**.

    > Note that you can only add this launchpad module to `MTA` projects.

      ![Add launchpad module](8_new_launchpad_module.png)

2. Name the module `Launchpad` and click **Finish**.

      ![Name the launchpad](9_name_launchpad_module.png)

You can see that the `Launchpad` module is now part of your `MTA` project:

  ![View Launchpad module](10_view_launchpad_module.png)

[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 3: ](Configure the launchpad content)]

Any app that you want to expose to the Portal service, should be added to the launchpad module. To add apps to the launchpad module, you should edit its `CommonDataModel.json` file.

In this step you are going to do just that.

>In this tutorial, we will use the default group name. You can use the **Add Group** button to add new groups to your launchpad.


1. Expand the launchpad module folder and select the `CommonDataModel.json` file.

    ![Select CommonDataModel](11_commondatamodel_json.png)

2. Make sure you're in **Launchpad Editor** view and then rename the default group tile to `People` by clicking on the **Edit title** icon next to it.

    ![Rename default group](13_name_group.png)


3. Now assign your SAP HTML5 module to the group. Click the **+** inside the `People` group.

    ![Add app to group](12_app_to_group.png)

4. In the **Select Project Apps** screen, check the **App Title** called `Candidates` and click **Select**. You have now assigned the `Candidates` app to the `People` group.

    ![Add app](14_add_app.png)

    This is what you'll see in the **Launchpad Editor**:

    ![View launchpad editor](15_view_launchpad_editor.png)

[VALIDATE_7]

[ACCORDION-END]


[ACCORDION-BEGIN [Step 4: ](Build and deploy your project)]

Build and deploy the `MTA` project with these modules thus exposing your app to the Portal service.

1. Right click on your `mta_FioriDemo` project and click **Build**.

    ![Build your project](16_build.png)


    An `mta_FioriDemo_0.0.1.mtar` file is generated. The file is located under the `mta_archives` folder in your Workspace.

      ![Archives file generated](19_expand_archives_folder.png)

  2. Right click your `mta_FioriDemo_0.0.1.mtar` file and click **Deploy to SAP Cloud Platform**.

      ![Deploy](17_deploy.png)

  3. The values for the **Endpoint**, **Organization**, and **Space** are automatically populated.  Click **Deploy**.

      ![View deploy details](18_deploy_details.png)


  4. Once you get a confirmation message that your project has been deployed, copy the App Router URL from the console.  

      It looks like this:
      `https://portal-dev-companyportal-jobcore-portal-space-mta-fiori<id>.cfapps.sap.hana.ondemand.com`
      Where `<id>` is your ID number.

[DONE]
[ACCORDION-END]



[ACCORDION-BEGIN [Step 5: ](Access the runtime launchpad module)]

Now let's see how the app is displayed in the runtime launchpad module.

Enter the URL that you copied from the console and add  `/cp.portal/` as a suffix to it.

Like this:

`https://portal-dev-companyportal-jobcore-portal-space-mta-fiori<id>.cfapps.sap.hana.ondemand.com/cp.portal`

Where `<id>` is your ID number.

Your launchpad module displays the `Candidates` app that you created in the `People` group.

  ![Launchpad Module](20_deployed_module.png)

Congratulations! Now you are ready to add your app to the **Launchpad** page in your Portal site.

[DONE]
[ACCORDION-END]
