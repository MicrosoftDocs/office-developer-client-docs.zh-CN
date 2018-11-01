---
title: 将自定义功能区应用于窗体或报表
TOCTitle: Apply a custom ribbon to a form or report
description: 如何在加载窗体或 Access 2013 中的报表时应用自定义功能区。
ms:assetid: 7dcdfa42-3eaa-43f9-b99d-56b2cac97f84
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196428(v=office.15)
ms:contentKeyID: 48545865
ms.date: 10/16/2018
mtps_version: v=office.15
ms.openlocfilehash: e494985054ffd91440f3aff6eb671b781a5f65d7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888823"
---
# <a name="apply-a-custom-ribbon-to-a-form-or-report"></a><span data-ttu-id="c51d8-103">将自定义功能区应用于窗体或报表</span><span class="sxs-lookup"><span data-stu-id="c51d8-103">Apply a custom ribbon to a form or report</span></span>

<span data-ttu-id="c51d8-104">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c51d8-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c51d8-105">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon.</span><span class="sxs-lookup"><span data-stu-id="c51d8-105">The ribbon uses text-based, declarative XML markup that simplifies creating and customizing the ribbon.</span></span> <span data-ttu-id="c51d8-106">使用几行 XML，您可以为用户创建适当的界面。</span><span class="sxs-lookup"><span data-stu-id="c51d8-106">With a few lines of XML, you can create just the right interface for the user.</span></span> <span data-ttu-id="c51d8-107">Access 在自定义功能区用户界面方面更好地提供灵活性。</span><span class="sxs-lookup"><span data-stu-id="c51d8-107">Access provides flexibility in customizing the ribbon user interface.</span></span> 

<span data-ttu-id="c51d8-108">例如，自定义标记可以存储在一个表中，嵌入在 VBA 程序中，存储在另一个 Access 数据库中，或链接到某个 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="c51d8-108">For example, customization markup can be stored in a table, embedded in a VBA procedure, stored in another Access database, or linked to from an Excel worksheet.</span></span> <span data-ttu-id="c51d8-109">本主题介绍加载窗体或报表时如何应用自定义的功能区。</span><span class="sxs-lookup"><span data-stu-id="c51d8-109">This topic describes how to apply customized ribbons when loading a form or report.</span></span>

## <a name="make-the-ribbon-customization-xml-available"></a><span data-ttu-id="c51d8-110">可用功能区自定义 XML</span><span class="sxs-lookup"><span data-stu-id="c51d8-110">Make the ribbon customization XML available</span></span>

### <a name="store-ribbon-extensibility-xml-in-a-table"></a><span data-ttu-id="c51d8-111">在表中存储功能区扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="c51d8-111">Store ribbon extensibility XML in a table</span></span>

<span data-ttu-id="c51d8-p103">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span><span class="sxs-lookup"><span data-stu-id="c51d8-p103">One method that you can use to make ribbon customizations available is to store them in a table. If you store the customizations in a table named **USysRibbons**, the customizations can be implemented without using macros or VBA code.</span></span>

<span data-ttu-id="c51d8-114">**USysRibbons** is a user-created system table.</span><span class="sxs-lookup"><span data-stu-id="c51d8-114">**USysRibbons** is a user-created system table.</span></span> <span data-ttu-id="c51d8-115">必须使用功能区自定义项的特定的列名称必须创建表。</span><span class="sxs-lookup"><span data-stu-id="c51d8-115">The table must be created using specific column names for the ribbon customizations to be implemented.</span></span> 

<span data-ttu-id="c51d8-116">下表列出了创建 **USysRibbons** 表时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="c51d8-116">The following table lists the settings to use when creating the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c51d8-117">列名称</span><span class="sxs-lookup"><span data-stu-id="c51d8-117">Column name</span></span></p></th>
<th><p><span data-ttu-id="c51d8-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="c51d8-118">Data type</span></span></p></th>
<th><p><span data-ttu-id="c51d8-119">说明</span><span class="sxs-lookup"><span data-stu-id="c51d8-119">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c51d8-120"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="c51d8-120"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="c51d8-121">Text</span><span class="sxs-lookup"><span data-stu-id="c51d8-121">Text</span></span></p></td>
<td><p><span data-ttu-id="c51d8-122">Contains the name of the custom ribbon to be associated with this customization.</span><span class="sxs-lookup"><span data-stu-id="c51d8-122">Contains the name of the custom ribbon to be associated with this customization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c51d8-123"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="c51d8-123"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="c51d8-124">Memo</span><span class="sxs-lookup"><span data-stu-id="c51d8-124">Memo</span></span></p></td>
<td><p><span data-ttu-id="c51d8-125">包含功能区扩展性 XML (RibbonX) 定义功能区自定义项。</span><span class="sxs-lookup"><span data-stu-id="c51d8-125">Contains the ribbon extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="load-ribbon-extensibility-xml-programmatically"></a><span data-ttu-id="c51d8-126">以编程方式加载功能区扩展性 XML</span><span class="sxs-lookup"><span data-stu-id="c51d8-126">Load ribbon extensibility XML programmatically</span></span>

<span data-ttu-id="c51d8-p105">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span><span class="sxs-lookup"><span data-stu-id="c51d8-p105">You can use the **[LoadCustomUI](https://docs.microsoft.com/office/vba/api/Access.Application.LoadCustomUI)** method to load ribbon customizations programmatically. Typically, to create and make the ribbon available to the application, you first create a module in the database with a procedure that calls the **LoadCustomUI** method, passing in the name of the ribbon and the XML customization markup.</span></span>

<span data-ttu-id="c51d8-p106">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span><span class="sxs-lookup"><span data-stu-id="c51d8-p106">The XML markup can come from a **Recordset** object created from a table, from a source external to the database such as an XML file that you parse into a string, or from XML markup embedded directly inside the procedure. You can make different ribbons using multiple calls to the **LoadCustomUI** method, passing in different XML markup as long as the name of each ribbon and the **id** attribute of the tabs that make up the ribbon are unique.</span></span>

<span data-ttu-id="c51d8-p107">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span><span class="sxs-lookup"><span data-stu-id="c51d8-p107">After the procedure is complete, you then create an AutoExec macro that calls the procedure by using the RunCode action. That way, when the application is started, the **LoadCustomUI** method is automatically executed and all of the custom ribbons are made available to the application.</span></span>

## <a name="assign-custom-ribbons-to-forms-or-reports"></a><span data-ttu-id="c51d8-133">分配窗体或报表的自定义功能区</span><span class="sxs-lookup"><span data-stu-id="c51d8-133">Assign custom ribbons to forms or reports</span></span>

1.  <span data-ttu-id="c51d8-134">按照先前描述的过程将自定义的功能区提供给该应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="c51d8-134">Follow the process described previously to make the customized ribbon available to the application.</span></span>

2.  <span data-ttu-id="c51d8-135">在"设计"视图中打开窗体或报表。</span><span class="sxs-lookup"><span data-stu-id="c51d8-135">Open the form or report in Design view.</span></span>

3.  <span data-ttu-id="c51d8-136">在设计选项卡中，选择**属性表**。</span><span class="sxs-lookup"><span data-stu-id="c51d8-136">On the Design tab, choose **Property Sheet**.</span></span>

4.  <span data-ttu-id="c51d8-137">在属性窗口的**所有**选项卡上，选择**功能区名称**列表，然后选择功能区。</span><span class="sxs-lookup"><span data-stu-id="c51d8-137">On the **All** tab of the Property window, choose the **Ribbon Name** list and then select a ribbon.</span></span>

5.  <span data-ttu-id="c51d8-p108">保存、关闭和重新打开窗体或报表。将显示您选择的功能区 UI。</span><span class="sxs-lookup"><span data-stu-id="c51d8-p108">Save, close, and then reopen the form or report. The ribbon UI you selected is displayed.</span></span>


> [!NOTE]
> <span data-ttu-id="c51d8-140">在功能区 UI 中显示的选项卡是累加。</span><span class="sxs-lookup"><span data-stu-id="c51d8-140">The tabs displayed in the ribbon UI are additive.</span></span> <span data-ttu-id="c51d8-141">即，除非您明确隐藏选项卡或*从头开始*属性设置为**True**，选项卡显示在窗体或报表的功能区用户界面除了现有选项卡。</span><span class="sxs-lookup"><span data-stu-id="c51d8-141">That is, unless you specifically hide the tabs or set the *Start from Scratch* attribute to **True**, the tabs displayed in a form's or report's ribbon user interface are in addition to the existing tabs.</span></span>

> [!NOTE]
> <span data-ttu-id="c51d8-142">[!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span><span class="sxs-lookup"><span data-stu-id="c51d8-142">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


