---
title: Access 启动时应用自定义功能区
TOCTitle: Apply a custom ribbon when starting Access
ms:assetid: 9e8ddf95-35aa-4e57-8422-d770da14711e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198313(v=office.15)
ms:contentKeyID: 48546659
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 575834f818386a7ba536e826fff2b7da00b324d5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25469036"
---
# <a name="apply-a-custom-ribbon-when-starting-access"></a><span data-ttu-id="3f38a-102">Access 启动时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="3f38a-102">Apply a custom ribbon when starting Access</span></span>

<span data-ttu-id="3f38a-103">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3f38a-103">**Applies to:** Access 2013 | Office 2013</span></span>

<span data-ttu-id="3f38a-p101">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.</span><span class="sxs-lookup"><span data-stu-id="3f38a-p101">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides tremendous flexibility in customizing the ribbon UI. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when opening a database.</span></span>

## <a name="making-the-ribbon-customization-xml-available"></a><span data-ttu-id="3f38a-109">Making the Ribbon Customization XML Available</span><span class="sxs-lookup"><span data-stu-id="3f38a-109">Making the Ribbon Customization XML Available</span></span>

### <a name="storing-ribbon-extensibility-xml-in-a-table"></a><span data-ttu-id="3f38a-110">Storing Ribbon Extensibility XML in a Table</span><span class="sxs-lookup"><span data-stu-id="3f38a-110">Storing Ribbon Extensibility XML in a Table</span></span>

<span data-ttu-id="3f38a-p102">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span><span class="sxs-lookup"><span data-stu-id="3f38a-p102">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span></span>

<span data-ttu-id="3f38a-p103">**USysRibbons** is a user-created system table. The table must be created using specific column names in order for the ribbon customizations to be implemented. The following table lists the settings to use when creating the **USysRibbons** table.</span><span class="sxs-lookup"><span data-stu-id="3f38a-p103">**USysRibbons** is a user-created system table. The table must be created using specific column names in order for the ribbon customizations to be implemented. The following table lists the settings to use when creating the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3f38a-116">列名称</span><span class="sxs-lookup"><span data-stu-id="3f38a-116">Column Name</span></span></p></th>
<th><p><span data-ttu-id="3f38a-117">数据类型</span><span class="sxs-lookup"><span data-stu-id="3f38a-117">Data Type</span></span></p></th>
<th><p><span data-ttu-id="3f38a-118">说明</span><span class="sxs-lookup"><span data-stu-id="3f38a-118">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f38a-119"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="3f38a-119"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="3f38a-120">Text</span><span class="sxs-lookup"><span data-stu-id="3f38a-120">Text</span></span></p></td>
<td><p><span data-ttu-id="3f38a-121">Contains the name of the custom ribbon to be associated with this customization.</span><span class="sxs-lookup"><span data-stu-id="3f38a-121">Contains the name of the custom ribbon to be associated with this customization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f38a-122"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="3f38a-122"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="3f38a-123">Memo</span><span class="sxs-lookup"><span data-stu-id="3f38a-123">Memo</span></span></p></td>
<td><p><span data-ttu-id="3f38a-124">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span><span class="sxs-lookup"><span data-stu-id="3f38a-124">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="loading-ribbon-extensibility-xml-programmatically"></a><span data-ttu-id="3f38a-125">Loading Ribbon Extensibility XML Programmatically</span><span class="sxs-lookup"><span data-stu-id="3f38a-125">Loading Ribbon Extensibility XML Programmatically</span></span>

<span data-ttu-id="3f38a-p104">You can use the **[LoadCustomUI](https://msdn.microsoft.com/library/ff194416\(v=office.15\))** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span><span class="sxs-lookup"><span data-stu-id="3f38a-p104">You can use the **[LoadCustomUI](https://msdn.microsoft.com/library/ff194416\(v=office.15\))** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span></span>

<span data-ttu-id="3f38a-p105">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span><span class="sxs-lookup"><span data-stu-id="3f38a-p105">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span></span>

<span data-ttu-id="3f38a-p106">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span><span class="sxs-lookup"><span data-stu-id="3f38a-p106">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span></span>

## <a name="applying-customized-ribbons-when-access-starts"></a><span data-ttu-id="3f38a-132">Applying Customized Ribbons When Access Starts</span><span class="sxs-lookup"><span data-stu-id="3f38a-132">Applying Customized Ribbons When Access Starts</span></span>

<span data-ttu-id="3f38a-133">To apply a custom UI so that it is available when the application starts, use the following procedure:</span><span class="sxs-lookup"><span data-stu-id="3f38a-133">To apply a custom UI so that it is available when the application starts, use the following procedure:</span></span>

1.  <span data-ttu-id="3f38a-134">Follow the process described previously to make the customized ribbons available to the application.</span><span class="sxs-lookup"><span data-stu-id="3f38a-134">Follow the process described previously to make the customized ribbons available to the application.</span></span>

2.  <span data-ttu-id="3f38a-135">Close and then restart the application.</span><span class="sxs-lookup"><span data-stu-id="3f38a-135">Close and then restart the application.</span></span>

3.  <span data-ttu-id="3f38a-136">单击**Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") ，然后单击**Access 选项**。</span><span class="sxs-lookup"><span data-stu-id="3f38a-136">Click the **Microsoft Office Button**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") and then click **Access Options**.</span></span>

4.  <span data-ttu-id="3f38a-137">Click the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, click the **Ribbon Name** list and select a ribbon.</span><span class="sxs-lookup"><span data-stu-id="3f38a-137">Click the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, click the **Ribbon Name** list and select a ribbon.</span></span>

5.  <span data-ttu-id="3f38a-p107">Now close and restart the application. The UI you selected is displayed.</span><span class="sxs-lookup"><span data-stu-id="3f38a-p107">Now close and restart the application. The UI you selected is displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="3f38a-140">[!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span><span class="sxs-lookup"><span data-stu-id="3f38a-140">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


