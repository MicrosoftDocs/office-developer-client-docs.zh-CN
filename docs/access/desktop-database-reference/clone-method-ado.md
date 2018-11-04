---
title: Clone 方法-ActiveX 数据对象 (ADO)
TOCTitle: Clone method (ADO)
ms:assetid: ca9b2b76-90bf-9a60-2611-3cb4977d5591
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249984(v=office.15)
ms:contentKeyID: 48547693
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c72902c4ed1d1d2657bfa6e2b4c5f84d76dfefa3
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25950256"
---
# <a name="clone-method-ado"></a><span data-ttu-id="3707c-102">Clone 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="3707c-102">Clone method (ADO)</span></span>

<span data-ttu-id="3707c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3707c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3707c-p101">用于从现有 [Recordset](recordset-object-ado.md) 对象创建重复的 **Recordset** 对象。还可以指定克隆为只读状态。</span><span class="sxs-lookup"><span data-stu-id="3707c-p101">Creates a duplicate [Recordset](recordset-object-ado.md) object from an existing **Recordset** object. Optionally, specifies that the clone be read-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="3707c-106">语法</span><span class="sxs-lookup"><span data-stu-id="3707c-106">Syntax</span></span>

<span data-ttu-id="3707c-107">**设置\*\*\*rstDuplicate* =  *rstOriginal*。克隆 (*LockType\*)</span><span class="sxs-lookup"><span data-stu-id="3707c-107">**Set** *rstDuplicate* = *rstOriginal*.Clone (*LockType*)</span></span>

## <a name="return-value"></a><span data-ttu-id="3707c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3707c-108">Return value</span></span>

<span data-ttu-id="3707c-109">返回 **Recordset** 对象引用。</span><span class="sxs-lookup"><span data-stu-id="3707c-109">Returns a **Recordset** object reference.</span></span>

## <a name="parameters"></a><span data-ttu-id="3707c-110">参数</span><span class="sxs-lookup"><span data-stu-id="3707c-110">Parameters</span></span>

|<span data-ttu-id="3707c-111">参数</span><span class="sxs-lookup"><span data-stu-id="3707c-111">Parameter</span></span>|<span data-ttu-id="3707c-112">说明</span><span class="sxs-lookup"><span data-stu-id="3707c-112">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="3707c-113">*rstDuplicate*</span><span class="sxs-lookup"><span data-stu-id="3707c-113">*rstDuplicate*</span></span> |<span data-ttu-id="3707c-114">一个标识要创建的重复 **Recordset** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="3707c-114">An object variable that identifies the duplicate **Recordset** object to be created.</span></span>|
|<span data-ttu-id="3707c-115">*rstOriginal*</span><span class="sxs-lookup"><span data-stu-id="3707c-115">*rstOriginal*</span></span> |<span data-ttu-id="3707c-116">对象变量，用于标识要重复的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="3707c-116">An object variable that identifies the **Recordset** object to be duplicated.</span></span>|
|<span data-ttu-id="3707c-117">*LockType*</span><span class="sxs-lookup"><span data-stu-id="3707c-117">*LockType*</span></span> |<span data-ttu-id="3707c-p102">可选。[LockTypeEnum](locktypeenum.md) 值，用于指定原始 **Recordset** 或只读 **Recordset** 的锁类型。有效值为 **adLockUnspecified** 或 **adLockReadOnly** 。</span><span class="sxs-lookup"><span data-stu-id="3707c-p102">Optional. A [LockTypeEnum](locktypeenum.md) value that specifies either the lock type of the original **Recordset**, or a read-only **Recordset**. Valid values are **adLockUnspecified** or **adLockReadOnly**.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3707c-121">说明</span><span class="sxs-lookup"><span data-stu-id="3707c-121">Remarks</span></span>

<span data-ttu-id="3707c-p103">可以使用 **Clone** 方法创建多个重复的 **Recordset** 对象，尤其是要在给定记录集中保留多个当前记录时。使用 **Clone** 方法比采用与原始对象相同的定义创建和打开一个新的 **Recordset** 对象效率更高。</span><span class="sxs-lookup"><span data-stu-id="3707c-p103">Use the **Clone** method to create multiple, duplicate **Recordset** objects, particularly if you want to maintain more than one current record in a given set of records. Using the **Clone** method is more efficient than creating and opening a new **Recordset** object with the same definition as the original.</span></span>

<span data-ttu-id="3707c-p104">原始 [Recordset](filter-property-ado.md) 的 **Filter** 属性（如果有）不适用于克隆。可以为新的 **Recordset** 设置 **Filter** 属性，以筛选结果。要复制任何现有的 **Filter** 值，最简单的方法是直接为其赋值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3707c-p104">The [Filter](filter-property-ado.md) property of the original **Recordset**, if any, will not be applied to the clone. Set the **Filter** property of the new **Recordset** in order to filter the results. The simplest way to copy any existing **Filter** value is to assign it directly, like this:</span></span>

<span data-ttu-id="3707c-127">新创建克隆的当前记录设置为第一条记录。</span><span class="sxs-lookup"><span data-stu-id="3707c-127">The current record of a newly created clone is set to the first record.</span></span>

<span data-ttu-id="3707c-p105">无论游标类型是什么，对一个 **Recordset** 对象所做的更改可以在该对象的所有副本中体现出来。但是，对原始 [Recordset](requery-method-ado.md) 对象执行 **Requery** 后，副本将不再与原始对象同步。</span><span class="sxs-lookup"><span data-stu-id="3707c-p105">Changes you make to one **Recordset** object are visible in all of its clones regardless of cursor type. However, after you execute [Requery](requery-method-ado.md) on the original **Recordset**, the clones will no longer be synchronized to the original.</span></span>

<span data-ttu-id="3707c-130">关闭原始 **Recordset** 不会关闭其副本，同样，关闭副本也不会关闭原始对象或其他任何副本。</span><span class="sxs-lookup"><span data-stu-id="3707c-130">Closing the original **Recordset** does not close its copies, nor does closing a copy close the original or any of the other copies.</span></span>

<span data-ttu-id="3707c-p106">只能克隆支持书签的 **Recordset** 对象。书签值是可以互换的；即，一个 **Recordset** 对象中的书签引用可以引用其任何副本中的同一个记录。</span><span class="sxs-lookup"><span data-stu-id="3707c-p106">You can only clone a **Recordset** object that supports bookmarks. Bookmark values are interchangeable; that is, a bookmark reference from one **Recordset** object refers to the same record in any of its clones.</span></span>

<span data-ttu-id="3707c-p107">触发的某些 **Recordset** 事件也将在所有 **Recordset** 克隆中激发。不过，由于克隆的 **Recordset** 之间的当前记录不同，对于某些克隆而言事件可能无效。</span><span class="sxs-lookup"><span data-stu-id="3707c-p107">Some **Recordset** events that are triggered will also fire in all **Recordset** clones. However, because the current record can differ between cloned **Recordsets**, the events may not be valid for the clone.</span></span>

<span data-ttu-id="3707c-135">例如，如果更改字段值，则在更改的 [Recordset](willchangefield-and-fieldchangecomplete-events-ado.md) 和所有克隆中都将发生 **WillChangeField** 事件。</span><span class="sxs-lookup"><span data-stu-id="3707c-135">For example, if you change a value of a field, a [WillChangeField](willchangefield-and-fieldchangecomplete-events-ado.md) event will occur in the changed **Recordset** and in all clones.</span></span> <span data-ttu-id="3707c-136">（其中不进行更改） 克隆**Recordset**的**WillChangeField**事件的*字段*参数将只需引用克隆，这可能比当前另一条记录成为当前记录的字段的记录原始**Recordset**发生更改。</span><span class="sxs-lookup"><span data-stu-id="3707c-136">The *Fields* parameter of the **WillChangeField** event of a cloned **Recordset** (where the change was not made) will simply refer to the fields of the current record of the clone, which may be a different record than the current record of the original **Recordset** where the change occurred.</span></span>

<span data-ttu-id="3707c-137">下表提供了所有 **Recordset** 事件的完整列表，并指示这些事件是否有效和对于用 **Clone** 方法生成的任何记录集克隆是否会触发这些事件。</span><span class="sxs-lookup"><span data-stu-id="3707c-137">The following table provided a full listing of all **Recordset** events and indicates whether they are valid and triggered for any recordset clones generated using the **Clone** method.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3707c-138">事件</span><span class="sxs-lookup"><span data-stu-id="3707c-138">Event</span></span></p></th>
<th><p><span data-ttu-id="3707c-139">是否在克隆中触发？</span><span class="sxs-lookup"><span data-stu-id="3707c-139">Triggered in clones?</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3707c-140"><a href="endofrecordset-event-ado.md">EndOfRecordset</a></span><span class="sxs-lookup"><span data-stu-id="3707c-140"><a href="endofrecordset-event-ado.md">EndOfRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-141">否</span><span class="sxs-lookup"><span data-stu-id="3707c-141">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3707c-142"><a href="fetchcomplete-event-ado.md">FetchComplete</a></span><span class="sxs-lookup"><span data-stu-id="3707c-142"><a href="fetchcomplete-event-ado.md">FetchComplete</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-143">否</span><span class="sxs-lookup"><span data-stu-id="3707c-143">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3707c-144"><a href="fetchprogress-event-ado.md">FetchProgress</a></span><span class="sxs-lookup"><span data-stu-id="3707c-144"><a href="fetchprogress-event-ado.md">FetchProgress</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-145">否</span><span class="sxs-lookup"><span data-stu-id="3707c-145">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3707c-146"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">FieldChangeComplete</a></span><span class="sxs-lookup"><span data-stu-id="3707c-146"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">FieldChangeComplete</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-147">是</span><span class="sxs-lookup"><span data-stu-id="3707c-147">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3707c-148"><a href="willmove-and-movecomplete-events-ado.md">MoveComplete</a></span><span class="sxs-lookup"><span data-stu-id="3707c-148"><a href="willmove-and-movecomplete-events-ado.md">MoveComplete</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-149">否</span><span class="sxs-lookup"><span data-stu-id="3707c-149">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3707c-150"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">RecordChangeComplete</a></span><span class="sxs-lookup"><span data-stu-id="3707c-150"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">RecordChangeComplete</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-151">是</span><span class="sxs-lookup"><span data-stu-id="3707c-151">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3707c-152"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">RecordsetChangeComplete</a></span><span class="sxs-lookup"><span data-stu-id="3707c-152"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">RecordsetChangeComplete</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-153">否</span><span class="sxs-lookup"><span data-stu-id="3707c-153">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3707c-154"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">WillChangeField</a></span><span class="sxs-lookup"><span data-stu-id="3707c-154"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">WillChangeField</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-155">是</span><span class="sxs-lookup"><span data-stu-id="3707c-155">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3707c-156"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">WillChangeRecord</a></span><span class="sxs-lookup"><span data-stu-id="3707c-156"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">WillChangeRecord</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-157">是</span><span class="sxs-lookup"><span data-stu-id="3707c-157">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3707c-158"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">在 WillChangeRecordset</a></span><span class="sxs-lookup"><span data-stu-id="3707c-158"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">WillChangeRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-159">否</span><span class="sxs-lookup"><span data-stu-id="3707c-159">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3707c-160"><a href="willmove-and-movecomplete-events-ado.md">WillMove</a></span><span class="sxs-lookup"><span data-stu-id="3707c-160"><a href="willmove-and-movecomplete-events-ado.md">WillMove</a></span></span></p></td>
<td><p><span data-ttu-id="3707c-161">否</span><span class="sxs-lookup"><span data-stu-id="3707c-161">No</span></span></p></td>
</tr>
</tbody>
</table>

