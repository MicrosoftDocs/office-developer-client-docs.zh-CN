---
title: DeleteRecord 宏操作
TOCTitle: DeleteRecord macro action
ms:assetid: c656a72c-c037-76a5-dc07-f6eccb6590dd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823132(v=office.15)
ms:contentKeyID: 48547624
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8fb20068052972696b09ea0d2165b344e97ea922
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294013"
---
# <a name="deleterecord-macro-action"></a><span data-ttu-id="bc486-102">DeleteRecord 宏操作</span><span class="sxs-lookup"><span data-stu-id="bc486-102">DeleteRecord macro action</span></span>

<span data-ttu-id="bc486-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bc486-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bc486-104">可以使用 **DeleteRecord** 操作删除记录。</span><span class="sxs-lookup"><span data-stu-id="bc486-104">You can use the **DeleteRecord** action to delete a record.</span></span>

## <a name="setting"></a><span data-ttu-id="bc486-105">Setting</span><span class="sxs-lookup"><span data-stu-id="bc486-105">Setting</span></span>

<span data-ttu-id="bc486-106">**DeleteRecord** 数据块具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="bc486-106">The **CreateRecord** data block has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bc486-107">参数</span><span class="sxs-lookup"><span data-stu-id="bc486-107">Argument</span></span></p></th>
<th><p><span data-ttu-id="bc486-108">说明</span><span class="sxs-lookup"><span data-stu-id="bc486-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc486-109"><strong>Record Alias</strong></span><span class="sxs-lookup"><span data-stu-id="bc486-109"><strong>Record Alias</strong></span></span></p></td>
<td><p><span data-ttu-id="bc486-110">一个用于标识要删除的记录的字符串。</span><span class="sxs-lookup"><span data-stu-id="bc486-110">A string that identifies the record to delete.</span></span> <span data-ttu-id="bc486-111">如果未指定 <em>Alias</em> 参数，则会删除当前记录。</span><span class="sxs-lookup"><span data-stu-id="bc486-111">If the <em>Alias</em> argument is not specified, then the current record is deleted.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a><span data-ttu-id="bc486-112">注解</span><span class="sxs-lookup"><span data-stu-id="bc486-112">Remarks</span></span>

<span data-ttu-id="bc486-113">您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。</span><span class="sxs-lookup"><span data-stu-id="bc486-113">You can use the **LastCreateRecordIdentity** local variable to work with last record created in a **CreateRecord** data block.</span></span> <span data-ttu-id="bc486-114">例如, 使用以下语法来引用最近创建的记录:</span><span class="sxs-lookup"><span data-stu-id="bc486-114">For example, use the following syntax to refer to the most recently created record:</span></span>

`[LastCreateRecordIdentity]`

