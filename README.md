# DreamHouse Sample Application

DreamHouse is a sample application that demonstrates the unique value proposition of the Salesforce App Cloud for building Employee Productivity and Customer Engagement apps.

Check out the [DreamHouse microsite](http://www.dreamhouseapp.io/) for more information.

## Installation Instructions

1. Install Salesforce DX. Enable the Dev Hub in your org or sign up for a Dev Hub trial org and install the Salesforce DX CLI. Follow the instructions in the [Salesforce DX Setup Guide](https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_intro.htm?search_text=trial%20hub%20org) or in the [App Development with Salesforce DX](https://trailhead.salesforce.com/modules/sfdx_app_dev) Trailhead module.

1. Clone the **dreamhouse-sfdx** repository:
    ```
    git clone https://github.com/dreamhouseapp/dreamhouse-sfdx
    cd dreamhouse-sfdx
    ```

1. Create a scratch org and provide it with an alias (dh):
    ```
    sfdx force:org:create -s -f config/project-scratch-def.json -a dh
    ```

1. Push the app to your scratch org:
    ```
    sfdx force:source:push
    ```

1. Assign the **dreamhouse** permission set to the default user:
    ```
    sfdx force:user:permset:assign -n dreamhouse
    ```

1. Import sample data
    ```
    sfdx force:data:tree:import -u dh --plan ./data/Broker__c-Property__c-plan.json
    ```    
    By default the **Date Listed** value for all the properties is arbitrarily set to 10 days before the date of the import. You may want to change that value on a few properties to make the the charts more interesting.

1. Open the scratch org:
    ```
    sfdx force:org:open
    ```

1. Select **DreamHouse** in the App Launcher
