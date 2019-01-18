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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709619"
---
# <a name="apply-a-custom-ribbon-when-starting-access"></a><span data-ttu-id="1285e-103">启动 Access 时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="1285e-103">Apply a custom ribbon when starting Access</span></span>

<span data-ttu-id="1285e-104">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1285e-104">**Applies to:** Access 2013 | Office 2013</span></span>

<span data-ttu-id="1285e-p101">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.</span><span class="sxs-lookup"><span data-stu-id="1285e-p101">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.</span></span>

## <a name="make-the-ribbon-customization-xml-available"></a><span data-ttu-id="1285e-110">可用功能区自定义 XML</span><span class="sxs-lookup"><span data-stu-id="1285e-110">Make the ribbon customization XML available</span></span>

### <a name="store-ribbon-extensibility-xml-in-a-table"></a><span data-ttu-id="1285e-111">在表中存储功能区扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="1285e-111">Store ribbon extensibility XML in a table</span></span>

<span data-ttu-id="1285e-p102">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span><span class="sxs-lookup"><span data-stu-id="1285e-p102">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span></span>

<span data-ttu-id="1285e-114">**USysRibbons** is a user-created system table.</span><span class="sxs-lookup"><span data-stu-id="1285e-114">**USysRibbons** is a user-created system table.</span></span> <span data-ttu-id="1285e-115">必须使用功能区自定义项的特定的列名称必须创建表。</span><span class="sxs-lookup"><span data-stu-id="1285e-115">The table must be created using specific column names for the ribbon customizations to be implemented.</span></span> 

<span data-ttu-id="1285e-116">下表列出了创建 **USysRibbons** 表时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="1285e-116">The following table lists the settings to use when creating the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1285e-117">列名称</span><span class="sxs-lookup"><span data-stu-id="1285e-117">Column name</span></span></p></th>
<th><p><span data-ttu-id="1285e-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="1285e-118">Data type</span></span></p></th>
<th><p><span data-ttu-id="1285e-119">说明</span><span class="sxs-lookup"><span data-stu-id="1285e-119">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1285e-120"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="1285e-120"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="1285e-121">Text</span><span class="sxs-lookup"><span data-stu-id="1285e-121">Text</span></span></p></td>
<td><p><span data-ttu-id="1285e-122">Contains the name of the custom ribbon to be associated with this customization.</span><span class="sxs-lookup"><span data-stu-id="1285e-122">Contains the name of the custom ribbon to be associated with this customization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1285e-123"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="1285e-123"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="1285e-124">Memo</span><span class="sxs-lookup"><span data-stu-id="1285e-124">Memo</span></span></p></td>
<td><p><span data-ttu-id="1285e-125">包含功能区扩展性 XML (RibbonX) 定义功能区自定义项。</span><span class="sxs-lookup"><span data-stu-id="1285e-125">Contains the ribbon extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="load-ribbon-extensibility-xml-programmatically"></a><span data-ttu-id="1285e-126">以编程方式加载功能区扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="1285e-126">Load ribbon extensibility XML programmatically</span></span>

<span data-ttu-id="1285e-p104">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span><span class="sxs-lookup"><span data-stu-id="1285e-p104">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span></span>

<span data-ttu-id="1285e-p105">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span><span class="sxs-lookup"><span data-stu-id="1285e-p105">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span></span>

<span data-ttu-id="1285e-131">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action.</span><span class="sxs-lookup"><span data-stu-id="1285e-131">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action.</span></span> <span data-ttu-id="1285e-132">这样，当应用程序启动和自动执行**LoadCustomUI**方法时，所有自定义功能区可向应用程序。</span><span class="sxs-lookup"><span data-stu-id="1285e-132">That way, when the application is started, the **LoadCustomUI** method is automatically executed, and all of the custom ribbons are made available to the application.</span></span>

## <a name="apply-customized-ribbons-when-access-starts"></a><span data-ttu-id="1285e-133">在 Access 启动时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="1285e-133">Apply customized ribbons when Access starts</span></span>

<span data-ttu-id="1285e-134">To apply a custom UI so that it is available when the application starts, use the following procedure:</span><span class="sxs-lookup"><span data-stu-id="1285e-134">To apply a custom UI so that it is available when the application starts, use the following procedure:</span></span>

1.  <span data-ttu-id="1285e-135">Follow the process described previously to make the customized ribbons available to the application.</span><span class="sxs-lookup"><span data-stu-id="1285e-135">Follow the process described previously to make the customized ribbons available to the application.</span></span>

2.  <span data-ttu-id="1285e-136">Close and then restart the application.</span><span class="sxs-lookup"><span data-stu-id="1285e-136">Close and then restart the application.</span></span>

3.  <span data-ttu-id="1285e-137">选择**Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") ，然后选择**访问选项**。</span><span class="sxs-lookup"><span data-stu-id="1285e-137">Choose the **Microsoft Office Button**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") and then choose **Access Options**.</span></span>

4.  <span data-ttu-id="1285e-138">选择**当前数据库**选项然后，在**功能区和工具栏选项**部分中，选择**功能区名称**列表并选择一个功能区。</span><span class="sxs-lookup"><span data-stu-id="1285e-138">Choose the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, choose the **Ribbon Name** list and select a ribbon.</span></span>

5.  <span data-ttu-id="1285e-p107">Now close and restart the application. The UI you selected is displayed.</span><span class="sxs-lookup"><span data-stu-id="1285e-p107">Now close and restart the application. The UI you selected is displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="1285e-141">[!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span><span class="sxs-lookup"><span data-stu-id="1285e-141">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


