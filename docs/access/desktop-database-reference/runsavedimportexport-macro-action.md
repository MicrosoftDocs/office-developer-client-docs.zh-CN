---
title: RunSavedImportExport 宏操作
TOCTitle: RunSavedImportExport macro action
ms:assetid: b2449c51-ee20-6e50-87f3-a45adc0b0dde
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822018(v=office.15)
ms:contentKeyID: 48547165
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm3022
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: adcc8a2a9462509f4b37d2dbdaf824387ae52a26
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309170"
---
# <a name="runsavedimportexport-macro-action"></a><span data-ttu-id="07b42-102">RunSavedImportExport 宏操作</span><span class="sxs-lookup"><span data-stu-id="07b42-102">RunSavedImportExport macro action</span></span>

<span data-ttu-id="07b42-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="07b42-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="07b42-104">可以使用 **RunSavedImportExport** 操作运行用"导入向导"或"导出向导"创建的已保存的导入或导出规格。</span><span class="sxs-lookup"><span data-stu-id="07b42-104">You can use the **RunSavedImportExport** action to run a saved import or export specification that you created by using the Import Wizard or the Export Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="07b42-105">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="07b42-105">This action will not be allowed if the database is not trusted.</span></span>

## <a name="setting"></a><span data-ttu-id="07b42-106">设置</span><span class="sxs-lookup"><span data-stu-id="07b42-106">Setting</span></span>

<span data-ttu-id="07b42-107">**RunSavedImportExport** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="07b42-107">The **RunSavedImportExport** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="07b42-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="07b42-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="07b42-109">说明</span><span class="sxs-lookup"><span data-stu-id="07b42-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07b42-110"><strong>保存的导入/导出名称</strong></span><span class="sxs-lookup"><span data-stu-id="07b42-110"><strong>Saved Import Export Name</strong></span></span></p></td>
<td><p><span data-ttu-id="07b42-111">请从下拉列表中选择保存的导入规格或导出规格的名称。</span><span class="sxs-lookup"><span data-stu-id="07b42-111">Select the name of a saved import or export specification from the drop-down list.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="07b42-112">注解</span><span class="sxs-lookup"><span data-stu-id="07b42-112">Remarks</span></span>

- <span data-ttu-id="07b42-113">此宏操作等效于在 Access 中执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="07b42-113">This macro action has the same effect as performing the following procedure in Access:</span></span>
    
  1.  <span data-ttu-id="07b42-114">在 **“外部数据”** 选项卡上，单击 **“已保存的导入”** 或 **“已保存的导出”**。</span><span class="sxs-lookup"><span data-stu-id="07b42-114">On the **External Data** tab, click either **Saved Imports** or **Saved Exports**.</span></span>
    
  2.  <span data-ttu-id="07b42-115">在 **“管理数据任务”** 对话框的 **“已保存的导入”** 或 **“已保存的导出”** 选项卡（取决于前面步骤中的选择)上，单击要运行的规格。</span><span class="sxs-lookup"><span data-stu-id="07b42-115">In the **Manage Data Tasks** dialog box, on the **Saved Imports** or **Saved Exports** tab (depending on your choice in the preceding step), click the specification that you want to run.</span></span>
    
  3.  <span data-ttu-id="07b42-116">单击 **"运行"**。</span><span class="sxs-lookup"><span data-stu-id="07b42-116">Click **Run**.</span></span>

- <span data-ttu-id="07b42-117">在运行 **RunSavedImportExport** 操作之前，请确保源文件和目标文件存在、源数据已经可以导入且操作不会意外覆盖目标文件中的任何数据。</span><span class="sxs-lookup"><span data-stu-id="07b42-117">Before running the **RunSavedImportExport** action, make sure that the source and destination files exist, the source data is ready for importing, and that the operation will not accidentally overwrite any data in your destination file.</span></span>

- <span data-ttu-id="07b42-118">在 **请参阅**部分中可以找到有关保存和运行导入规格和导出规格的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="07b42-118">Find links to more information about saving and running import and export specifications in the **See Also** section.</span></span>

- <span data-ttu-id="07b42-119">如果在创建宏后, 为**保存的导入导出名称**参数选择的已保存的导入或导出规格已删除, 则在运行该宏时, Access 将显示以下错误消息:\*\*具有指定索引的规范将执行不存在。指定一个不同的索引。' \* \* \* \* \* 规范名称 \* \*\*\* \* \* \* '。</span><span class="sxs-lookup"><span data-stu-id="07b42-119">If the saved import or export specification you choose for the **Saved Import Export Name** argument is deleted after the macro is created, Access displays the following error message when the macro is run: **The specification with the specified index does not exist. Specify a different index. '\*\*\*\*\*specification name\*\*\*\*\*'.**</span></span>

