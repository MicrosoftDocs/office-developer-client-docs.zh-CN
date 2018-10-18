---
标题： 访问 （访问桌面数据库引用） TOCTitle 中的更改： Access 中的更改 <<<<<<< 标头 ms:assetid: 8dfc5fc9-a6a7-4a91-8e97-c3874e9b880f ms:mtpsurl: https://msdn.microsoft.com/library/JJ618413(v=office.15) ms:contentKeyID: 49106417 ms.date: 09/18/2015年 ===说明： 访问不包含 Access 数据项目 (Adp) 的支持。 Access introduces a new application type that enables you to create a web-based Access app.
ms:assetid: 8dfc5fc9-a6a7-4a91-8e97-c3874e9b880f ms:mtpsurl: https://msdn.microsoft.com/library/JJ618413(v=office.15) ms:contentKeyID: 49106417 ms.date: 10/16/2018
>>>>>>> 主 mtps_version: office.15.aspx
---

# <a name="changes-in-access"></a>Changes in Access 2013

**适用于：** Access 2013 |Office 2013

<<<<<<< 标头访问不包含 Access 数据项目 (Adp) 的支持。 Access introduces a new application type that enables you to create a web-based Access app. By using this application type, you can create web-based applications that use the power of SQL Server on premise or in the cloud.

Access introduces a new application type that enables you to create a web-based Access app. By using this application type, you can create web-based applications that use the power of SQL Server on premise or in the cloud.

In an Access app on SharePoint Server, when you create a table, a query or a data macro in the Access client in which you are creating tables, views or triggers in a SQL Server database. Using the Access client, you can open your database to other applications that connect to SQL Server. This enables you to share your data or load data from other systems into your Access app.

With Office 365 and Access, you can build applications that reach your users without having to worry about deployment challenges, software installation issues, or operating system compatibilities. Build your app in one location and share it across the web with the power of SQL Azure and SQL Server.

[SQL Azure](https://msdn.microsoft.com/library/azure/ee336279.aspx), the cloud version of SQL Server, does not support features that Access Data Projects (ADPs) rely on to operate. To support ADPs on SQL Azure, Access would require significant changes.

For these reasons, Access does not support ADPs. ADPs have been a great tool for working with SQL Server in an on-premise environment, however much has changed since ADPs were introduced in Access 2000. Users now expect their database to be available wherever they are.

## <a name="adp-support-and-the-future"></a>ADP support and the future

ADPs continue to work in earlier versions of Access. You can continue to develop your ADP applications and we will continue to support earlier versions of Access under the standard [support lifecycle](https://support.microsoft.com/gp/lifeselect). We will not update older versions of Access to support new versions of SQL Server or SQL Azure. Therefore, you may encounter issues if you use SQL Server 2012 or later versions with your ADP. ADPs will continue to support SQL 2008 R2 and earlier.

For the future, ADP developers can consider several different possibilities:

- **将转换为 Access 应用程序**– 使用 Access，可以导入表新的 Access 应用程序和窗体应用程序会自动为您创建。 You can extend the functionality of the base forms Access creates for you and users can use your application on the web. Although some of the functionality that you use in ADPs may not be available now, expect Microsoft to continue to focus improvements in the product for this application type.

- **将转换为链接的桌面数据库**– 访问继续支持.accdb 文件格式创建桌面数据库。 You can convert your application to the .accdb format, including all of your existing forms and reports, and leave the data in SQL Server. You can link to the SQL Server database using linked tables and your application will continue to operate against the same data.

- **创建一个混合应用程序**– 如果您的应用程序很大，并且您不想要在同一时间转换的全部内容，您可以导入数据的 Access 应用程序和链接到 SQL Server 数据库从.accdb。 This allows you migrate gradually, adding forms and functionality over time to your Access app while maintaining your client application as an .accdb with linked tables to the SQL Server database behind the Access app.

- **升级到.NET Framework** – 您的应用程序可能复杂足够的一个要考虑移动到.NET Framework 如专业开发平台。 SQL Server 旨在使您更轻松地使用现有数据库基础结构已创建和扩展您的应用程序的功能而无需显著重新编写代码。
=== 访问不包含 Access 数据项目 (Adp) 的支持。 Access introduces a new application type that enables you to create a web-based Access app. 使用此应用程序类型，您可以创建基于 web 的应用程序使用的 SQL Server 本地或云中的强大功能。

在 SharePoint 服务器上的 Access 应用程序中访问客户端在其中创建表、 视图或触发器在 SQL Server 数据库中，使用访问客户端，创建一个表、 查询或数据宏时可以打开其他应用程序数据库的连接ect 到 SQL Server。 This enables you to share your data or load data from other systems into your Access app.

With Office 365 and Access, you can build applications that reach your users without having to worry about deployment challenges, software installation issues, or operating system compatibilities. Build your app in one location and share it across the web with the power of SQL Azure and SQL Server.

[SQL Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview), the cloud version of SQL Server, does not support features that Access Data Projects (ADPs) rely on to operate. To support ADPs on SQL Azure, Access would require significant changes.

For these reasons, Access does not support ADPs. Adp 已在内部部署环境; 中使用 SQL Server 的绝佳工具但是后 Access 2000 中引入 Adp, 何已更改。 Users now expect their database to be available wherever they are.

## <a name="adp-support-and-the-future"></a>ADP support and the future

ADPs continue to work in earlier versions of Access. You can continue to develop your ADP applications and we will continue to support earlier versions of Access under the standard [support lifecycle](https://support.microsoft.com/lifecycle/search). We will not update older versions of Access to support new versions of SQL Server or SQL Azure. Therefore, you may encounter issues if you use SQL Server 2012 or later versions with your ADP. ADPs will continue to support SQL 2008 R2 and earlier.

For the future, ADP developers can consider several different possibilities:

- **将转换为 Access 应用程序**– 使用 Access，可以导入表的新的 Access 应用程序，并为您自动创建您的应用程序的表单。 您可以扩展，则 Access 将创建的基准表单的功能和用户可以在 web 上使用您的应用程序。 Although some of the functionality that you use in ADPs may not be available now, expect Microsoft to continue to focus improvements in the product for this application type.

- **将转换为链接的桌面数据库**– 访问继续支持.accdb 文件格式创建桌面数据库。 You can convert your application to the .accdb format, including all of your existing forms and reports, and leave the data in SQL Server. 您可以通过使用链接的表链接到的 SQL Server 数据库和您的应用程序将继续运行针对相同的数据。

- **创建一个混合应用程序**– 如果您的应用程序很大，并且您不想要在同一时间转换的全部内容，您可以导入数据的 Access 应用程序和链接到 SQL Server 数据库从.accdb。 这样，您迁移逐步，向窗体和功能随着时间的推移访问应用程序，同时维护客户端应用程序作为与链接表.accdb 到 SQL Server 数据库后面 Access 应用程序。

- **升级到.NET Framework** – 您的应用程序可能足够复杂，需要考虑移动到.NET Framework 如专业开发平台。 SQL Server 旨在使您更轻松地使用现有数据库基础结构和扩展您的应用程序的功能而无需显著重新编写代码。
>>>>>>> master

## <a name="conclusion"></a>Conclusion

Access is designed to connect databases with the cloud by building on SharePoint Server and SQL Server technologies and easily work with Office 365. Access is designed to help you quickly create and share data-driven business apps that help run your business.

## <a name="see-also"></a>另请参阅

<<<<<<< 标头
- [Access 中面向开发人员的新增功能](https://msdn.microsoft.com/library/jj250134\(v=office.15\))
- [Microsoft Support Lifecycle](https://support.microsoft.com/lifecycle/)
- [Microsoft Azure SQL 数据库](https://msdn.microsoft.com/library/azure/ee336279.aspx)
=======
- [面向开发人员的 Access 2013 中的新增功能](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/new-in-access-for-developers)

>>>>>>> master

