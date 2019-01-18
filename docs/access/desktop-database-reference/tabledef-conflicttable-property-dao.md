---
title: TableDef.ConflictTable 属性 (DAO)
TOCTitle: ConflictTable Property
ms:assetid: 0db8b975-eb6d-19c6-cfb7-6ce01230ebe4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845218(v=office.15)
ms:contentKeyID: 48543228
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053356
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 0189a5163dd5e225ad34841264cf84e85785d7fb
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718915"
---
# <a name="tabledefconflicttable-property-dao"></a><span data-ttu-id="1d59c-102">TableDef.ConflictTable 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="1d59c-102">TableDef.ConflictTable property (DAO)</span></span>


<span data-ttu-id="1d59c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1d59c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1d59c-p101">返回冲突表（其中包含同步两个副本的过程中发生冲突的数据库记录）的名称（仅适用于 Microsoft Access 工作区）。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="1d59c-p101">Returns the name of a conflict table containing the database records that conflicted during the synchronization of two replicas (Microsoft Access workspaces only). Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="1d59c-106">语法</span><span class="sxs-lookup"><span data-stu-id="1d59c-106">Syntax</span></span>

<span data-ttu-id="1d59c-107">*表达式*。ConflictTable</span><span class="sxs-lookup"><span data-stu-id="1d59c-107">*expression* .ConflictTable</span></span>

<span data-ttu-id="1d59c-108">*表达式*一个返回**TableDef**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="1d59c-108">*expression* An expression that returns a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d59c-109">注解</span><span class="sxs-lookup"><span data-stu-id="1d59c-109">Remarks</span></span>

<span data-ttu-id="1d59c-110">如果不存在冲突表，或者数据库不是副本，则返回值为 **String** 数据类型的零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="1d59c-110">The return value is a **String** data type that is a zero-length string ("") if there is no conflict table or the database isn't a replica.</span></span>

<span data-ttu-id="1d59c-p102">如果两个用户在不同的副本位置对数据库中的相同记录各自执行了更改，则其中一个用户所做的更改将无法应用到另一个副本。因此，更改失败的那个用户必须解决冲突。</span><span class="sxs-lookup"><span data-stu-id="1d59c-p102">If two users at two separate replicas each make a change to the same record in the database, the changes made by one user will fail to be applied to the other replica. Consequently, the user with the failed change must resolve the conflicts.</span></span>

<span data-ttu-id="1d59c-p103">冲突是在记录级别发生的，而不是在字段之间发生的。例如，如果一个用户更改了 Address 字段，而另一个用户更新了同一记录中的 Phone 字段，则会拒绝其中一项更改。由于冲突在记录级别发生，因此，即使成功的更改和拒绝的更改在事实上不太可能会导致信息冲突，也会发生拒绝。</span><span class="sxs-lookup"><span data-stu-id="1d59c-p103">Conflicts occur at the record level, not between fields. For example, if one user changes the Address field and another updates the Phone field in the same record, then one change is rejected. Because conflicts occur at the record level, the rejection occurs even though the successful change and the rejected change are unlikely to result in a true conflict of information.</span></span>

<span data-ttu-id="1d59c-p104">同步机制通过创建冲突表来处理记录冲突。冲突表包含本应在更改成功后放入到表中的信息。您可以检查这些冲突表，并逐行处理，修复一切适用的项目。</span><span class="sxs-lookup"><span data-stu-id="1d59c-p104">The synchronization mechanism handles the record conflicts by creating conflict tables, which contain the information that would have been placed in the table, if the change had been successful. You can examine these conflict tables and work through them row by row, fixing whatever is appropriate.</span></span>

<span data-ttu-id="1d59c-118">所有冲突表已都命名表\_冲突，其中 table 是表中，截断为最大的表名称长度的原始名称。</span><span class="sxs-lookup"><span data-stu-id="1d59c-118">All conflict tables are named table\_conflict, where table is the original name of the table, truncated to the maximum table name length.</span></span>

