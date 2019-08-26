## Exercise 5.2: Using Unifi to Ingest 2nd & 3rd Party Profiles
In this exercise, the goal is to learn how to import Profile data into Unifi, join data sets, and ingest the data into Adobe Experience Platform.

### Learning Objectives

- Learn how to create datasets in Unifi
- Learn how to create jobs in Unifi. 
- Understand the process to join data sets, enrich profile data, and ingest it in Platfrom.

### Lab Resources

- Unifi: [https://adobe-demo.westus2.cloudapp.azure.com/datai/#/dashboard](https://adobe-demo.westus2.cloudapp.azure.com/datai/#/dashboard)
- Experience Platform UI: [https://platform.adobe.com/](https://platform.adobe.com/)
- Sample data: [Survey Data](../data/survey_data.csv.zip)
- Sample data: [Demographics Data](../data/3rdparty_data.csv.zip)

### Lab Tasks

- Create datasets in Unifi for Survey and Demographics data.
- Create a job to join the above data sets, enrich and filter the data.
- Run the job to ingest the profiles into Platform

### Story: Using Unifi to ingest 2nd and 3rd party data into Platform.

La Boutique fashion brand, has a partnership with Survey corp which has agreed to share their latest survey results on people preferences on designers, colors, and brands. La Boutique has also decided to buy some demographics data from a marketplace from Money Corp, providing details on people income and credit score. By combining these two data sets La Boutique is aiming to target their customer with more meaning experiences to their preferences as well as income.

### Exercise 5.2.1 - Create Unifi Data Sets

In this exercise, you'll create two data sets in Unifi, one for the profiles from survey data, one for the 3rd party profiles.

1. Download and unzip the two .csv files provided in the lab resources above and save them in a folder of your choice in your local machine.

2. Go to <a href="https://adobe-demo.westus2.cloudapp.azure.com/datai/#/dashboard" _target="blank">Unifi site</a>, and login using the credentials provided. Upon successful login you should see the Unifi Dashboard.

![Unifi Dashboard](../images/unifi_dashboard.png)

3. Using the left side navigation, go to **Build > Data Set**

![Unifi Build Data Set](../images/unifi_build_data_set.png)

4. On the modal, select ``Local System``.

![Unifi Data Set Local](../images/unifi_data_set_local.png)

5. Click on ``Upload File`` and select the ``survey_data.csv`` file downloaded above. 

![Unifi Data Set Upload](../images/unifi_data_set_upload_survey.png)

6. Input the Data Set Name following the below format. Click on ``Create``.

Name Format: **ldap - Unifi - Survey Data** 

![Unifi Data Set](../images/unifi_data_set_create_survey.png)

6. Click ``Save`` on the top right corner, to save the new data set.

![Unifi Data Set](../images/unifi_data_set_save_survey.png)

You have created your fist data set! This data set contains the following data:

| Column       | Description                           |
|:----         | :--------                             |
| id           | Row number                            |
| email        | Email ID                              |
| fav_designer | Person's favourite designer           |
| fav_color    | Person's favourite color              |
| fav_shop     | Person's favourite brand              |


![Unifi Data Set](../images/unifi_data_set_created_survey.png)


7. Repeat steps 3-6 for ``3rdparty_data.csv``. Please name the data set as per below:

Name Format: **ldap - Unifi - 3rdParty** 

You have created your second data set! This data set contains the following data:

| Column        | Description                           |
|:----          | :--------                             |
| id            | Row Number                            |
| first_name    | Customer's first name                 |
| last_name     | Customer's last name                  |
| email         | Customer's email address              |
| yearly_income | Customer's yearly income              |
| credit-score  | Customer's current credit score       |

![Unifi Data Set](../images/unifi_data_set_created_3rdParty.png)

You have now created the data sets required for this exercise!


### Exercise 5.2.2 - Create Unifi Job

In this exercise, you'll create the job to join the above create data sets, enrich the data, and ingest it in Platform.

1. Go to <a href="https://adobe-demo.westus2.cloudapp.azure.com/datai/#/dashboard" _target="blank">Unifi site</a>, and login using the credentials provided. Upon successful login you should see the Unifi Dashboard.

![Unifi Dashboard](../images/unifi_dashboard.png)

2. Using the left side navigation, go to **Build > Job**

![Unifi Build Job](../images/unifi_build_job.png)

3. On the modal, name the job **``ldap - EMEA Enablement - 2nd_3rd_Party``**. Click ``Create``.

![Unifi Job](../images/unifi_job_23.png)

You have now entered the Job workflow.  

![Unifi Job Workflow](../images/unifi_job_workflow_23.png)

4. Select the Survey Data - dataset created on the previous exercise. Name Format: **ldap - Unifi - Survey Data** 

![Unifi Job Select Data Set ](../images/unifi_job_select_data_set_survey.png)

5. Move to step 2 **Join Data Sets**.

![Unifi Job Join Data Set](../images/unifi_job_join_data_set_23.png)

6. Select the 3rd Party Data - dataset created on the previous exercise. Name Format: **ldap - Unifi - 2nd_3rd_Party** 

![Unifi Job Select Data Set 2](../images/unifi_job_select_data_set_3.png)

* The aim of this join is to enrich both the profiles from the survey data and demographics data with the attributes on either source. So, we would use a Full Outer Join. For mor info on joins please go <a href="https://en.wikipedia.org/wiki/Join_(SQL)" target="_blank">here.</a>

* As we know from the above exercise, the two data sets have one attribute in common, ``email``. We will use this to stich the two datasets together. Once selected click ``Done``.

![Unifi Job left outer](../images/unifi_job_select_full_outer.png)

7. Move to step 3 **Enrich Data**.

![Unifi Job Enrich Data](../images/unifi_job_enrich_data_23.png)

8. On the **Enrich Data** step we will enrich the datasets with a few other required fields before we can ingest the data in Platform.

![Unifi Job Enrich Data](../images/unifi_job_enrich_data_UI.png)

We know from previous past modules that when ingesting Identity object data we have 4 fields that are required:
- ID namespace
- ID
- Authenticated State
- Primary Identity

From the imported data sources we only have the ``ID``. We need to add the other three.

**Creating the emailNS attribute**
- On the **3. Enrich Data** interface, ``Create Function`` form, give the function the name ``emailNS``, and define it to be ```'Email'``` (include the quotes). Click ``Done``.

![Unifi Job Enrich Data - Email Namespace](../images/unifi_job_enrich_data_emailNS_saved.png)

**Creating the authenticatedState attribute**
- On the **3. Enrich Data** interface, ``Create Function`` form, give the function the name ``authenticatesState``, and define it to be ```'Authenticated'```(include the quotes). Click ``Done``.

![Unifi Job Enrich Data - Auth](../images/unifi_job_enrich_data_auth_saved.png)

**Creating the primaryID attribute**
- On the **3. Enrich Data** interface, ``Create Function`` form, give the function the name ``primaryID``, and define it to be ```1```. Click ``Done``.

![Unifi Job Enrich Data - Primary ID](../images/unifi_job_enrich_data_primary_saved.png)

Additionally to the above, we know that the ``yearly_income`` attribute is currently a number indicating the persons income. This number is not of very high importance to the La Boutique marketing team, but the team has instead categorized the yearly income in 3 groups: high salary - >100K, medium salary - >50K & <100K, low salary <50K. To manage this create the function the name ``salaryGroup``, and define it to be:
 
```case when [yourLDAP - Unifi - 3rdParty.yearly_income] > 100000 then 'high' when [yourLDAP - Unifi - 3rdParty.yearly_income] > 50000 then 'medium' else 'low' end```. 

Replace ``yourLDAP`` with your LDAP in the above lines of code.

Click Done.

![Unifi Job Enrich Data - Primary ID](../images/unifi_job_enrich_data_income.png)

You should have now created 4 functions as per below:

![Unifi Job Enrich Data - Saved](../images/unifi_job_enrich_saved23.png)

9. Move to step 4 **Choose Columns**.

![Unifi Job Columns](../images/unifi_job_columns23.png)

10. On the **Choose Columns** step, we are going to select all the columns that want to ingest into Platform. So, please select the following:
	* all the defined Funtions
	* from the **ldap - Unifi - Survey Data** select ``email``, ``fav_designer``, ``fav_color``, ``fav_shop``
	* from the **ldap - Unifi - 2nd_3rd_Party** select ``yearly_income`` and ``credit-score``

	![Unifi Job Columns](../images/unifi_job_columns_selected_23.png)

11. For these data sets we won't need to apply any filters, so we will skip step 5 **Add Filter** and move to step 6 **Aggregate**.

![Unifi Job Aggregate](../images/unifi_job_aggregate_23.png)

14. On this step you are able to perform any aggregate funtions, or grouping the data. To learn more about aggreagate functions click <a href="https://en.wikipedia.org/wiki/Aggregate_function" target="_blank">here.</a>

For this use case we do not require to use any functions, so we will only be selecting all columns.

![Unifi Job Aggregate](../images/unifi_job_aggregate_done_23.png)


13. Move to final step **Output**.

![Unifi Job Output](../images/unifi_job_output_23.png)

14. On the final step, you will be map the output of the Job to a Schema in Platform and ingest the data.

* On the right hand side configure the Output as per below:

| Setting         | Value                    |
| :---            | :---                     |
| Type            | AEP                      |
| Data Source     | Experience Platform EMEA |
| Select Data Set | Unifi - 2nd_3rd_Party    |

![Unifi Job Output](../images/unifi_job_output_config_23.png)

* You should now see on the UI, the data set schema as Target. If you see that mappings have already been made, delete them first so that you start with a clean overview. Mappings can be deleted/reset by clicking the ``Reset Connections`` - button.

![Unifi Job Output](../images/resetconnection.png) 

![Unifi Job Output](../images/unifi_job_output_schema_23.png)

* Map the Output to the Schema attributes as per below:

| Output                                    | Target                                                 |
| :---                                      | :---                                                   |
| ldap - Unifi - Survey Data.email        | identityMap[0].id                                      |
| ldap - Unifi - Survey Data.fav_designer | \_experienceplatform.customer_preferences.fav_designer |
| ldap - Unifi - Survey Data.fav_color    | \_experienceplatform.customer_preferences.fav_color    |
| ldap - Unifi - Survey Data.fav_shop.    | \_experienceplatform.customer_preferences.fav_brand    |
| ldap - Unifi - 3rdParty.credit-score    | \_experienceplatform.customer_demographics.credit_score|
| emailNS                                   | identityMap[identityMapKey]                            |
| authenticatedState                        | identityMap[0].authenticatedState                      |
| primaryID                                 | identityMap[0].primary                                 |
| salaryGroup                               | \_experienceplatform.customer_demographics.income      |

In the below screenshot you see colored lines. When first configuring this mapping, the lines will be gray. After saving, they will have similar colors as below.

![Unifi Job Output](../images/unifi_job_output_map23.png)

* Click Save & Run

![Unifi Job Output](../images/unifi_job_output_run23.png)

Uppon completion, in the log UI find the batch ID.

![Unifi Job Output](../images/unifi_job_output_batch_ID_23.png)

15. Open the Platform UI and go to ``Datasets`` > ``Unifi`` . Find the batch with the above id. You should see a success message.

![Platform Batch](../images/unifi_job_platform23.png)

Congratulations you have now successfully used Unifi to ingest Profile data to Adobe Experience Platform! Please input the batch id on <a href="https://wiki.corp.adobe.com/display/expplatformemea/Module+5%3A+Unifi" target="_blank">this page</a> to complete the exercise.


[Go Back to Module 5](../README.md)

[Go Back to All Modules](../../README.md)




