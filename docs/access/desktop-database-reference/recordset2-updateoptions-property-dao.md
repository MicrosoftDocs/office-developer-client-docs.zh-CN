---
title: UpdateOptions 属性 (DAO) Recordset2
TOCTitle: UpdateOptions Property
ms:assetid: 2692480e-c472-dd8e-f91a-939776822ece
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191899(v=office.15)
ms:contentKeyID: 48543816
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0d655ba231466ac41902dba3a1422ca02893938f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309090"
---
# <a name="recordset2updateoptions-property-dao"></a><span data-ttu-id="4ac2e-102">UpdateOptions 属性 (DAO) Recordset2</span><span class="sxs-lookup"><span data-stu-id="4ac2e-102">Recordset2.UpdateOptions property (DAO)</span></span>


<span data-ttu-id="4ac2e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="4ac2e-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="4ac2e-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ac2e-104">Syntax</span></span>

<span data-ttu-id="4ac2e-105">*表达式*。UpdateOptions</span><span class="sxs-lookup"><span data-stu-id="4ac2e-105">*expression* .UpdateOptions</span></span>

<span data-ttu-id="4ac2e-106">*表达式*一个代表**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-106">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ac2e-107">注解</span><span class="sxs-lookup"><span data-stu-id="4ac2e-107">Remarks</span></span>

<span data-ttu-id="4ac2e-108">当执行批处理模式的 **[Update](recordset2-update-method-dao.md)** 时，DAO 和客户端批处理光标库创建一系列 SQL UPDATE 语句，以进行所需的更改。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-108">When a batch-mode **[Update](recordset2-update-method-dao.md)** is executed, DAO and the client batch cursor library create a series of SQL UPDATE statements to make the needed changes.</span></span> <span data-ttu-id="4ac2e-109">为每次更新创建了 SQL WHERE 子句，以便隔离被 **[RecordStatus](recordset2-recordstatus-property-dao.md)** 属性标记为已更改的记录。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-109">An SQL WHERE clause is created for each update to isolate the records that are marked as changed by the **[RecordStatus](recordset2-recordstatus-property-dao.md)** property.</span></span> <span data-ttu-id="4ac2e-110">由于某些远程服务器使用触发器或其他方法实施参照完整性，所以将更新的字段限制为受更改影响的那些记录通常是很有必要的。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-110">Because some remote servers use triggers or other ways to enforce referential integrity, is it often important to limit the fields being updated to just those affected by the change.</span></span> 

<span data-ttu-id="4ac2e-111">为此，需要将 **UpdateOptions** 属性设置为常量 **dbCriteriaKey**、 **dbCriteriaModValues**、 **dbCriteriaAllCols** 或 **dbCriteriaTimeStamp** 之一。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-111">To do this, set the **UpdateOptions** property to one of the constants **dbCriteriaKey**, **dbCriteriaModValues**, **dbCriteriaAllCols**, or **dbCriteriaTimeStamp**.</span></span> <span data-ttu-id="4ac2e-112">这样，将只执行触发器代码的最小绝对量。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-112">This way, only the absolute minimum amount of trigger code is executed.</span></span> <span data-ttu-id="4ac2e-113">因此，可以更快速地执行更新操作，潜在错误也会较少。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-113">As a result, the update operation is executed more quickly, and with fewer potential errors.</span></span>

<span data-ttu-id="4ac2e-p103">还可以连接 **dbCriteriaDeleteInsert** 或 **dbCriteriaUpdate**，以确定在将批修改发送回服务器时，对于每次更新是使用 SQL DELETE 和 INSERT 语句集合，还是使用 SQL UPDATE 语句。在前一种情况下，需要两个单独操作才能更新记录。在某些情况下，尤其是远程系统实施 DELETE、INSERT 和 UPDATE 触发器时，选择正确的 **UpdateOptions** 属性设置会显著影响性能。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-p103">You can also concatenate either of the constants **dbCriteriaDeleteInsert** or **dbCriteriaUpdate** to determine whether to use a set of SQL DELETE and INSERT statements or an SQL UPDATE statement for each update when sending batched modifications back to the server. In the former case, two separate operations are required to update the record. In some cases, especially where the remote system implements DELETE, INSERT, and UPDATE triggers, choosing the correct **UpdateOptions** property setting can significantly impact performance.</span></span>

<span data-ttu-id="4ac2e-117">如果您不指定任何常量，将使用 **dbCriteriaUpdate** 和 **dbCriteriaKey**。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-117">If you don't specify any constants, **dbCriteriaUpdate** and **dbCriteriaKey** will be used.</span></span>

<span data-ttu-id="4ac2e-118">新添加的记录始终生成 INSERT 语句，删除的记录始终生成 DELETE 语句，所以该属性只对光标库如何更新修改的记录适用。</span><span class="sxs-lookup"><span data-stu-id="4ac2e-118">Newly added records will always generate INSERT statements and deleted records will always generate DELETE statements, so this property only applies to how the cursor library updates modified records.</span></span>

