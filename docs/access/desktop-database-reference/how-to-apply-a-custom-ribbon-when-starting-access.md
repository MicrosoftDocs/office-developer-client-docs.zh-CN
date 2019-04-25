---
title: 启动 Access 时应用自定义功能区
TOCTitle: Apply a custom ribbon when starting Access
description: 如何在 Access 2013 中打开数据库时应用自定义功能区。
ms:assetid: 9e8ddf95-35aa-4e57-8422-d770da14711e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198313(v=office.15)
ms:contentKeyID: 48546659
ms.date: 10/16/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 0acd99a498a74f098b08814e9f11d49b28bae097
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291955"
---
# <a name="apply-a-custom-ribbon-when-starting-access"></a><span data-ttu-id="9d44a-103">启动 Access 时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="9d44a-103">Apply a custom ribbon when starting Access</span></span>

<span data-ttu-id="9d44a-104">**适用于**：Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="9d44a-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9d44a-p101">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.</span><span class="sxs-lookup"><span data-stu-id="9d44a-p101">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.</span></span>

## <a name="make-the-ribbon-customization-xml-available"></a><span data-ttu-id="9d44a-110">提供功能区自定义 XML</span><span class="sxs-lookup"><span data-stu-id="9d44a-110">Make the ribbon customization XML available</span></span>

### <a name="store-ribbon-extensibility-xml-in-a-table"></a><span data-ttu-id="9d44a-111">在表中存储功能区可扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="9d44a-111">Store ribbon extensibility XML in a table</span></span>

<span data-ttu-id="9d44a-p102">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span><span class="sxs-lookup"><span data-stu-id="9d44a-p102">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span></span>

<span data-ttu-id="9d44a-114">**USysRibbons** 是用户创建的系统表。</span><span class="sxs-lookup"><span data-stu-id="9d44a-114">**USysRibbons** is a user-created system table.</span></span> <span data-ttu-id="9d44a-115">必须使用特定的列名创建表才能实现功能区自定义。</span><span class="sxs-lookup"><span data-stu-id="9d44a-115">The table must be created using specific column names in order for the ribbon customizations to be implemented.</span></span> 

<span data-ttu-id="9d44a-116">下表列出创建 **USysRibbons** 表时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="9d44a-116">The following table lists the settings to use when creating the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9d44a-117">列名称</span><span class="sxs-lookup"><span data-stu-id="9d44a-117">Column name</span></span></p></th>
<th><p><span data-ttu-id="9d44a-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="9d44a-118">Data type</span></span></p></th>
<th><p><span data-ttu-id="9d44a-119">说明</span><span class="sxs-lookup"><span data-stu-id="9d44a-119">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d44a-120"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="9d44a-120"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="9d44a-121">Text</span><span class="sxs-lookup"><span data-stu-id="9d44a-121">Text</span></span></p></td>
<td><p><span data-ttu-id="9d44a-122">Contains the name of the custom ribbon to be associated with this customization.</span><span class="sxs-lookup"><span data-stu-id="9d44a-122">Contains the name of the custom ribbon to be associated with this customization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d44a-123"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="9d44a-123"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="9d44a-124">备注</span><span class="sxs-lookup"><span data-stu-id="9d44a-124">Memo</span></span></p></td>
<td><p><span data-ttu-id="9d44a-125">包含定义功能区自定义的功能区扩展性 XML (RibbonX)。</span><span class="sxs-lookup"><span data-stu-id="9d44a-125">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="load-ribbon-extensibility-xml-programmatically"></a><span data-ttu-id="9d44a-126">以编程的方式加载功能区扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="9d44a-126">Load ribbon extensibility XML programmatically</span></span>

<span data-ttu-id="9d44a-p104">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span><span class="sxs-lookup"><span data-stu-id="9d44a-p104">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span></span>

<span data-ttu-id="9d44a-p105">XML 标记可以来自表中创建的“Recordset”\*\*\*\* 对象，来自数据库的外部源（如您解析成字符串的 XML 文件），或来自直接嵌入在程序中的 XML 标记。您可以使用对“LoadCustomUI”\*\*\*\* 方法的多个调用创建不同的功能区，传递不同的 XML 标记，只要各功能区的名称和构成功能区的选项卡的“id”\*\*\*\* 属性是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9d44a-p105">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span></span>

<span data-ttu-id="9d44a-131">完成此程序后，使用 RunCode 操作创建调用该程序的 AutoExec 宏。</span><span class="sxs-lookup"><span data-stu-id="9d44a-131">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action.</span></span> <span data-ttu-id="9d44a-132">这样一来，启动应用程序时，**LoadCustomUI** 方法会自动执行，所有自定义功能区将提供给应用程序。</span><span class="sxs-lookup"><span data-stu-id="9d44a-132">That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span></span>

## <a name="apply-customized-ribbons-when-access-starts"></a><span data-ttu-id="9d44a-133">Access 启动时，应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="9d44a-133">Apply customized ribbons when Access starts</span></span>

<span data-ttu-id="9d44a-134">To apply a custom UI so that it is available when the application starts, use the following procedure:</span><span class="sxs-lookup"><span data-stu-id="9d44a-134">To apply a custom UI so that it is available when the application starts, use the following procedure:</span></span>

1.  <span data-ttu-id="9d44a-135">Follow the process described previously to make the customized ribbons available to the application.</span><span class="sxs-lookup"><span data-stu-id="9d44a-135">Follow the process described previously to make the customized ribbons available to the application.</span></span>

2.  <span data-ttu-id="9d44a-136">Close and then restart the application.</span><span class="sxs-lookup"><span data-stu-id="9d44a-136">Close and then restart the application.</span></span>

3.  <span data-ttu-id="9d44a-137">选择 **Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102")，然后选择“**Access 选项**”。</span><span class="sxs-lookup"><span data-stu-id="9d44a-137">Choose the **Microsoft Office Button**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") and then choose **Access Options**.</span></span>

4.  <span data-ttu-id="9d44a-138">选择“**当前数据库**”选项，然后在“**功能区和工具栏选项**”部分，选择“**功能区名称**”列表，然后选择一个功能区。</span><span class="sxs-lookup"><span data-stu-id="9d44a-138">Click the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, click the **Ribbon Name** list and select a ribbon.</span></span>

5.  <span data-ttu-id="9d44a-p107">Now close and restart the application. The UI you selected is displayed.</span><span class="sxs-lookup"><span data-stu-id="9d44a-p107">Now close and restart the application. The UI you selected is displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="9d44a-141">有关其他 Office 应用程序中的功能区 UI 的详细信息，请参阅 [Office Fluent 功能区概述](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon)。</span><span class="sxs-lookup"><span data-stu-id="9d44a-141">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


