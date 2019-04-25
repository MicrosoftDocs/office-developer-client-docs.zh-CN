---
title: Access 启动时隐藏功能区
TOCTitle: Hide the ribbon when Access starts
description: 如何加载可隐藏 Access 2013 中所有内置选项卡的自定义功能区。
ms:assetid: f98bab58-8094-1c56-f70b-ced2e7849574
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837012(v=office.15)
ms:contentKeyID: 48548817
ms.date: 10/16/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 4ce9327790f620ba9163f5cdbe7b5c8900de4341
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291936"
---
# <a name="hide-the-ribbon-when-access-starts"></a><span data-ttu-id="f3548-103">Access 启动时隐藏功能区</span><span class="sxs-lookup"><span data-stu-id="f3548-103">Hide the ribbon when Access starts</span></span>

<span data-ttu-id="f3548-104">**适用于**：Access 2013 | Office 2013</span><span class="sxs-lookup"><span data-stu-id="f3548-104">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f3548-p101">默认情况下，Microsoft Access 不提供用于隐藏功能区的方法。本主题介绍如何加载可隐藏所有的内置选项卡的自定义功能区。</span><span class="sxs-lookup"><span data-stu-id="f3548-p101">By default, Microsoft Access does not provide a method for hiding the ribbon. This topic describes how to load a customized ribbon that hides all of the built-in tabs.</span></span>

<span data-ttu-id="f3548-107">要在 Access 启动时加载自定义的功能区，应将其设置存储在一个名为 **USysRibbons** 的表中。</span><span class="sxs-lookup"><span data-stu-id="f3548-107">To load the customized ribbon when Access starts, you should store its settings in a table named **USysRibbons**.</span></span>

<span data-ttu-id="f3548-108">必须使用特定的列名创建 **USysRibbons** 表才能实现功能区自定义。</span><span class="sxs-lookup"><span data-stu-id="f3548-108">The **USysRibbons** table must be created using specific column names in order for the ribbon customizations to be implemented.</span></span> 

<span data-ttu-id="f3548-109">下表列出了创建 **USysRibbons** 表时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="f3548-109">The following table lists the settings to use when creating the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f3548-110">列名称</span><span class="sxs-lookup"><span data-stu-id="f3548-110">Column name</span></span></p></th>
<th><p><span data-ttu-id="f3548-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="f3548-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="f3548-112">说明</span><span class="sxs-lookup"><span data-stu-id="f3548-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3548-113"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="f3548-113"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="f3548-114">Text</span><span class="sxs-lookup"><span data-stu-id="f3548-114">Text</span></span></p></td>
<td><p><span data-ttu-id="f3548-115">Contains the name of the custom ribbon to be associated with this customization.</span><span class="sxs-lookup"><span data-stu-id="f3548-115">Contains the name of the custom ribbon to be associated with this customization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3548-116"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="f3548-116"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="f3548-117">备注</span><span class="sxs-lookup"><span data-stu-id="f3548-117">Memo</span></span></p></td>
<td><p><span data-ttu-id="f3548-118">包含定义功能区自定义的功能区扩展性 XML (RibbonX)。</span><span class="sxs-lookup"><span data-stu-id="f3548-118">Contains the Ribbon Extensibility XML (RibbonX) that  defines the ribbon customization.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="f3548-119">下表列出了要存储在 **USysRibbons** 表中的功能区自定义设置。</span><span class="sxs-lookup"><span data-stu-id="f3548-119">The following table lists the ribbon customization settings to store in the **USysRibbons** table.</span></span>

|<span data-ttu-id="f3548-120">列名称</span><span class="sxs-lookup"><span data-stu-id="f3548-120">Column name</span></span>|<span data-ttu-id="f3548-121">值</span><span class="sxs-lookup"><span data-stu-id="f3548-121">Value</span></span>|
|:----------|:----|
|<span data-ttu-id="f3548-122">**RibbonName**</span><span class="sxs-lookup"><span data-stu-id="f3548-122">**RibbonName**</span></span>|<span data-ttu-id="f3548-123">HideTheRibbon</span><span class="sxs-lookup"><span data-stu-id="f3548-123">HideTheRibbon</span></span>|
|<span data-ttu-id="f3548-124">**RibbonXML**</span><span class="sxs-lookup"><span data-stu-id="f3548-124">**RibbonXML**</span></span>|`<CustomUI xmlns="https://schemas.microsoft.com/office/2006/01/CustomUI"> <ribbon startFromScratch="true"/></CustomUI>`|


## <a name="apply-a-custom-ribbon-when-access-starts"></a><span data-ttu-id="f3548-125">Access 启动时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="f3548-125">Apply a custom ribbon when starting Access</span></span>

<span data-ttu-id="f3548-126">若要应用自定义功能区以使它在应用程序启动时可用，请执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="f3548-126">To apply a custom ribbon so that it is available when the application starts, use the following procedure:</span></span>

1.  <span data-ttu-id="f3548-127">按照先前描述的过程将自定义的功能区提供给该应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="f3548-127">Follow the process described previously to make the customized ribbon available to the application.</span></span>

2.  <span data-ttu-id="f3548-128">关闭应用程序，然后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="f3548-128">Close and then restart the application.</span></span>

3.  <span data-ttu-id="f3548-129">选择 **Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102")，然后选择“**Access 选项**”。</span><span class="sxs-lookup"><span data-stu-id="f3548-129">Choose the **Microsoft Office Button**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102"), and then choose **Access Options**.</span></span>

4.  <span data-ttu-id="f3548-130">选择“**当前数据库**”选项，然后在“**功能区和工具栏选项**”部分，选择“**功能区名称**”列表，然后选择“**HideTheRibbon**”。</span><span class="sxs-lookup"><span data-stu-id="f3548-130">Click the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, click the **Ribbon Name** list and select **HideTheRibbon**.</span></span>

5.  <span data-ttu-id="f3548-131">关闭再重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="f3548-131">Close and then restart the application.</span></span>

> [!NOTE]
> <span data-ttu-id="f3548-132">有关其他 Office 应用程序中的功能区 UI 的详细信息，请参阅 [Office Fluent 功能区概述](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon)。</span><span class="sxs-lookup"><span data-stu-id="f3548-132">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


