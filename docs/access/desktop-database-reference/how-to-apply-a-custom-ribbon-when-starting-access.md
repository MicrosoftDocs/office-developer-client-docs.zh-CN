---
<span data-ttu-id="735f2-101">标题： 启动 Access TOCTitle 时应用自定义功能区： Access 启动时应用自定义功能区 <<<<<<< 标头 ms:assetid: 9e8ddf95-35aa-4e57-8422-d770da14711e ms:mtpsurl: https://msdn.microsoft.com/library/Ff198313(v=office.15) ms:contentKeyID: 48546659 ms.date: 09/18 /2015 === 说明： 如何在 Access 2013 中打开数据库时应用自定义功能区。</span><span class="sxs-lookup"><span data-stu-id="735f2-101">title: Apply a custom ribbon when starting Access TOCTitle: Apply a custom ribbon when starting Access <<<<<<< HEAD ms:assetid: 9e8ddf95-35aa-4e57-8422-d770da14711e ms:mtpsurl: https://msdn.microsoft.com/library/Ff198313(v=office.15) ms:contentKeyID: 48546659 ms.date: 09/18/2015 ======= description: How to apply customized ribbons when opening a database in Access 2013.</span></span> <span data-ttu-id="735f2-102">ms:assetid: 9e8ddf95-35aa-4e57-8422-d770da14711e ms:mtpsurl: https://msdn.microsoft.com/library/Ff198313(v=office.15) ms:contentKeyID: 48546659 ms.date: 10/16/2018</span><span class="sxs-lookup"><span data-stu-id="735f2-102">ms:assetid: 9e8ddf95-35aa-4e57-8422-d770da14711e ms:mtpsurl: https://msdn.microsoft.com/library/Ff198313(v=office.15) ms:contentKeyID: 48546659 ms.date: 10/16/2018</span></span>
>>>>>>> <span data-ttu-id="735f2-103">主 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="735f2-103">master mtps_version: v=office.15</span></span>
---

# <a name="apply-a-custom-ribbon-when-starting-access"></a><span data-ttu-id="735f2-104">Access 启动时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="735f2-104">Apply a custom ribbon when starting Access</span></span>

<span data-ttu-id="735f2-105">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="735f2-105">**Applies to:** Access 2013 | Office 2013</span></span>

<span data-ttu-id="735f2-p102">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.</span><span class="sxs-lookup"><span data-stu-id="735f2-p102">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.</span></span>

<span data-ttu-id="735f2-111"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="735f2-111"><<<<<<< HEAD</span></span>
## <a name="making-the-ribbon-customization-xml-available"></a><span data-ttu-id="735f2-112">Making the Ribbon Customization XML Available</span><span class="sxs-lookup"><span data-stu-id="735f2-112">Making the Ribbon Customization XML Available</span></span>

### <a name="storing-ribbon-extensibility-xml-in-a-table"></a><span data-ttu-id="735f2-113">Storing Ribbon Extensibility XML in a Table</span><span class="sxs-lookup"><span data-stu-id="735f2-113">Storing Ribbon Extensibility XML in a Table</span></span>

<span data-ttu-id="735f2-p103">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span><span class="sxs-lookup"><span data-stu-id="735f2-p103">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span></span>

<span data-ttu-id="735f2-p104">**USysRibbons** is a user-created system table. The table must be created using specific column names in order for the ribbon customizations to be implemented. The following table lists the settings to use when creating the **USysRibbons** table.</span><span class="sxs-lookup"><span data-stu-id="735f2-p104">**USysRibbons** is a user-created system table. The table must be created using specific column names in order for the ribbon customizations to be implemented. The following table lists the settings to use when creating the **USysRibbons** table.</span></span>
=======
## <a name="make-the-ribbon-customization-xml-available"></a><span data-ttu-id="735f2-119">可用功能区自定义 XML</span><span class="sxs-lookup"><span data-stu-id="735f2-119">Make the ribbon customization XML available</span></span>

### <a name="store-ribbon-extensibility-xml-in-a-table"></a><span data-ttu-id="735f2-120">在表中存储功能区扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="735f2-120">Store ribbon extensibility XML in a table</span></span>

<span data-ttu-id="735f2-p105">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span><span class="sxs-lookup"><span data-stu-id="735f2-p105">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span></span>

<span data-ttu-id="735f2-123">**USysRibbons** is a user-created system table.</span><span class="sxs-lookup"><span data-stu-id="735f2-123">**USysRibbons** is a user-created system table.</span></span> <span data-ttu-id="735f2-124">必须使用功能区自定义项的特定的列名称必须创建表。</span><span class="sxs-lookup"><span data-stu-id="735f2-124">The table must be created using specific column names for the ribbon customizations to be implemented.</span></span> 

<span data-ttu-id="735f2-125">下表列出了创建 **USysRibbons** 表时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="735f2-125">The following table lists the settings to use when creating the **USysRibbons** table.</span></span>
>>>>>>> <span data-ttu-id="735f2-126">master</span><span class="sxs-lookup"><span data-stu-id="735f2-126">master</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<span data-ttu-id="735f2-127"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="735f2-127"><<<<<<< HEAD</span></span>
<th><p><span data-ttu-id="735f2-128">列名称</span><span class="sxs-lookup"><span data-stu-id="735f2-128">Column Name</span></span></p></th>
<th><p><span data-ttu-id="735f2-129">数据类型</span><span class="sxs-lookup"><span data-stu-id="735f2-129">Data Type</span></span></p></th>
=======
<th><p><span data-ttu-id="735f2-130">列名称</span><span class="sxs-lookup"><span data-stu-id="735f2-130">Column name</span></span></p></th>
<th><p><span data-ttu-id="735f2-131">数据类型</span><span class="sxs-lookup"><span data-stu-id="735f2-131">Data type</span></span></p></th><span data-ttu-id="735f2-132">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="735f2-132">
>>>>>>> master</span></span>
<th><p><span data-ttu-id="735f2-133">说明</span><span class="sxs-lookup"><span data-stu-id="735f2-133">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="735f2-134"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="735f2-134"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="735f2-135">Text</span><span class="sxs-lookup"><span data-stu-id="735f2-135">Text</span></span></p></td>
<td><p><span data-ttu-id="735f2-136">Contains the name of the custom ribbon to be associated with this customization.</span><span class="sxs-lookup"><span data-stu-id="735f2-136">Contains the name of the custom ribbon to be associated with this customization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735f2-137"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="735f2-137"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="735f2-138">Memo</span><span class="sxs-lookup"><span data-stu-id="735f2-138">Memo</span></span></p></td>
<span data-ttu-id="735f2-139"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="735f2-139"><<<<<<< HEAD</span></span>
<td><p><span data-ttu-id="735f2-140">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span><span class="sxs-lookup"><span data-stu-id="735f2-140">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td>
=======
<td><p><span data-ttu-id="735f2-141">包含功能区扩展性 XML (RibbonX) 定义功能区自定义项。</span><span class="sxs-lookup"><span data-stu-id="735f2-141">Contains the ribbon extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td><span data-ttu-id="735f2-142">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="735f2-142">
>>>>>>> master</span></span>
</tr>
</tbody>
</table>


<span data-ttu-id="735f2-143"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="735f2-143"><<<<<<< HEAD</span></span>
### <a name="loading-ribbon-extensibility-xml-programmatically"></a><span data-ttu-id="735f2-144">Loading Ribbon Extensibility XML Programmatically</span><span class="sxs-lookup"><span data-stu-id="735f2-144">Loading Ribbon Extensibility XML Programmatically</span></span>

<span data-ttu-id="735f2-p107">You can use the **[LoadCustomUI](https://msdn.microsoft.com/library/ff194416\(v=office.15\))** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span><span class="sxs-lookup"><span data-stu-id="735f2-p107">You can use the **[LoadCustomUI](https://msdn.microsoft.com/library/ff194416\(v=office.15\))** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span></span>

<span data-ttu-id="735f2-p108">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span><span class="sxs-lookup"><span data-stu-id="735f2-p108">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span></span>

<span data-ttu-id="735f2-p109">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span><span class="sxs-lookup"><span data-stu-id="735f2-p109">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span></span>

## <a name="applying-customized-ribbons-when-access-starts"></a><span data-ttu-id="735f2-151">Applying Customized Ribbons When Access Starts</span><span class="sxs-lookup"><span data-stu-id="735f2-151">Applying Customized Ribbons When Access Starts</span></span>
=======
### <a name="load-ribbon-extensibility-xml-programmatically"></a><span data-ttu-id="735f2-152">以编程方式加载功能区扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="735f2-152">Load ribbon extensibility XML programmatically</span></span>

<span data-ttu-id="735f2-p110">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span><span class="sxs-lookup"><span data-stu-id="735f2-p110">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span></span>

<span data-ttu-id="735f2-p111">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span><span class="sxs-lookup"><span data-stu-id="735f2-p111">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span></span>

<span data-ttu-id="735f2-157">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action.</span><span class="sxs-lookup"><span data-stu-id="735f2-157">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action.</span></span> <span data-ttu-id="735f2-158">这样，当应用程序启动和自动执行**LoadCustomUI**方法时，所有自定义功能区可向应用程序。</span><span class="sxs-lookup"><span data-stu-id="735f2-158">That way, when the application is started, the **LoadCustomUI** method is automatically executed, and all of the custom ribbons are made available to the application.</span></span>

## <a name="apply-customized-ribbons-when-access-starts"></a><span data-ttu-id="735f2-159">在 Access 启动时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="735f2-159">Apply customized ribbons when Access starts</span></span>
>>>>>>> <span data-ttu-id="735f2-160">master</span><span class="sxs-lookup"><span data-stu-id="735f2-160">master</span></span>

<span data-ttu-id="735f2-161">To apply a custom UI so that it is available when the application starts, use the following procedure:</span><span class="sxs-lookup"><span data-stu-id="735f2-161">To apply a custom UI so that it is available when the application starts, use the following procedure:</span></span>

1.  <span data-ttu-id="735f2-162">Follow the process described previously to make the customized ribbons available to the application.</span><span class="sxs-lookup"><span data-stu-id="735f2-162">Follow the process described previously to make the customized ribbons available to the application.</span></span>

2.  <span data-ttu-id="735f2-163">Close and then restart the application.</span><span class="sxs-lookup"><span data-stu-id="735f2-163">Close and then restart the application.</span></span>

<span data-ttu-id="735f2-164"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="735f2-164"><<<<<<< HEAD</span></span>
3.  <span data-ttu-id="735f2-165">单击**Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") ，然后单击**Access 选项**。</span><span class="sxs-lookup"><span data-stu-id="735f2-165">Click the **Microsoft Office Button**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") and then click **Access Options**.</span></span>

4.  <span data-ttu-id="735f2-166">Click the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, click the **Ribbon Name** list and select a ribbon.</span><span class="sxs-lookup"><span data-stu-id="735f2-166">Click the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, click the **Ribbon Name** list and select a ribbon.</span></span>
=======
3.  <span data-ttu-id="735f2-167">选择**Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") ，然后选择**访问选项**。</span><span class="sxs-lookup"><span data-stu-id="735f2-167">Choose the **Microsoft Office Button**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") and then choose **Access Options**.</span></span>

4.  <span data-ttu-id="735f2-168">选择**当前数据库**选项然后，在**功能区和工具栏选项**部分中，选择**功能区名称**列表并选择一个功能区。</span><span class="sxs-lookup"><span data-stu-id="735f2-168">Choose the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, choose the **Ribbon Name** list and select a ribbon.</span></span>
>>>>>>> <span data-ttu-id="735f2-169">master</span><span class="sxs-lookup"><span data-stu-id="735f2-169">master</span></span>

5.  <span data-ttu-id="735f2-p113">Now close and restart the application. The UI you selected is displayed.</span><span class="sxs-lookup"><span data-stu-id="735f2-p113">Now close and restart the application. The UI you selected is displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="735f2-172">[!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span><span class="sxs-lookup"><span data-stu-id="735f2-172">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


