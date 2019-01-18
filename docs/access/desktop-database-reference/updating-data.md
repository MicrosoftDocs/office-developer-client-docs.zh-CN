---
title: 更新数据 （访问桌面数据库参考 （英文）
TOCTitle: Updating Data
ms:assetid: 02e82066-77c8-cbb2-db28-98e2fc94404c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248794(v=office.15)
ms:contentKeyID: 48542970
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8e6989468e23fc1c9c611eb091172822a6ffe938
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726335"
---
# <a name="updating-data"></a><span data-ttu-id="bbcda-102">更新数据</span><span class="sxs-lookup"><span data-stu-id="bbcda-102">Updating data</span></span>


<span data-ttu-id="bbcda-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bbcda-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bbcda-104">更新行为和更新功能在很大程度上取决于更新模式（锁定类型）、游标类型和游标位置。</span><span class="sxs-lookup"><span data-stu-id="bbcda-104">Update behavior and functionality is largely dependent upon update mode (lock type), cursor type, and cursor location.</span></span>

<span data-ttu-id="bbcda-p101">使用 **Update** 方法，可以保存在调用 **AddNew** 方法或更改现有记录中的任何字段值以来，对 **Recordset** 对象中的当前记录进行的任何更改。 **Recordset** 对象必须支持更新。</span><span class="sxs-lookup"><span data-stu-id="bbcda-p101">Use the **Update** method to save any changes you have made to the current record of a **Recordset** object since calling the **AddNew** method or since changing any field values in an existing record. The **Recordset** object must support updates.</span></span>

<span data-ttu-id="bbcda-p102">如果 **Recordset** 对象支持批更新，则在调用 **UpdateBatch** 方法前，可以在本地缓存对一个或多个记录所做的多次更改。如果在调用 **UpdateBatch** 方法时正在编辑当前记录或添加新记录，则 ADO 在将批更改传输到提供程序前，将自动调用 **Update** 方法将所有挂起的更改保存到当前记录。</span><span class="sxs-lookup"><span data-stu-id="bbcda-p102">If the **Recordset** object supports batch updating, you can cache multiple changes to one or more records locally until you call the **UpdateBatch** method. If you are editing the current record or adding a new record when you call the **UpdateBatch** method, ADO will automatically call the **Update** method to save any pending changes to the current record before transmitting the batched changes to the provider.</span></span>

<span data-ttu-id="bbcda-109">在调用 **Update** 或 **UpdateBatch** 方法之后，当前的记录将保持最新。</span><span class="sxs-lookup"><span data-stu-id="bbcda-109">The current record remains current after you call the **Update** or **UpdateBatch** methods.</span></span>

<span data-ttu-id="bbcda-110">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="bbcda-110">This section includes the following topics:</span></span>

- [<span data-ttu-id="bbcda-111">直接模式</span><span class="sxs-lookup"><span data-stu-id="bbcda-111">Immediate mode</span></span>](immediate-mode.md)
- [<span data-ttu-id="bbcda-112">事务处理</span><span class="sxs-lookup"><span data-stu-id="bbcda-112">Transaction processing</span></span>](transaction-processing.md)
- [<span data-ttu-id="bbcda-113">批模式 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bbcda-113">Batch mode (ADO)</span></span>](batch-mode.md)

