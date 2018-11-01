---
title: Group 宏语句
TOCTitle: Group Macro Statement
ms:assetid: 42aa4afa-ab5d-9dcc-2182-786f025e316d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192918(v=office.15)
ms:contentKeyID: 48544481
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 35f9ad1d445dbddaa5487e28da60b9202a72dae1
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879849"
---
# <a name="group-macro-statement"></a><span data-ttu-id="d39be-102">Group 宏语句</span><span class="sxs-lookup"><span data-stu-id="d39be-102">Group Macro Statement</span></span>


<span data-ttu-id="d39be-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d39be-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d39be-104">**使用 Group**语句，可以指定一个块中的宏，您可以展开或折叠的操作。</span><span class="sxs-lookup"><span data-stu-id="d39be-104">The **Group** statement enables you to specify a block of actions within a macro that you can expand or collapse.</span></span>

## <a name="setting"></a><span data-ttu-id="d39be-105">设置</span><span class="sxs-lookup"><span data-stu-id="d39be-105">Setting</span></span>

<span data-ttu-id="d39be-106">**Group** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="d39be-106">The **Group** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d39be-107">参数</span><span class="sxs-lookup"><span data-stu-id="d39be-107">Argument</span></span></p></th>
<th><p><span data-ttu-id="d39be-108">是否必需</span><span class="sxs-lookup"><span data-stu-id="d39be-108">Required</span></span></p></th>
<th><p><span data-ttu-id="d39be-109">说明</span><span class="sxs-lookup"><span data-stu-id="d39be-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d39be-110"><strong>Description</strong></span><span class="sxs-lookup"><span data-stu-id="d39be-110"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="d39be-111">否</span><span class="sxs-lookup"><span data-stu-id="d39be-111">No</span></span></p></td>
<td><p><span data-ttu-id="d39be-112">一个在折叠时显示为组标题的字符串。</span><span class="sxs-lookup"><span data-stu-id="d39be-112">A string that appears as the title of a group when it is collapsed.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="d39be-113">注释</span><span class="sxs-lookup"><span data-stu-id="d39be-113">Remarks</span></span>

<span data-ttu-id="d39be-p101">**Group** 语句不定义可以单独执行的宏区域。使用 **[Submacro](submacro-macro-statement.md)** 语句可定义要在 **"宏设计器"** 窗口中单独执行的一组操作。</span><span class="sxs-lookup"><span data-stu-id="d39be-p101">The **Group** statment does not define a region of a macro that can be executed separately. Use the **[Submacro](submacro-macro-statement.md)** statment to define a set of actions to be executed separately in the **Macro Designer** window.</span></span>

