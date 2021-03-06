---
title: 将 InfoPath 表单与 Microsoft Access 数据库集成
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5ec9a9c0-b348-4a31-b377-e95db2f92455
description: Microsoft InfoPath 支持将 Microsoft Access 2010 数据库用作表单的主要数据源，或者用作表单或控件的辅助数据源。本文介绍如何使用 Access 2010 数据库作为数据源。
ms.openlocfilehash: dbc39e0d0908214904d77b8955f3d231f0bfb20b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423109"
---
# <a name="integrate-an-infopath-form-with-a-microsoft-access-database"></a>将 InfoPath 表单与 Microsoft Access 数据库集成

Microsoft InfoPath 支持将 Microsoft Access 2010 数据库用作表单的主要数据源，或者用作表单或控件的辅助数据源。本文介绍如何使用 Access 2010 数据库作为数据源。
  
## <a name="using-a-microsoft-access-database-as-a-data-source"></a>使用 Microsoft Access 数据库作为数据源

### <a name="setting-up-a-microsoft-access-database-as-a-forms-primary-data-source"></a>将 Microsoft Access 数据库设置为表单的主要数据源

Database connections are established in InfoPath by using the **Data Connection Wizard**. This wizard is opened by selecting **Database** in the **Advanced Form Templates** section on the **New** tab of the Microsoft Office Backstage, and then clicking pressing **Design This Form**.
  
通过单击“选择数据库”，可以选择现有数据源或直接连接到特定数据库文件。
  
After you select a database, the wizard prompts you to select a table from the database to use as the data source for the form. As you add tables, their relationships to each other are established, and the wizard displays the tables and their hierarchical relationships in the **Data source structure** list. If you select the **Show table columns** check box, the wizard displays the field names of each table in the Data source structure list; you use the check boxes next to each field name to specify whether a field is included in the SQL statement that the wizard constructs. 
  
> [!NOTE]
> 每个表中的主键字段会始终被选中，并且无法删除。 
  
When the tables, relationships, and fields have been specified using the **Data Connection Wizard**, you can click **Edit SQL** to view the SQL statement that will be used to establish the data source for the form. In the **Edit SQL** dialog box, you can click **Test SQL Statement** to verify that InfoPath will be able to create the data source from the information provided. You can also use the **Edit SQL** dialog box to modify the SQL statement to create more complex queries. 
  
> [!NOTE]
> InfoPath 使用的 SQL 语句是数据构形查询。数据构形查询允许在查询中的两个或多个逻辑实体之间建立层次关系。可以使用 SQL JOIN 语句，但不建议这么做，因为这样做将会禁用表单提交。有关数据构形查询的详细信息，请参阅 Microsoft Developer Network (MSDN) 上的文档。 
  
The last page of the **Data Connection Wizard** displays summary information about the data source, including the name and file location of the data source, the name of the primary parent table, the number of tables used, and the submit status. The submit status tells you whether the generated SQL statement will allow for successful submission of data to the data source. 
  
### <a name="setting-up-a-microsoft-access-database-as-a-secondary-data-source"></a>设置 Microsoft Access 数据库作为辅助数据源

Secondary data sources can be used to provide the entries for a list box or drop-down list box, or you can write code to add data from a secondary data source to your form. To work with secondary data sources in your form, click **Data Connections** on the **Data** tab when designing a form. 
  
When you start the **Data Connection Wizard**, you are prompted to select whether to receive data to use in the form, or to submit data in the form. Choose **Receive data**, and then click **Next**. To create a secondary data source from a database, select **Database (Microsoft SQL Server or Microsoft Office Access only)**. On the next page of the wizard, click **Select Database** to choose an existing data source or connect directly to a specific database file. 
  
After you select a database, the wizard prompts you to select a table or query from the database to use as the data source for the form. You must select one table or query to begin with, but you can select additional tables later if you want to include them. After you've selected a table or query, the wizard allows you to select the fields you want to use in the **Data source structure** list. By default, all the fields of the table are selected, but you can remove fields if they aren't necessary for your form. You can also control how the records returned from the table are sorted, and whether multiple records are allowed. To do so, click **Modify Table**, and then select up to three sorting criteria in the **Sort Order** dialog box. When you're satisfied, click **Finish**.
  
> [!NOTE]
> 每个表中的主键字段会始终被选中，并且无法删除。 
  
InfoPath also enables you to retrieve data from multiple tables or queries at the same time. When you retrieve data from multiple tables or queries, you must be able to establish a relationship between all of the tables or queries involved with the original table or query you selected in the **Data Connection Wizard**. For example, if you were retrieving data from the Customers table of the Northwind database, you could add the Orders table to retrieve data about all the orders for that customer, and you could add the Order Details table to retrieve the details of each order.
  
To add an additional table to the data source, select the table you want to add a child table to in the **Data source structure** list, and then click **Add Table**. Select the table or query you want to add, and then click **Next**. InfoPath prompts you to select the relationship or relationships you want to use. If fields in the two tables have the same name, InfoPath automatically adds those fields as a relationship, but if not, or if you want to use a custom relationship, you can click **Add Relationship** to specify which fields in the parent table correspond to fields in the child table. You can also remove existing relationships by clicking **Remove Relationship** in the **Edit Relationship** dialog box. 
  
When you're satisfied with the relationships, click **Finish**. As with the main table, you can specify which fields are returned from the child table. You cannot, however, use the **Modify Table** button to edit the order in which the records are returned. 
  
When the tables, relationships, and fields have been specified, you can click **Edit SQL** to view the SQL query statement that will be used to establish the data source for the form. In the **Edit SQL** dialog box, you can click **Test SQL Statement** to verify that InfoPath will be able to create the data source from the information provided. You can also use the **Edit SQL** dialog box to modify the SQL statement to create more complex queries. 
  
> [!NOTE]
> InfoPath 使用的 SQL 语句是数据构形查询。数据构形查询允许在查询中的两个或多个逻辑实体之间建立层次关系。可以使用 SQL JOIN 语句，但不建议这么做，因为这样做将会禁用表单提交。有关数据构形查询的详细信息，请参阅 Microsoft Developer Network (MSDN) 上的文档。 
  
## <a name="enabling-form-submission"></a>启用表单提交

In addition to receiving data from an Access database, InfoPath can submit new or changed data back to the database. When you use the **Submit** command on the **Home** tab or the Microsoft Office Backstage to submit changes to the database, InfoPath uses ActiveX Data Objects (ADO) to update the records in the database. Form submission is enabled when all of the following conditions are met: 
  
- 表单查询中使用的每个列必须都有一个基础列。
    
- 在整个查询中，一个表列不能多次出现。
    
- 在表单查询所使用的 SELECT 子句中，每个表的主键、唯一约束或唯一索引必须可用。
    
- 表单查询中不能多次包含同一个表。
    
- 父表与子表之间的关系必须包括父表中的所有主键列。
    
- 在表单查询所使用的 SELECT 子句中，所有列只有一个基表。
    
There are some circumstances under which InfoPath cannot submit form changes to a database. For example, if you create a form that draws data from a query instead of a table, or if you customize the SQL statement that is used by InfoPath to include a JOIN statement, InfoPath will be unable to submit changes. Another circumstance that would prevent InfoPath from submitting changes is if you were to add tables to the form that have a many-to-one relationship with their parent table. In situations where InfoPath will be unable to submit changes to the database, the **Submit status** field on the last page of the **Data Connection Wizard** will display the reason for the limitation. 
  

