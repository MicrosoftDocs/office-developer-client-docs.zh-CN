---
title: 适用于窗体或报表的自定义功能区
TOCTitle: Apply a custom ribbon to a form or report
ms:assetid: 7dcdfa42-3eaa-43f9-b99d-56b2cac97f84
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196428(v=office.15)
ms:contentKeyID: 48545865
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f4fb0155b1a1ed36b6fe924f72a4da385197cc21
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468113"
---
# <a name="apply-a-custom-ribbon-to-a-form-or-report"></a><span data-ttu-id="f4202-102">适用于窗体或报表的自定义功能区</span><span class="sxs-lookup"><span data-stu-id="f4202-102">Apply a custom ribbon to a form or report</span></span>


<span data-ttu-id="f4202-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f4202-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f4202-p101">功能区采用基于文本的声明性 XML 标记，从而简化了创建和自定义功能区。使用几行 XML，您可以为用户创建适当的界面。Access 在自定义功能区用户界面方面更好地提供灵活性。例如，自定义标记可以存储在一个表中，嵌入在 VBA 程序中，存储在另一个 Access 数据库中，或链接到某个 Excel 工作表。本主题介绍加载窗体或报表时如何应用自定义的功能区。</span><span class="sxs-lookup"><span data-stu-id="f4202-p101">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon. With a few lines of XML, you can create just the right interface for the user. Access provides flexibility in customizing the ribbon user interface. For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet. This topic describes how to apply customized ribbons when loading a form or report.</span></span>

## <a name="making-the-ribbon-customization-xml-available"></a><span data-ttu-id="f4202-109">提供功能区自定义 XML</span><span class="sxs-lookup"><span data-stu-id="f4202-109">Making the Ribbon Customization XML Available</span></span>

<span data-ttu-id="f4202-110">**Storing Ribbon Extensibility XML in a Table**</span><span class="sxs-lookup"><span data-stu-id="f4202-110">**Storing Ribbon Extensibility XML in a Table**</span></span>

<span data-ttu-id="f4202-p102">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span><span class="sxs-lookup"><span data-stu-id="f4202-p102">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span></span>

<span data-ttu-id="f4202-p103">**USysRibbons** is a user-created system table. The table must be created using specific column names in order for the ribbon customizations to be implemented. The following table lists the settings to use when creating the **USysRibbons** table.</span><span class="sxs-lookup"><span data-stu-id="f4202-p103">**USysRibbons** is a user-created system table. The table must be created using specific column names in order for the ribbon customizations to be implemented. The following table lists the settings to use when creating the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f4202-116">列名称</span><span class="sxs-lookup"><span data-stu-id="f4202-116">Column Name</span></span></p></th>
<th><p><span data-ttu-id="f4202-117">数据类型</span><span class="sxs-lookup"><span data-stu-id="f4202-117">Data Type</span></span></p></th>
<th><p><span data-ttu-id="f4202-118">说明</span><span class="sxs-lookup"><span data-stu-id="f4202-118">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4202-119"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="f4202-119"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="f4202-120">文本</span><span class="sxs-lookup"><span data-stu-id="f4202-120">Text</span></span></p></td>
<td><p><span data-ttu-id="f4202-121">包含要与该自定义项关联的自定义功能区名称</span><span class="sxs-lookup"><span data-stu-id="f4202-121">Contains the name of the custom ribbon to be associated with this customization</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4202-122"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="f4202-122"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="f4202-123">备注</span><span class="sxs-lookup"><span data-stu-id="f4202-123">Memo</span></span></p></td>
<td><p><span data-ttu-id="f4202-124">包含定义功能区自定义项的功能区扩展性 XML (RibbonX)</span><span class="sxs-lookup"><span data-stu-id="f4202-124">Contains the ribbon Extensibility XML (RibbonX) that defines the ribbon customization</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f4202-125">**以编程的方式加载功能区扩展性 XML**</span><span class="sxs-lookup"><span data-stu-id="f4202-125">**Loading Ribbon Extensibility XML Programmatically**</span></span>

<span data-ttu-id="f4202-p104">You can use the **[LoadCustomUI](https://msdn.microsoft.com/library/ff194416\(v=office.15\))** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span><span class="sxs-lookup"><span data-stu-id="f4202-p104">You can use the **[LoadCustomUI](https://msdn.microsoft.com/library/ff194416\(v=office.15\))** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span></span>

<span data-ttu-id="f4202-p105">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span><span class="sxs-lookup"><span data-stu-id="f4202-p105">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span></span>

<span data-ttu-id="f4202-p106">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span><span class="sxs-lookup"><span data-stu-id="f4202-p106">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span></span>

## <a name="assigning-custom-ribbons-to-forms-or-reports"></a><span data-ttu-id="f4202-132">将自定义功能区分配到窗体或报表</span><span class="sxs-lookup"><span data-stu-id="f4202-132">Assigning Custom Ribbons to Forms or Reports</span></span>

1.  <span data-ttu-id="f4202-133">按照先前描述的过程将自定义的功能区提供给该应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="f4202-133">Follow the process described previously to make the customized ribbon available to the application.</span></span>

2.  <span data-ttu-id="f4202-134">在"设计"视图中打开窗体或报表。</span><span class="sxs-lookup"><span data-stu-id="f4202-134">Open the form or report in Design view.</span></span>

3.  <span data-ttu-id="f4202-135">在设计选项卡中，单击**属性表**。</span><span class="sxs-lookup"><span data-stu-id="f4202-135">On the Design tab, click **Property Sheet**.</span></span>

4.  <span data-ttu-id="f4202-136">在属性窗口的**所有**选项卡上，单击**功能区名称**列表，然后选择功能区。</span><span class="sxs-lookup"><span data-stu-id="f4202-136">On the **All** tab of the Property window, click the **Ribbon Name** list and then select a ribbon.</span></span>

5.  <span data-ttu-id="f4202-p107">保存、关闭和重新打开窗体或报表。将显示您选择的功能区 UI。</span><span class="sxs-lookup"><span data-stu-id="f4202-p107">Save, close, and then reopen the form or report. The ribbon UI you selected is displayed.</span></span>


> [!NOTE]
> <span data-ttu-id="f4202-139">在功能区 UI 中显示的选项卡是累加。</span><span class="sxs-lookup"><span data-stu-id="f4202-139">The tabs displayed in the ribbon UI are additive.</span></span> <span data-ttu-id="f4202-140">即，除非您明确隐藏选项卡或*从头开始*属性设置为**True**，选项卡显示在窗体或报表的功能区用户界面除了现有选项卡。</span><span class="sxs-lookup"><span data-stu-id="f4202-140">That is, unless you specifically hide the tabs or set the *Start from Scratch* attribute to **True**, the tabs displayed in a form's or report's ribbon user interface are in addition to the existing tabs.</span></span>

> [!NOTE]
> <span data-ttu-id="f4202-141">[!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span><span class="sxs-lookup"><span data-stu-id="f4202-141">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


