---
title: 添加记录 （访问桌面数据库参考 （英文）
TOCTitle: Adding records
ms:assetid: 7a5b27bc-7b28-4f43-b55e-a21edfb9e1b3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249505(v=office.15)
ms:contentKeyID: 48545791
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 177eeb0499f3ba3376237c4773e776f8c7c7583f
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946508"
---
# <a name="adding-records"></a><span data-ttu-id="5f9aa-102">添加记录</span><span class="sxs-lookup"><span data-stu-id="5f9aa-102">Adding records</span></span>

<span data-ttu-id="5f9aa-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5f9aa-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5f9aa-p101">使用 **AddNew** 方法在现有 **Recordset** 中创建并初始化新的记录。您可以使用 **Supports** 方法和 **adAddNew** 的 **CursorOptionEnum** 值来验证是否可以向当前 **Recordset** 对象添加记录。</span><span class="sxs-lookup"><span data-stu-id="5f9aa-p101">Use the **AddNew** method to create and initialize a new record in an existing **Recordset**. You can use the **Supports** method with a **CursorOptionEnum** value of **adAddNew** to verify whether you can add records to the current **Recordset** object.</span></span>

<span data-ttu-id="5f9aa-p102">在调用 **AddNew** 方法后，新记录会变为当前记录并在调用 **Update** 方法后仍然保持当前状态。如果 **Recordset** 对象不支持书签，则在转到其他记录后，您可能无法访问新记录。因此，根据游标类型，您可能希望调用 **Requery** 方法来使新记录可以访问。</span><span class="sxs-lookup"><span data-stu-id="5f9aa-p102">After you call the **AddNew** method, the new record becomes the current record and remains current after you call the **Update** method. If the **Recordset** object does not support bookmarks, you might not be able to access the new record once you move to another record. Therefore, depending on your cursor type, you might need to call the **Requery** method to make the new record accessible.</span></span>

<span data-ttu-id="5f9aa-109">如果在编辑当前记录或添加新记录时调用 **AddNew** ，则 ADO 会调用 **Update** 方法来保存所有更改，然后创建新记录。</span><span class="sxs-lookup"><span data-stu-id="5f9aa-109">If you call **AddNew** while editing the current record or while adding a new record, ADO calls the **Update** method to save any changes and then creates the new record.</span></span>

<span data-ttu-id="5f9aa-110">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="5f9aa-110">This section includes the following topics:</span></span>

- [<span data-ttu-id="5f9aa-111">添加多个字段</span><span class="sxs-lookup"><span data-stu-id="5f9aa-111">Adding multiple fields</span></span>](adding-multiple-fields.md)
- [<span data-ttu-id="5f9aa-112">确定编辑模式</span><span class="sxs-lookup"><span data-stu-id="5f9aa-112">Determining Edit mode</span></span>](determining-edit-mode.md)
- [<span data-ttu-id="5f9aa-113">在即时和批模式下使用 AddNew</span><span class="sxs-lookup"><span data-stu-id="5f9aa-113">Using AddNew in Immediate and Batch modes</span></span>](using-addnew-in-immediate-and-batch-modes.md)

