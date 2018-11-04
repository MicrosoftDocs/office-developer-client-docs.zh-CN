---
title: Delete 方法（ADO 记录集）
TOCTitle: Delete method (ADO Recordset)
ms:assetid: 62c39b4d-223e-7b48-6780-6cd272e3114e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249374(v=office.15)
ms:contentKeyID: 48545246
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3a7ab998052cc08aa57320d05e46542b84282e6c
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949507"
---
# <a name="delete-method-ado-recordset"></a><span data-ttu-id="b59f7-102">Delete 方法（ADO 记录集）</span><span class="sxs-lookup"><span data-stu-id="b59f7-102">Delete method (ADO Recordset)</span></span>

<span data-ttu-id="b59f7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b59f7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b59f7-104">用于删除当前记录或一组记录。</span><span class="sxs-lookup"><span data-stu-id="b59f7-104">Deletes the current record or a group of records.</span></span>

## <a name="syntax"></a><span data-ttu-id="b59f7-105">语法</span><span class="sxs-lookup"><span data-stu-id="b59f7-105">Syntax</span></span>

<span data-ttu-id="b59f7-106">*记录集*。删除*AffectRecords*</span><span class="sxs-lookup"><span data-stu-id="b59f7-106">*recordset*.Delete *AffectRecords*</span></span>

## <a name="parameters"></a><span data-ttu-id="b59f7-107">参数</span><span class="sxs-lookup"><span data-stu-id="b59f7-107">Parameters</span></span>

|<span data-ttu-id="b59f7-108">参数</span><span class="sxs-lookup"><span data-stu-id="b59f7-108">Parameter</span></span>|<span data-ttu-id="b59f7-109">说明</span><span class="sxs-lookup"><span data-stu-id="b59f7-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="b59f7-110">*AffectRecords*</span><span class="sxs-lookup"><span data-stu-id="b59f7-110">*AffectRecords*</span></span> |<span data-ttu-id="b59f7-p101">[AffectEnum](affectenum.md) 值，可确定 **Delete** 方法将影响的记录数。默认值为 **adAffectCurrent** 。</span><span class="sxs-lookup"><span data-stu-id="b59f7-p101">An [AffectEnum](affectenum.md) value that determines how many records the **Delete** method will affect. The default value is **adAffectCurrent**.</span></span>|

> [!NOTE]
> <span data-ttu-id="b59f7-113">[!注释] **adAffectAll** 和 **adAffectAllChapters** 不是有效的 **Delete** 参数。</span><span class="sxs-lookup"><span data-stu-id="b59f7-113">**adAffectAll** and **adAffectAllChapters** are not valid arguments to **Delete**.</span></span>

## <a name="remarks"></a><span data-ttu-id="b59f7-114">备注</span><span class="sxs-lookup"><span data-stu-id="b59f7-114">Remarks</span></span>

<span data-ttu-id="b59f7-p102">使用 **Delete** 方法可为 [Recordset](recordset-object-ado.md) 对象中的当前记录或记录组打上删除标记。如果 **Recordset** 对象不允许删除记录，则会发生错误。在即时更新模式下，会立即在数据库中进行删除。如果无法顺利删除记录（例如，由于违反数据库完整性），在调用 **Update** 后，该记录仍保持为编辑模式。这意味着在从当前记录移开（例如，用 [Close](cancelupdate-method-ado.md)、[Move](close-method-ado.md) 或 [NextRecordset](move-method-ado.md)）之前，必须使用 [CancelUpdate](nextrecordset-method-ado.md) 取消更新。</span><span class="sxs-lookup"><span data-stu-id="b59f7-p102">Using the **Delete** method marks the current record or a group of records in a [Recordset](recordset-object-ado.md) object for deletion. If the **Recordset** object doesn't allow record deletion, an error occurs. If you are in immediate update mode, deletions occur in the database immediately. If a record cannot be successfully deleted (due to database integrity violations, for example), the record will remain in edit mode after the call to **Update**. This means that you must cancel the update with [CancelUpdate](cancelupdate-method-ado.md) before moving off the current record (for example, with [Close](close-method-ado.md), [Move](move-method-ado.md), or [NextRecordset](nextrecordset-method-ado.md)).</span></span>

<span data-ttu-id="b59f7-p103">如果处于批更新模式下，则会将记录标记为从缓存中删除，而在调用 [UpdateBatch](updatebatch-method-ado.md) 方法时执行实际的删除操作。（可以使用 [Filter](filter-property-ado.md) 属性查看删除的记录。）</span><span class="sxs-lookup"><span data-stu-id="b59f7-p103">If you are in batch update mode, the records are marked for deletion from the cache and the actual deletion happens when you call the [UpdateBatch](updatebatch-method-ado.md) method. (Use the [Filter](filter-property-ado.md) property to view the deleted records.)</span></span>

<span data-ttu-id="b59f7-p104">检索已删除记录中的字段值时会产生错误。删除当前记录后，在移动到其他记录之前，已删除记录仍然是当前记录。一旦从已删除记录移开，就无法再访问它。</span><span class="sxs-lookup"><span data-stu-id="b59f7-p104">Retrieving field values from the deleted record generates an error. After deleting the current record, the deleted record remains current until you move to a different record. Once you move away from the deleted record, it is no longer accessible.</span></span>

<span data-ttu-id="b59f7-p105">如果在事务中嵌套删除，可以使用 [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法恢复已删除的记录。处于批更新模式时，可以使用 [CancelBatch](cancelbatch-method-ado.md) 方法取消一个或一组挂起的删除操作。</span><span class="sxs-lookup"><span data-stu-id="b59f7-p105">If you nest deletions in a transaction, you can recover deleted records with the [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) method. If you are in batch update mode, you can cancel a pending deletion or group of pending deletions with the [CancelBatch](cancelbatch-method-ado.md) method.</span></span>

<span data-ttu-id="b59f7-p106">如果由于与基础数据冲突而导致删除记录的尝试失败（例如，记录已被另一个用户删除），则提供程序会将警告返回到 [Errors](errors-collection-ado.md) 集合，但是不会停止程序执行。只有当所有被请求的记录都有冲突时，才会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="b59f7-p106">If the attempt to delete records fails because of a conflict with the underlying data (for example, a record has already been deleted by another user), the provider returns warnings to the [Errors](errors-collection-ado.md) collection but does not halt program execution. A run-time error occurs only if there are conflicts on all the requested records.</span></span>

<span data-ttu-id="b59f7-129">如果设置了 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 动态属性，且 **Recordset** 是对多个表执行 JOIN 操作的结果，那么 **Delete** 方法将只从 [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) 属性所指定的表中删除行。</span><span class="sxs-lookup"><span data-stu-id="b59f7-129">If the [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) dynamic property is set, and the **Recordset** is the result of executing a JOIN operation on multiple tables, then the **Delete** method will only delete rows from the table named in the [Unique Table](unique-table-unique-schema-unique-catalog-properties-dynamic-ado.md) property.</span></span>

