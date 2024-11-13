# Extract, Transform, and Load (ETL) using Power Query

## Table of Contents

- [Overview](#overview)
- [Extract](#extract)
- [Transform](#transform)
- [Load](#load)

### Overview

A demo of extract, transform, and load process using Power Query in Excel or PowerBI.

### Extract

1. Open PowerBI Desktop app &#8594; Select **Blank Report**
  >
  ![powerbi desktop](screenshots/powerbi_desktop.jpg)
  >
2. From **Home** tab &#8594; Select **Transform data**
  >
  ![transform data](screenshots/transform_data.jpg)
  >
3. The Power Query window will open, go to **Home** tab &#8594; **Manage Parameters**
  >
  ![manage parameter](screenshots/manage_parameter.jpg)
  >
4. Click **New** to create a new parameter, give it a name, description, type, and value (folder directory) then click **OK**
  >
  ![new parameter](screenshots/new_parameter.jpg)
  >
5. From the Power Query Editor window, go to **Home** tab &#8594; **New Source** &#8594; **All** &#8594; **Folder** &#8594; **Connect**
  >
  ![get data](screenshots/get_data.jpg)
  >
6. A window will pop up, click **Browse** and locate the data source folder then click **OK**. Later we will update it with the parameter we created. Another window will pop up, click **Transform Data**.
  >
  ![folder path](screenshots/folderpath.jpg)
  >
7. Our data is now loaded as you can see on the query pane. Now we will update the folder path with the parameter we created. Click the **Gear** icon beside **Source** on the **APPLIED STEPS** pane &#8594; a window will pop up, click **ABC** drop-down and change it to **Parameter** &#8594; Select **p_folderPath** &#8594; click **OK**.
  >
   ![old_folderpath](screenshots/old_folderpath.jpg)
  >
8. Folder path is now updated using the dynamic parameter we created instead of the static path. Whenever we move our data source to a different directory we will only update the value on the parameter.
  >
  ![updated folder path](screenshots/updated_folderpath.jpg)
  ![parameter value](screenshots/parameter_value.jpg)
  >
9. Right-click on the query pane anywhere in the grey area, and we will create the following groups for all of our queries/tables.
  - Parameter
  - Extract
  - Transform
  - Load
  >
  ![create group](screenshots/create_group.jpg)
  >
10. Once all groups are created, place the **p_folderPath** in the **Parameter** folder and the **ETL_PowerQuery** table to **Extract** folder.
  >
  ![created group](screenshots/created_group.jpg)
  >
11. Rename the **ETL_PowerQuery** as **extract_transactions** &#8594; go to current view and filter **Name** to **transactions.xlsx** and **Extension** to **.xlsx**. We are instructing our query to accept only the **transactions.xlsx** and **.xlsx** files in case other files are in the folder path.
  >
  ![rename filter table](screenshots/rename_filter_table.jpg)
  >
12. Go to **Add Column** &#8594; select **Custom Column**, and give it a name &#8594; on the **Custom column formula**, add ***Excel.Workbook([Content])*** then click **OK**
  >
  ![custom column1](screenshots/custom_column1.jpg)
  >
13. Expand the custom column we created by clicking the arrow beside the **GetContent** column, uncheck **Use original column name as prefix** then click **OK**.
  >
  ![expand getcontent](screenshots/expand_getcontent.jpg)
  >
14. Filter **Kind** column to **Sheet** then click **OK**.
  >
  ![filter kind](screenshots/filter_kind.jpg)
  >
15. Go to **Add Column** &#8594; select **Custom Column**, give it a name &#8594; on the **Custom column formula**, add ***Table.PromoteHeaders([Data])*** then click **OK**. We are making the first row of our data as Headers.
  >
  ![custom column2](screenshots/custom_column2.jpg)
  >
16. Right-click on the **PromoteHeaders** column &#8594; select **Remove Other Columns**
  >
  ![remove other columns](screenshots/remove_other_column.jpg)
  >
  ![removed other columns](screenshots/removed_other_column.jpg)
  >
17. Right-click on the arrow beside **PromoteHeaders** column to expand the data &#8594; uncheck **Use original column name as prefix** then click **OK**.
  >
  ![expand promoteheaders](screenshots/expand_promoteheaders.jpg)
  >
18. Finally, we have done the first stage of the ETL process. All the steps we have made are recorded on the **APPLIED STEPS**, you can go back, review, and make changes if you need to.
  >
  ![final extract table](screenshots/final_extract_table.jpg)
  >

### Transform


### Load
