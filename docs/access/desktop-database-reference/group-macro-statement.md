---
title: Group 宏语句
TOCTitle: Group Macro Statement
ms:assetid: 42aa4afa-ab5d-9dcc-2182-786f025e316d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192918(v=office.15)
ms:contentKeyID: 48544481
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 189744d228db0dadd3260ce77457daf8724828f8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467013"
---
# <a name="group-macro-statement"></a><span data-ttu-id="8e2c7-102">Group 宏语句</span><span class="sxs-lookup"><span data-stu-id="8e2c7-102">Group Macro Statement</span></span>


<span data-ttu-id="8e2c7-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8e2c7-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8e2c7-104">**使用 Group**语句，可以指定一个块中的宏，您可以展开或折叠的操作。</span><span class="sxs-lookup"><span data-stu-id="8e2c7-104">The **Group** statement enables you to specify a block of actions within a macro that you can expand or collapse.</span></span>

## <a name="setting"></a><span data-ttu-id="8e2c7-105">设置</span><span class="sxs-lookup"><span data-stu-id="8e2c7-105">Setting</span></span>

<span data-ttu-id="8e2c7-106">**Group** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="8e2c7-106">The **Group** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8e2c7-107">参数</span><span class="sxs-lookup"><span data-stu-id="8e2c7-107">Argument</span></span></p></th>
<th><p><span data-ttu-id="8e2c7-108">是否必需</span><span class="sxs-lookup"><span data-stu-id="8e2c7-108">Required</span></span></p></th>
<th><p><span data-ttu-id="8e2c7-109">说明</span><span class="sxs-lookup"><span data-stu-id="8e2c7-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2c7-110"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="8e2c7-110"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2c7-111">否</span><span class="sxs-lookup"><span data-stu-id="8e2c7-111">No</span></span></p></td>
<td><p><span data-ttu-id="8e2c7-112">一个在折叠时显示为组标题的字符串。</span><span class="sxs-lookup"><span data-stu-id="8e2c7-112">A string that appears as the title of a group when it is collapsed.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="8e2c7-113">注释</span><span class="sxs-lookup"><span data-stu-id="8e2c7-113">Remarks</span></span>

<span data-ttu-id="8e2c7-p101">**Group** 语句不定义可以单独执行的宏区域。使用 **[Submacro](submacro-macro-statement.md)** 语句可定义要在 **"宏设计器"** 窗口中单独执行的一组操作。</span><span class="sxs-lookup"><span data-stu-id="8e2c7-p101">The **Group** statment does not define a region of a macro that can be executed separately. Use the **[Submacro](submacro-macro-statement.md)** statment to define a set of actions to be executed separately in the **Macro Designer** window.</span></span>
