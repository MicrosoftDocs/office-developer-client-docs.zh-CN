---
title: 与记录集相关的错误信息
TOCTitle: Recordset-Related Error Information
ms:assetid: 388308c7-e121-bd12-228a-312c897b8c55
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249136(v=office.15)
ms:contentKeyID: 48544222
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 62f9a6d235b6c06ad8e7fa49d7b89960fd1ad2b5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467830"
---
# <a name="recordset-related-error-information"></a><span data-ttu-id="87658-102">与记录集相关的错误信息</span><span class="sxs-lookup"><span data-stu-id="87658-102">Recordset-Related Error Information</span></span>


<span data-ttu-id="87658-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="87658-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="87658-104">在批处理期间， **Recordset** 对象的 **Status** 属性将提供 **Recordset** 中各个记录的信息。</span><span class="sxs-lookup"><span data-stu-id="87658-104">During batch processing, the **Status** property of the **Recordset** object provides information about the individual records in the **Recordset**.</span></span> <span data-ttu-id="87658-105">发生批更新之前， **Recordset** 的 **Status** 属性可以反映将要添加、更改和删除的记录的相关信息。</span><span class="sxs-lookup"><span data-stu-id="87658-105">Before a batch update takes place, the **Status** property of the **Recordset** reflects information about records to be added, changed and deleted.</span></span> 

<span data-ttu-id="87658-106">调用 **UpdateBatch** 之后， **Status** 属性将指示操作成功或失败。</span><span class="sxs-lookup"><span data-stu-id="87658-106">After **UpdateBatch** has been called, the **Status** property indicates the success or failure of the operation.</span></span> <span data-ttu-id="87658-107">在 **Recordset** 中从一条记录移动到另一条记录时， **Status** 属性的值将发生更改，以描述当前记录的状态。</span><span class="sxs-lookup"><span data-stu-id="87658-107">As you move from record to record in the **Recordset,** the value of the **Status** property changes to describe the status of the current record.</span></span>

