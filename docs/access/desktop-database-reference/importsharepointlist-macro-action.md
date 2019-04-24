---
title: ImportSharePointList 宏操作
TOCTitle: ImportSharePointList macro action
ms:assetid: 6a633d7d-d81d-0e2e-6c1c-706a552c1bf2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195403(v=office.15)
ms:contentKeyID: 48545429
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm152234
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: df77d2375b66df907832b6ff2717427ae54a35a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291857"
---
# <a name="importsharepointlist-macro-action"></a><span data-ttu-id="1db07-102">ImportSharePointList 宏操作</span><span class="sxs-lookup"><span data-stu-id="1db07-102">ImportSharePointList macro action</span></span>

<span data-ttu-id="1db07-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1db07-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1db07-104">可以使用 **ImportSharePointList** 操作从 Microsoft SharePoint Foundation 网站导入或链接数据。</span><span class="sxs-lookup"><span data-stu-id="1db07-104">You can use the **ImportSharePointList** action to import or link data from a Microsoft SharePoint Foundation site.</span></span>

> [!NOTE]
> <span data-ttu-id="1db07-105">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="1db07-105">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="1db07-106">设置</span><span class="sxs-lookup"><span data-stu-id="1db07-106">Setting</span></span>

<span data-ttu-id="1db07-107">**ImportSharePointList** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="1db07-107">The **ImportSharePointList** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1db07-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="1db07-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="1db07-109">说明</span><span class="sxs-lookup"><span data-stu-id="1db07-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1db07-110"><strong>迁移类型</strong></span><span class="sxs-lookup"><span data-stu-id="1db07-110"><strong>Transfer Type</strong></span></span></p></td>
<td><p><span data-ttu-id="1db07-111">请选择迁移类型。</span><span class="sxs-lookup"><span data-stu-id="1db07-111">Select the type of transfer.</span></span></p>
<ul>
<li><p><span data-ttu-id="1db07-112">选择 "<strong>导入</strong>", 将 SharePoint Foundation 数据复制到 Microsoft Access 中的表中。</span><span class="sxs-lookup"><span data-stu-id="1db07-112">Select <strong>Import</strong> to copy the SharePoint Foundation data into a table in Microsoft Access.</span></span> <span data-ttu-id="1db07-113">Access 中的数据更新不会影响 SharePoint Foundation 中的数据。</span><span class="sxs-lookup"><span data-stu-id="1db07-113">Updates to the data in Access do not affect the data in SharePoint Foundation.</span></span> <span data-ttu-id="1db07-114">同样, 对 SharePoint Foundation 中的数据的更新不会影响 Access 中的数据。</span><span class="sxs-lookup"><span data-stu-id="1db07-114">Likewise, updates to the data in SharePoint Foundation do not affect the data in Access.</span></span></p></li>
<li><p><span data-ttu-id="1db07-115">选择 "<strong>链接</strong>" 可在 Access 中创建链接到 SharePoint Foundation 中的数据的链接表。</span><span class="sxs-lookup"><span data-stu-id="1db07-115">Select <strong>Link</strong> to create a linked table in Access that links to the data in SharePoint Foundation.</span></span> <span data-ttu-id="1db07-116">对 Access 中的数据的更新反映在 SharePoint Foundation 中。</span><span class="sxs-lookup"><span data-stu-id="1db07-116">Updates to the data in Access are reflected in SharePoint Foundation.</span></span> <span data-ttu-id="1db07-117">同样, 对 SharePoint Foundation 中的数据的更新会在 Access 中反映出来。</span><span class="sxs-lookup"><span data-stu-id="1db07-117">Likewise, updates to the data in SharePoint Foundation are reflected in Access.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1db07-118"><strong>网站地址</strong></span><span class="sxs-lookup"><span data-stu-id="1db07-118"><strong>Site Address</strong></span></span></p></td>
<td><p><span data-ttu-id="1db07-119">请输入 SharePoint 网站的完整路径。</span><span class="sxs-lookup"><span data-stu-id="1db07-119">Enter the full path of the SharePoint site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1db07-120"><strong>列表 ID</strong></span><span class="sxs-lookup"><span data-stu-id="1db07-120"><strong>List ID</strong></span></span></p></td>
<td><p><span data-ttu-id="1db07-121">请输入要迁移的列表的名称或 GUID。</span><span class="sxs-lookup"><span data-stu-id="1db07-121">Enter the name or GUID of the list to be transferred.</span></span> <span data-ttu-id="1db07-122">此参数是必选的。</span><span class="sxs-lookup"><span data-stu-id="1db07-122">Required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1db07-123"><strong>视图 ID</strong></span><span class="sxs-lookup"><span data-stu-id="1db07-123"><strong>View ID</strong></span></span></p></td>
<td><p><span data-ttu-id="1db07-p104">请输入要使用的列表的视图的 GUID。将此参数留空可迁移列表中的所有行和列。</span><span class="sxs-lookup"><span data-stu-id="1db07-p104">Enter the GUID of the view for the list you want to use. Leave this argument blank to transfer all rows and columns in the list.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1db07-126"><strong>表格名称</strong></span><span class="sxs-lookup"><span data-stu-id="1db07-126"><strong>Table Name</strong></span></span></p></td>
<td><p><span data-ttu-id="1db07-127">请输入要在 Access 中显示的表或链接表的名称。</span><span class="sxs-lookup"><span data-stu-id="1db07-127">Enter the name you want displayed for the table or linked table in Access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1db07-128"><strong>获取查阅的显示值</strong></span><span class="sxs-lookup"><span data-stu-id="1db07-128"><strong>Get Lookup Display Values</strong></span></span></p></td>
<td><p><span data-ttu-id="1db07-129">选择<strong>“是”</strong>可迁移查阅字段的显示值而不是用于执行查阅的 ID。</span><span class="sxs-lookup"><span data-stu-id="1db07-129">Select <strong>Yes</strong> to transfer display values for Lookup fields instead of the ID used to perform the lookup.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="1db07-130">注解</span><span class="sxs-lookup"><span data-stu-id="1db07-130">Remarks</span></span>

- <span data-ttu-id="1db07-131">此操作等效于单击 **"外部数据"** 选项卡上的 **"导入"** 组中的 **"SharePoint 列表"**。该操作的参数与在"获取外部数据向导"中的选择相对应。</span><span class="sxs-lookup"><span data-stu-id="1db07-131">This action has the same effect as clicking **SharePoint List** in the **Import** group on the **External Data** tab. The arguments for the action correspond to the choices you make in the Get External Data Wizard.</span></span>

- <span data-ttu-id="1db07-132">若要在 VBA 模块中运行 **ImportSharePointList** 操作，请使用 **DoCmd** 对象的 **TransferSharePointList** 方法。</span><span class="sxs-lookup"><span data-stu-id="1db07-132">To run the **ImportSharePointList** action in a VBA module, use the **TransferSharePointList** method of the **DoCmd** object.</span></span>

- <span data-ttu-id="1db07-133">如果指定了不存在的列表或视图，不会产生任何错误，也不会传输任何数据。</span><span class="sxs-lookup"><span data-stu-id="1db07-133">If you specify a nonexistent list or view, no error occurs, and no data is transferred.</span></span>

- <span data-ttu-id="1db07-p105">GUID 是列表或视图的唯一的十六进制标识符。GUID 必须按以下格式输入，此处的"F"是一个十六进制数字（0 到 9 或 A 到 F）。</span><span class="sxs-lookup"><span data-stu-id="1db07-p105">A GUID is a unique hexadecimal identifier for a list or a view. A GUID must be entered in the following format, where each "F" is a hexadecimal number (0 through 9 or A through F).</span></span>
    
  `{FFFFFFFF-FFFF-FFFF-FFFF-FFFFFFFFFFFF}`
    
  <span data-ttu-id="1db07-136">可以利用以下过程从 SharePoint 网站获得列表或视图的 GUID：</span><span class="sxs-lookup"><span data-stu-id="1db07-136">You can obtain the GUID for a list or view from the SharePoint site by using the following procedure:</span></span>
    
  1. <span data-ttu-id="1db07-137">打开 SharePoint Foundation 中的列表。</span><span class="sxs-lookup"><span data-stu-id="1db07-137">Open the list in SharePoint Foundation.</span></span>
    
  2. <span data-ttu-id="1db07-138">如果未显示所需的视图，请单击 **"视图"** 下拉箭头，然后选择所需的视图。</span><span class="sxs-lookup"><span data-stu-id="1db07-138">If the view you want is not displayed, click the **View** drop-down arrow and then select the view you want.</span></span>
    
  3. <span data-ttu-id="1db07-139">单击 "**视图**" 下拉箭头, 然后选择 "**修改此视图**"。浏览器地址栏中的地址包含列表和视图的 guid。</span><span class="sxs-lookup"><span data-stu-id="1db07-139">Click the **View** drop-down arrow and then select **Modify this View**.The address in the browser's address bar contains the GUIDs for both the list and the view.</span></span> <span data-ttu-id="1db07-140">列表的 guid 如下所示\*\*\*\*, 视图的 guid 如下所示: **view =**。</span><span class="sxs-lookup"><span data-stu-id="1db07-140">The GUID for the list follows **List=**, and the GUID for the view follows **View=**.</span></span> <span data-ttu-id="1db07-141">但是, 在地址中, 每个 **{** (左大括号) 字符都由字符串 **% 7b**表示, **-** 每 (连字符) 字符由字符串 **% 2d**表示, 每个 **}** (右大括号) 字符由字符串表示 **% 7d**。</span><span class="sxs-lookup"><span data-stu-id="1db07-141">However, in the address, each **{** (left brace) character is represented by the string **%7B**, each **-** (hyphen) character is represented by the string **%2D**, and each **}** (right brace) character is represented by the string **%7D**.</span></span> <span data-ttu-id="1db07-142">例如：</span><span class="sxs-lookup"><span data-stu-id="1db07-142">For example:</span></span>
        
     `https://MySite12/_layouts/ViewEdit.aspx?List=%7B2A82A404%2D5529%2D47DC%2DAE13%2DAC1D9BC0A84F%7D&View=%7B357B4FE6%2D44CF%2D4275%2DB91F%2D46558301579B%7D`
        
  <span data-ttu-id="1db07-143">必须将每个 **% 7b**字符串替换为 **{** 字符, 并将每个% 的**2d**字符串替换为**-** 字符, 然后将每个% **7d**字符串替换为 **}** 字符。</span><span class="sxs-lookup"><span data-stu-id="1db07-143">Before you can use the GUIDs from the address as arguments in this macro action, you must replace each **%7B** string with the **{** character, replace each **%2D** string with the **-** character, and replace each **%7D** string with the **}** character.</span></span> <span data-ttu-id="1db07-144">请勿在列表 GUID **&** 中包含跟在 **% 7d**字符串后面的 (与号) 字符。</span><span class="sxs-lookup"><span data-stu-id="1db07-144">Do not include the **&** (ampersand) character that follows the **%7D** string in the list GUID.</span></span>

