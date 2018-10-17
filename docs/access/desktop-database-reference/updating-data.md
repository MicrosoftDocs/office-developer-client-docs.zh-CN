---
title: 更新数据 （访问桌面数据库参考 （英文）
TOCTitle: Updating Data
ms:assetid: 02e82066-77c8-cbb2-db28-98e2fc94404c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248794(v=office.15)
ms:contentKeyID: 48542970
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2f507cb7d8939a4d4da65b570ae8e2db53cc8c7c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466438"
---
# <a name="updating-data"></a><span data-ttu-id="4b968-102">更新数据</span><span class="sxs-lookup"><span data-stu-id="4b968-102">Updating Data</span></span>


<span data-ttu-id="4b968-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4b968-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4b968-104">更新行为和更新功能在很大程度上取决于更新模式（锁定类型）、游标类型和游标位置。</span><span class="sxs-lookup"><span data-stu-id="4b968-104">Update behavior and functionality is largely dependent upon update mode (lock type), cursor type, and cursor location.</span></span>

<span data-ttu-id="4b968-p101">使用 **Update** 方法，可以保存在调用 **AddNew** 方法或更改现有记录中的任何字段值以来，对 **Recordset** 对象中的当前记录进行的任何更改。 **Recordset** 对象必须支持更新。</span><span class="sxs-lookup"><span data-stu-id="4b968-p101">Use the **Update** method to save any changes you have made to the current record of a **Recordset** object since calling the **AddNew** method or since changing any field values in an existing record. The **Recordset** object must support updates.</span></span>

<span data-ttu-id="4b968-p102">如果 **Recordset** 对象支持批更新，则在调用 **UpdateBatch** 方法前，可以在本地缓存对一个或多个记录所做的多次更改。如果在调用 **UpdateBatch** 方法时正在编辑当前记录或添加新记录，则 ADO 在将批更改传输到提供程序前，将自动调用 **Update** 方法将所有挂起的更改保存到当前记录。</span><span class="sxs-lookup"><span data-stu-id="4b968-p102">If the **Recordset** object supports batch updating, you can cache multiple changes to one or more records locally until you call the **UpdateBatch** method. If you are editing the current record or adding a new record when you call the **UpdateBatch** method, ADO will automatically call the **Update** method to save any pending changes to the current record before transmitting the batched changes to the provider.</span></span>

<span data-ttu-id="4b968-109">在调用 **Update** 或 **UpdateBatch** 方法之后，当前的记录将保持最新。</span><span class="sxs-lookup"><span data-stu-id="4b968-109">The current record remains current after you call the **Update** or **UpdateBatch** methods.</span></span>
