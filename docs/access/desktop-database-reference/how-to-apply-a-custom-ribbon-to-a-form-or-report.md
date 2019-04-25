---
title: 将自定义功能区应用于窗体或报表
TOCTitle: Apply a custom ribbon to a form or report
description: 如何在 Access 2013 中加载窗体或报表时应用自定义功能区。
ms:assetid: 7dcdfa42-3eaa-43f9-b99d-56b2cac97f84
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196428(v=office.15)
ms:contentKeyID: 48545865
ms.date: 10/16/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 329f184a1bcd3c856ccfd0b15c3fa92bc6230c98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291913"
---
# <a name="apply-a-custom-ribbon-to-a-form-or-report"></a><span data-ttu-id="00a76-103">将自定义功能区应用于窗体或报表</span><span class="sxs-lookup"><span data-stu-id="00a76-103">Apply a custom ribbon to a form or report</span></span>

<span data-ttu-id="00a76-104">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="00a76-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="00a76-105">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon.</span><span class="sxs-lookup"><span data-stu-id="00a76-105">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon.</span></span> <span data-ttu-id="00a76-106">使用几行 XML，您可以为用户创建适当的界面。</span><span class="sxs-lookup"><span data-stu-id="00a76-106">With a few lines of XML, you can create just the right interface for the user.</span></span> <span data-ttu-id="00a76-107">Access 在自定义功能区用户界面方面更好地提供灵活性。</span><span class="sxs-lookup"><span data-stu-id="00a76-107">Access provides flexibility in customizing the ribbon user interface.</span></span> 

<span data-ttu-id="00a76-108">例如，自定义标记可以存储在一个表中，嵌入在 VBA 程序中，存储在另一个 Access 数据库中，或链接到某个 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="00a76-108">For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet.</span></span> <span data-ttu-id="00a76-109">本主题介绍加载窗体或报表时如何应用自定义的功能区。</span><span class="sxs-lookup"><span data-stu-id="00a76-109">This topic describes how to apply customized ribbons when loading a form or report.</span></span>

## <a name="make-the-ribbon-customization-xml-available"></a><span data-ttu-id="00a76-110">提供功能区自定义 XML</span><span class="sxs-lookup"><span data-stu-id="00a76-110">Make the ribbon customization XML available</span></span>

### <a name="store-ribbon-extensibility-xml-in-a-table"></a><span data-ttu-id="00a76-111">在表中存储功能区可扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="00a76-111">Store ribbon extensibility XML in a table</span></span>

<span data-ttu-id="00a76-p103">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span><span class="sxs-lookup"><span data-stu-id="00a76-p103">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span></span>

<span data-ttu-id="00a76-114">**USysRibbons** 是用户创建的系统表。</span><span class="sxs-lookup"><span data-stu-id="00a76-114">**USysRibbons** is a user-created system table.</span></span> <span data-ttu-id="00a76-115">必须使用特定的列名创建表才能实现功能区自定义。</span><span class="sxs-lookup"><span data-stu-id="00a76-115">The table must be created using specific column names in order for the ribbon customizations to be implemented.</span></span> 

<span data-ttu-id="00a76-116">下表列出创建 **USysRibbons** 表时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="00a76-116">The following table lists the settings to use when creating the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="00a76-117">列名称</span><span class="sxs-lookup"><span data-stu-id="00a76-117">Column name</span></span></p></th>
<th><p><span data-ttu-id="00a76-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="00a76-118">Data type</span></span></p></th>
<th><p><span data-ttu-id="00a76-119">说明</span><span class="sxs-lookup"><span data-stu-id="00a76-119">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00a76-120"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="00a76-120"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="00a76-121">Text</span><span class="sxs-lookup"><span data-stu-id="00a76-121">Text</span></span></p></td>
<td><p><span data-ttu-id="00a76-122">Contains the name of the custom ribbon to be associated with this customization.</span><span class="sxs-lookup"><span data-stu-id="00a76-122">Contains the name of the custom ribbon to be associated with this customization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00a76-123"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="00a76-123"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="00a76-124">备注</span><span class="sxs-lookup"><span data-stu-id="00a76-124">Memo</span></span></p></td>
<td><p><span data-ttu-id="00a76-125">包含定义功能区自定义的功能区扩展性 XML (RibbonX)。</span><span class="sxs-lookup"><span data-stu-id="00a76-125">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="load-ribbon-extensibility-xml-programmatically"></a><span data-ttu-id="00a76-126">以编程的方式加载功能区扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="00a76-126">Load ribbon extensibility XML programmatically</span></span>

<span data-ttu-id="00a76-p105">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span><span class="sxs-lookup"><span data-stu-id="00a76-p105">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span></span>

<span data-ttu-id="00a76-p106">XML 标记可以来自表中创建的“Recordset”\*\*\*\* 对象，来自数据库的外部源（如您解析成字符串的 XML 文件），或来自直接嵌入在程序中的 XML 标记。您可以使用对“LoadCustomUI”\*\*\*\* 方法的多个调用创建不同的功能区，传递不同的 XML 标记，只要各功能区的名称和构成功能区的选项卡的“id”\*\*\*\* 属性是唯一的。</span><span class="sxs-lookup"><span data-stu-id="00a76-p106">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span></span>

<span data-ttu-id="00a76-p107">完成此程序后，再创建一个使用 RunCode 操作调用该程序的 AutoExec 宏。如此一来，当应用程序启动时，系统将自动执行“LoadCustomUI”\*\*\*\* 方法，并且所有自定义功能区都可提供给该应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="00a76-p107">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span></span>

## <a name="assign-custom-ribbons-to-forms-or-reports"></a><span data-ttu-id="00a76-133">为窗体或报表指定自定义功能区</span><span class="sxs-lookup"><span data-stu-id="00a76-133">Assigning custom ribbons to forms or reports</span></span>

1.  <span data-ttu-id="00a76-134">按照先前描述的过程将自定义的功能区提供给该应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="00a76-134">Follow the process described previously to make the customized ribbon available to the application.</span></span>

2.  <span data-ttu-id="00a76-135">在“设计”视图中打开窗体或报表。</span><span class="sxs-lookup"><span data-stu-id="00a76-135">Open the form or report in Design view.</span></span>

3.  <span data-ttu-id="00a76-136">在“设计”选项卡上，选择“**属性表**”。</span><span class="sxs-lookup"><span data-stu-id="00a76-136">On the Design tab, click **Property Sheet**.</span></span>

4.  <span data-ttu-id="00a76-137">在“属性”窗口的“**所有**”选项卡上，选择“**功能区名称**”列表，然后选择一个功能区。</span><span class="sxs-lookup"><span data-stu-id="00a76-137">On the **All** tab of the Property window, click the **Ribbon Name** list and then select a ribbon.</span></span>

5.  <span data-ttu-id="00a76-138">保存、关闭和重新打开窗体或报表。</span><span class="sxs-lookup"><span data-stu-id="00a76-138">Save, close, and then reopen the form or report.</span></span> <span data-ttu-id="00a76-139">将显示您选择的功能区 UI。</span><span class="sxs-lookup"><span data-stu-id="00a76-139">The ribbon UI you selected is displayed.</span></span>


> [!NOTE]
> <span data-ttu-id="00a76-p109">在功能区 UI 中显示的选项卡具有累加性。即，除非明确隐藏选项卡或将“从头开始”\*\* 属性设置为“True”\*\*\*\*，否则显示在窗体或报表功能区用户界面中的选项卡是对现有选项卡的补充。</span><span class="sxs-lookup"><span data-stu-id="00a76-p109">The tabs displayed in the ribbon UI are additive. That is, unless you specifically hide the tabs or set the *Start from Scratch* attribute to **True**, the tabs displayed in a form's or report's ribbon user interface are in addition to the existing tabs.</span></span>

> [!NOTE]
> <span data-ttu-id="00a76-142">有关其他 Office 应用程序中的功能区 UI 的详细信息，请参阅 [Office Fluent 功能区概述](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon)。</span><span class="sxs-lookup"><span data-stu-id="00a76-142">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


