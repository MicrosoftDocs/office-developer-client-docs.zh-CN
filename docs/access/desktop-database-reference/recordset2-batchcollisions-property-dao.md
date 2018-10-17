---
title: Recordset2.BatchCollisions Property (DAO)
TOCTitle: BatchCollisions Property
ms:assetid: 07d6c25f-baf5-f7d6-d225-0447e0f78fe6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844993(v=office.15)
ms:contentKeyID: 48543085
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101180
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 204b66b120405522707da23bf093a311ca8c2625
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467325"
---
# <a name="recordset2batchcollisions-property-dao"></a><span data-ttu-id="3f7f3-102">Recordset2.BatchCollisions Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="3f7f3-102">Recordset2.BatchCollisions Property (DAO)</span></span>


<span data-ttu-id="3f7f3-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3f7f3-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="3f7f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f7f3-104">Syntax</span></span>

<span data-ttu-id="3f7f3-105">*表达式*。BatchCollisions</span><span class="sxs-lookup"><span data-stu-id="3f7f3-105">*expression* .BatchCollisions</span></span>

<span data-ttu-id="3f7f3-106">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="3f7f3-106">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f7f3-107">注解</span><span class="sxs-lookup"><span data-stu-id="3f7f3-107">Remarks</span></span>

<span data-ttu-id="3f7f3-p101">该属性包含一个书签数组，用于指示上次尝试的批 **[Update](recordset2-update-method-dao.md)** 调用中遇到冲突的行。 **[BatchCollisionCount](recordset2-batchcollisioncount-property-dao.md)** 属性指示该数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="3f7f3-p101">This property contains an array of bookmarks to rows that encountered a collision during the last attempted batch **[Update](recordset2-update-method-dao.md)** call. The **[BatchCollisionCount](recordset2-batchcollisioncount-property-dao.md)** property indicates the number of elements in the array.</span></span>

<span data-ttu-id="3f7f3-110">如果将正在工作的 **Recordset** 对象的 **[Bookmark](recordset2-bookmark-property-dao.md)** 属性设置为 **BatchCollisions** 数组中的书签值，则可以移到无法完成最近一次批模式更新操作的每条记录。</span><span class="sxs-lookup"><span data-stu-id="3f7f3-110">If you set the working **Recordset** object's **[Bookmark](recordset2-bookmark-property-dao.md)** property to bookmark values in the **BatchCollisions** array, you can move to each record that failed to complete the most recent batch-mode Update operation.</span></span>

<span data-ttu-id="3f7f3-p102">更正冲突记录后，可再次调用批模式 **Update** 方法。此时，DAO 将尝试进行另一次批更新，同时 **BatchCollisions** 属性将再次反映第二次尝试失败的记录集。不会在当前尝试中发送上一次尝试成功的任何记录，因为这些记录的 **[RecordStatus](recordset2-recordstatus-property-dao.md)** 属性现在已经为 dbRecordUnmodified。只要发生冲突，此过程就会继续下去，直到您放弃更新并关闭结果集为止。</span><span class="sxs-lookup"><span data-stu-id="3f7f3-p102">After the collision records are corrected, you can call the batch mode **Update** method again. At this point DAO attempts another batch update, and the **BatchCollisions** property again reflects the set of records that failed the second attempt. Any records that succeeded in the previous attempt are not sent in the current attempt, as they now have a **[RecordStatus](recordset2-recordstatus-property-dao.md)** property of dbRecordUnmodified. This process can continue as long as collisions occur, or until you abandon the updates and close the result set.</span></span>

<span data-ttu-id="3f7f3-115">每次执行批模式的 **Update** 方法时，都会重新创建此数组。</span><span class="sxs-lookup"><span data-stu-id="3f7f3-115">This array is re-created each time you execute a batch-mode **Update** method.</span></span>
