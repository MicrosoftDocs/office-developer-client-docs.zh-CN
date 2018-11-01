---
title: RunSavedImportExport 宏操作
TOCTitle: RunSavedImportExport Macro Action
ms:assetid: b2449c51-ee20-6e50-87f3-a45adc0b0dde
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822018(v=office.15)
ms:contentKeyID: 48547165
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm3022
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 48e808fa27e468dd7cb651cb5784627d5064fea0
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870931"
---
# <a name="runsavedimportexport-macro-action"></a><span data-ttu-id="4f275-102">RunSavedImportExport 宏操作</span><span class="sxs-lookup"><span data-stu-id="4f275-102">RunSavedImportExport Macro Action</span></span>


<span data-ttu-id="4f275-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4f275-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4f275-104">可以使用 **RunSavedImportExport** 操作运行用"导入向导"或"导出向导"创建的已保存的导入或导出规格。</span><span class="sxs-lookup"><span data-stu-id="4f275-104">You can use the **RunSavedImportExport** action to run a saved import or export specification that you created by using the Import Wizard or the Export Wizard.</span></span>


> [!NOTE]
> <P><span data-ttu-id="4f275-p101">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="4f275-p101">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="4f275-107">设置</span><span class="sxs-lookup"><span data-stu-id="4f275-107">Setting</span></span>

<span data-ttu-id="4f275-108">**RunSavedImportExport** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="4f275-108">The **RunSavedImportExport** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4f275-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="4f275-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="4f275-110">说明</span><span class="sxs-lookup"><span data-stu-id="4f275-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f275-111"><strong>保存的导入/导出名称</strong></span><span class="sxs-lookup"><span data-stu-id="4f275-111"><strong>Saved Import Export Name</strong></span></span></p></td>
<td><p><span data-ttu-id="4f275-112">请从下拉列表中选择保存的导入规格或导出规格的名称。</span><span class="sxs-lookup"><span data-stu-id="4f275-112">Select the name of a saved import or export specification from the drop-down list.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4f275-113">说明</span><span class="sxs-lookup"><span data-stu-id="4f275-113">Remarks</span></span>

  - <span data-ttu-id="4f275-114">此宏操作等效于在 Access 中执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="4f275-114">This macro action has the same effect as performing the following procedure in Access:</span></span>
    
    1.  <span data-ttu-id="4f275-115">在 **"外部数据"** 选项卡上，单击 **"已保存的导入"** 或 **"已保存的导出"**。</span><span class="sxs-lookup"><span data-stu-id="4f275-115">On the **External Data** tab, click either **Saved Imports** or **Saved Exports**.</span></span>
    
    2.  <span data-ttu-id="4f275-116">在 **"管理数据任务"** 对话框的 **"已保存的导入"** 或 **"已保存的导出"** 选项卡（取决于前面步骤中的选择）上，单击要运行的规格。</span><span class="sxs-lookup"><span data-stu-id="4f275-116">In the **Manage Data Tasks** dialog box, on the **Saved Imports** or **Saved Exports** tab (depending on your choice in the preceding step), click the specification that you want to run.</span></span>
    
    3.  <span data-ttu-id="4f275-117">单击 **"运行"**。</span><span class="sxs-lookup"><span data-stu-id="4f275-117">Click **Run**.</span></span>

  - <span data-ttu-id="4f275-118">在运行 **RunSavedImportExport** 操作之前，请确保源文件和目标文件存在、源数据已经可以导入且操作不会意外覆盖目标文件中的任何数据。</span><span class="sxs-lookup"><span data-stu-id="4f275-118">Before running the **RunSavedImportExport** action, make sure that the source and destination files exist, the source data is ready for importing, and that the operation will not accidentally overwrite any data in your destination file.</span></span>

  - <span data-ttu-id="4f275-119">在 **请参阅**部分中可以找到有关保存和运行导入规格和导出规格的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="4f275-119">Find links to more information about saving and running import and export specifications in the **See Also** section.</span></span>

  - <span data-ttu-id="4f275-120">如果保存的导入或导出的规格您选择的创建宏后，将删除**保存导入/导出名称**参数，Access 将显示以下错误消息时运行宏：**具有指定索引规范执行不存在。指定一个不同的索引。**\* 规范名称 \***'。**</span><span class="sxs-lookup"><span data-stu-id="4f275-120">If the saved import or export specification you choose for the **Saved Import Export Name** argument is deleted after the macro is created, Access displays the following error message when the macro is run: **The specification with the specified index does not exist. Specify a different index. '\*\*\*\*\*specification name\*\*\*\*\*'.**</span></span>

