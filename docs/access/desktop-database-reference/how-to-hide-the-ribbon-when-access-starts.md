---
title: 在 Access 启动时隐藏功能区
TOCTitle: Hide the ribbon when Access starts
ms:assetid: f98bab58-8094-1c56-f70b-ced2e7849574
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837012(v=office.15)
ms:contentKeyID: 48548817
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2b2b3e28157662a585fa03353da92a598b96bd2c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466193"
---
# <a name="hide-the-ribbon-when-access-starts"></a><span data-ttu-id="8e937-102">在 Access 启动时隐藏功能区</span><span class="sxs-lookup"><span data-stu-id="8e937-102">Hide the ribbon when Access starts</span></span>

<span data-ttu-id="8e937-103">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8e937-103">**Applies to:** Access 2013 | Office 2013</span></span>

<span data-ttu-id="8e937-p101">默认情况下，Microsoft Access 不提供用于隐藏功能区的方法。本主题介绍如何加载可隐藏所有的内置选项卡的自定义功能区。</span><span class="sxs-lookup"><span data-stu-id="8e937-p101">By default, Microsoft Access does not provide a method for hiding the ribbon. This topic describes how to load a customized ribbon that hides all of the built-in tabs.</span></span>

<span data-ttu-id="8e937-106">要在 Access 启动时加载自定义的功能区，应将其设置存储在一个名为 **USysRibbons** 的表中。</span><span class="sxs-lookup"><span data-stu-id="8e937-106">To load the customized ribbon when Access starts, you should store its settings in a table named **USysRibbons**.</span></span>

<span data-ttu-id="8e937-p102">必须使用特定的列名创建 **USysRibbons** 表才能实现功能区自定义。下表列出了创建 **USysRibbons** 表时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="8e937-p102">The **USysRibbons** table must be created using specific column names in order for the ribbon customizations to be implemented. The following table lists the settings to use when creating the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8e937-109">列名称</span><span class="sxs-lookup"><span data-stu-id="8e937-109">Column Name</span></span></p></th>
<th><p><span data-ttu-id="8e937-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="8e937-110">Data Type</span></span></p></th>
<th><p><span data-ttu-id="8e937-111">说明</span><span class="sxs-lookup"><span data-stu-id="8e937-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e937-112"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="8e937-112"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="8e937-113">Text</span><span class="sxs-lookup"><span data-stu-id="8e937-113">Text</span></span></p></td>
<td><p><span data-ttu-id="8e937-114">Contains the name of the custom ribbon to be associated with this customization.</span><span class="sxs-lookup"><span data-stu-id="8e937-114">Contains the name of the custom ribbon to be associated with this customization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e937-115"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="8e937-115"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="8e937-116">Memo</span><span class="sxs-lookup"><span data-stu-id="8e937-116">Memo</span></span></p></td>
<td><p><span data-ttu-id="8e937-117">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span><span class="sxs-lookup"><span data-stu-id="8e937-117">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8e937-118">下表列出了要存储在 **USysRibbons** 表中的功能区自定义设置。</span><span class="sxs-lookup"><span data-stu-id="8e937-118">The following table lists the ribbon customization settings to store in the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8e937-119">列名</span><span class="sxs-lookup"><span data-stu-id="8e937-119">Column Name</span></span></p></th>
<th><p><span data-ttu-id="8e937-120">值</span><span class="sxs-lookup"><span data-stu-id="8e937-120">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e937-121"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="8e937-121"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="8e937-122">HideTheRibbon</span><span class="sxs-lookup"><span data-stu-id="8e937-122">HideTheRibbon</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e937-123"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="8e937-123"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="8e937-124">&lt;CustomUI xmlns =&quot;https://schemas.microsoft.com/office/2006/01/CustomUI&quot;&gt; &lt;功能区 startFromScratch =&quot;true&quot;/&gt;&lt;/CustomUI&gt;</span><span class="sxs-lookup"><span data-stu-id="8e937-124">&lt;CustomUI xmlns=&quot;https://schemas.microsoft.com/office/2006/01/CustomUI&quot;&gt; &lt;ribbon startFromScratch=&quot;true&quot;/&gt;&lt;/CustomUI&gt;</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="applying-a-custom-ribbon-when-access-starts"></a><span data-ttu-id="8e937-125">在 Access 启动时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="8e937-125">Applying a Custom Ribbon When Access Starts</span></span>

<span data-ttu-id="8e937-126">若要应用自定义功能区以使它在应用程序启动时可用，请执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="8e937-126">To apply a custom ribbon so that it is available when the application starts, use the following procedure:</span></span>

1.  <span data-ttu-id="8e937-127">按照前面描述的过程使自定义功能区可供应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="8e937-127">Follow the process described previously to make the customized ribbon available to the application.</span></span>

2.  <span data-ttu-id="8e937-128">关闭应用程序，然后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="8e937-128">Close and then restart the application.</span></span>

3.  <span data-ttu-id="8e937-129">单击**Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") ，然后单击**Access 选项**。</span><span class="sxs-lookup"><span data-stu-id="8e937-129">Click the **Microsoft Office Button**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") and then click **Access Options**.</span></span>

4.  <span data-ttu-id="8e937-130">单击 **"当前数据库"** 选项，然后在 **"功能区和工具栏选项"** 部分单击 **"功能区名称"** 列表并选择 **"HideTheRibbon"** 。</span><span class="sxs-lookup"><span data-stu-id="8e937-130">Click the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, click the **Ribbon Name** list and select **HideTheRibbon**.</span></span>

5.  <span data-ttu-id="8e937-131">关闭应用程序，然后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="8e937-131">Close and then restart the application.</span></span>

> [!NOTE]
> <span data-ttu-id="8e937-132">[!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span><span class="sxs-lookup"><span data-stu-id="8e937-132">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


