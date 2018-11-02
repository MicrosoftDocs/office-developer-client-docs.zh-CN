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
ms.openlocfilehash: 70fda733ae05a94af856a76fba231e6a1da001d1
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928227"
---
# <a name="runsavedimportexport-macro-action"></a>RunSavedImportExport 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **RunSavedImportExport** 操作运行用"导入向导"或"导出向导"创建的已保存的导入或导出规格。


> [!NOTE]
> <P>[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</P>



## <a name="setting"></a>设置

**RunSavedImportExport** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>保存的导入/导出名称</strong></p></td>
<td><p>请从下拉列表中选择保存的导入规格或导出规格的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

  - 此宏操作等效于在 Access 中执行以下过程：
    
    1.  在 **"外部数据"** 选项卡上，单击 **"已保存的导入"** 或 **"已保存的导出"**。
    
    2.  在 **"管理数据任务"** 对话框的 **"已保存的导入"** 或 **"已保存的导出"** 选项卡（取决于前面步骤中的选择）上，单击要运行的规格。
    
    3.  单击 **"运行"**。

  - 在运行 **RunSavedImportExport** 操作之前，请确保源文件和目标文件存在、源数据已经可以导入且操作不会意外覆盖目标文件中的任何数据。

  - 在 **请参阅**部分中可以找到有关保存和运行导入规格和导出规格的详细信息的链接。

  - 如果保存的导入或导出的规格您选择的创建宏后，将删除**保存导入/导出名称**参数，Access 将显示以下错误消息时运行宏：**具有指定索引规范执行不存在。指定一个不同的索引。*** 规范名称 ***'。**

