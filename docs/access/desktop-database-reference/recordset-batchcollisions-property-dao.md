---
title: BatchCollisions 属性 (DAO)
TOCTitle: BatchCollisions Property
ms:assetid: 53e5572b-770c-9ea5-31a5-984abdf66faa
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194079(v=office.15)
ms:contentKeyID: 48544881
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 61f60567ac170a0ecde2d4bd46589d2308b7788f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300859"
---
# <a name="recordsetbatchcollisions-property-dao"></a><span data-ttu-id="6de39-102">BatchCollisions 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="6de39-102">Recordset.BatchCollisions property (DAO)</span></span>


<span data-ttu-id="6de39-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6de39-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="6de39-104">语法</span><span class="sxs-lookup"><span data-stu-id="6de39-104">Syntax</span></span>

<span data-ttu-id="6de39-105">*表达式*。BatchCollisions</span><span class="sxs-lookup"><span data-stu-id="6de39-105">*expression* .BatchCollisions</span></span>

<span data-ttu-id="6de39-106">*表达式*一个代表**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6de39-106">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6de39-107">注解</span><span class="sxs-lookup"><span data-stu-id="6de39-107">Remarks</span></span>

<span data-ttu-id="6de39-p101">该属性包含一个书签数组，用于指示上次尝试的批 **[Update](recordset-update-method-dao.md)** 调用中遇到冲突的行。 **[BatchCollisionCount](recordset-batchcollisioncount-property-dao.md)** 属性指示该数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="6de39-p101">This property contains an array of bookmarks to rows that encountered a collision during the last attempted batch **[Update](recordset-update-method-dao.md)** call. The **[BatchCollisionCount](recordset-batchcollisioncount-property-dao.md)** property indicates the number of elements in the array.</span></span>

<span data-ttu-id="6de39-110">如果将正在工作的 **[Recordset](recordset-object-dao.md)** 对象的 **[Bookmark](recordset-bookmark-property-dao.md)** 属性设置为 **BatchCollisions** 数组中的书签值，则可以移到无法完成最近一次批模式更新操作的每条记录。</span><span class="sxs-lookup"><span data-stu-id="6de39-110">If you set the working **[Recordset](recordset-object-dao.md)** object's **[Bookmark](recordset-bookmark-property-dao.md)** property to bookmark values in the **BatchCollisions** array, you can move to each record that failed to complete the most recent batch-mode Update operation.</span></span>

<span data-ttu-id="6de39-p102">更正冲突记录后，可再次调用批模式 **Update** 方法。此时，DAO 将尝试进行另一次批更新，同时 **BatchCollisions** 属性将再次反映第二次尝试失败的记录集。不会在当前尝试中发送上一次尝试成功的任何记录，因为这些记录的 **[RecordStatus](recordset-recordstatus-property-dao.md)** 属性现在已经为 dbRecordUnmodified。只要发生冲突，此过程就会继续下去，直到您放弃更新并关闭结果集为止。</span><span class="sxs-lookup"><span data-stu-id="6de39-p102">After the collision records are corrected, you can call the batch mode **Update** method again. At this point DAO attempts another batch update, and the **BatchCollisions** property again reflects the set of records that failed the second attempt. Any records that succeeded in the previous attempt are not sent in the current attempt, as they now have a **[RecordStatus](recordset-recordstatus-property-dao.md)** property of dbRecordUnmodified. This process can continue as long as collisions occur, or until you abandon the updates and close the result set.</span></span>

<span data-ttu-id="6de39-115">每次执行批模式的 **Update** 方法时，都会重新创建此数组。</span><span class="sxs-lookup"><span data-stu-id="6de39-115">This array is re-created each time you execute a batch-mode **Update** method.</span></span>

