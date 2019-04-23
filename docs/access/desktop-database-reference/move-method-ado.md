---
title: Move 方法-ActiveX 数据对象 (ADO)
TOCTitle: Move method (ADO)
ms:assetid: 1f858654-5fa3-273d-7cdc-574c5f09a420
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248982(v=office.15)
ms:contentKeyID: 48543645
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6c7db661e590bc21605d9c289b1de6d4ae9f46e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288832"
---
# <a name="move-method-ado"></a><span data-ttu-id="8bf53-102">Move 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="8bf53-102">Move method (ADO)</span></span>

<span data-ttu-id="8bf53-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="8bf53-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8bf53-104">用于移动 [Recordset](recordset-object-ado.md) 对象中当前记录的位置。</span><span class="sxs-lookup"><span data-stu-id="8bf53-104">Moves the position of the current record in a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="8bf53-105">语法</span><span class="sxs-lookup"><span data-stu-id="8bf53-105">Syntax</span></span>

<span data-ttu-id="8bf53-106">*recordset*。移动*NumRecords*、*开始*</span><span class="sxs-lookup"><span data-stu-id="8bf53-106">*recordset*.Move *NumRecords*, *Start*</span></span>

## <a name="parameters"></a><span data-ttu-id="8bf53-107">参数</span><span class="sxs-lookup"><span data-stu-id="8bf53-107">Parameters</span></span>

|<span data-ttu-id="8bf53-108">参数</span><span class="sxs-lookup"><span data-stu-id="8bf53-108">Parameter</span></span>|<span data-ttu-id="8bf53-109">描述</span><span class="sxs-lookup"><span data-stu-id="8bf53-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="8bf53-110">*NumRecords*</span><span class="sxs-lookup"><span data-stu-id="8bf53-110">*NumRecords*</span></span> |<span data-ttu-id="8bf53-111">有符号的 **长整型** 表达式，指定当前记录位置移动的记录数。</span><span class="sxs-lookup"><span data-stu-id="8bf53-111">A signed **Long** expression that specifies the number of records that the current record position moves.</span></span>|
|<span data-ttu-id="8bf53-112">*Start*</span><span class="sxs-lookup"><span data-stu-id="8bf53-112">*Start*</span></span> |<span data-ttu-id="8bf53-p101">可选。 **字符串型** 值或值为书签的 **变量型** 值。也可以使用 [BookmarkEnum](bookmarkenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="8bf53-p101">Optional. A **String** value or **Variant** that evaluates to a bookmark. You can also use a [BookmarkEnum](bookmarkenum.md) value.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8bf53-116">注解</span><span class="sxs-lookup"><span data-stu-id="8bf53-116">Remarks</span></span>

<span data-ttu-id="8bf53-117">所有的 **Recordset** 对象都支持 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="8bf53-117">The **Move** method is supported on all **Recordset** objects.</span></span>

<span data-ttu-id="8bf53-p102">如果 *NumRecords* 参数大于零，则当前记录的位置会（朝着 **Recordset** 的末尾）向前移动；如果 *NumRecords* 小于零，则当前记录的位置会（朝着 **Recordset** 的开头）向后移动。</span><span class="sxs-lookup"><span data-stu-id="8bf53-p102">If the *NumRecords* argument is greater than zero, the current record position moves forward (toward the end of the **Recordset**). If *NumRecords* is less than zero, the current record position moves backward (toward the beginning of the **Recordset**).</span></span>

<span data-ttu-id="8bf53-120">如果**移动**调用会将当前记录位置移动到第一个记录之前的某个点, 则 ADO 会将当前记录设置为 recordset 中的第一条记录之前的位置 ([BOF](bof-eof-properties-ado.md)为**True**)。</span><span class="sxs-lookup"><span data-stu-id="8bf53-120">If the **Move** call would move the current record position to a point before the first record, ADO sets the current record to the position before the first record in the recordset ([BOF](bof-eof-properties-ado.md) is **True**).</span></span> <span data-ttu-id="8bf53-121">当 **BOF** 属性已经为 **True** 时尝试向后移动将生成错误。</span><span class="sxs-lookup"><span data-stu-id="8bf53-121">An attempt to move backward when the **BOF** property is already **True** generates an error.</span></span>

<span data-ttu-id="8bf53-p104">如果 **Move** 调用会将当前记录的位置移到最后一个记录后面的某个点，则 ADO 会将当前的记录设置为记录集中最后一个记录后面的位置（[EOF](bof-eof-properties-ado.md) 为 **True**）。当 **EOF** 属性已经为 **True** 时尝试向前移动将生成错误。</span><span class="sxs-lookup"><span data-stu-id="8bf53-p104">If the **Move** call would move the current record position to a point after the last record, ADO sets the current record to the position after the last record in the recordset ([EOF](bof-eof-properties-ado.md) is **True**). An attempt to move forward when the **EOF** property is already **True** generates an error.</span></span>

<span data-ttu-id="8bf53-124">从空 **Recordset** 对象调用 **Move** 方法将生成错误。</span><span class="sxs-lookup"><span data-stu-id="8bf53-124">Calling the **Move** method from an empty **Recordset** object generates an error.</span></span>

<span data-ttu-id="8bf53-p105">如果传递 *Start* 参数，则相对于具有该书签的记录进行移动（假设 **Recordset** 对象支持书签）。如果未指定该参数，则将相对于当前的记录进行移动。</span><span class="sxs-lookup"><span data-stu-id="8bf53-p105">If you pass the *Start* argument, the move is relative to the record with this bookmark, assuming the **Recordset** object supports bookmarks. If not specified, the move is relative to the current record.</span></span>

<span data-ttu-id="8bf53-p106">如果要使用 [CacheSize](cachesize-property-ado.md) 属性在本地缓存提供程序的记录，而且所传递 *NumRecords* 参数会将当前记录的位置移到缓存记录的当前组外部，则会强制 ADO 检索一组新记录（从目标记录开始）。**CacheSize** 属性确定新检索组的大小，目标记录是检索到的第一个记录。</span><span class="sxs-lookup"><span data-stu-id="8bf53-p106">If you are using the [CacheSize](cachesize-property-ado.md) property to locally cache records from the provider, passing a *NumRecords* argument that moves the current record position outside the current group of cached records forces ADO to retrieve a new group of records, starting from the destination record. The **CacheSize** property determines the size of the newly retrieved group, and the destination record is the first record retrieved.</span></span>

<span data-ttu-id="8bf53-p107">如果 **Recordset** 对象的方向仅为向前，则用户仍然可以传递小于零的 *NumRecords* 参数，只要目标在当前缓存的记录集中。如果 **Move** 调用会使当前记录位置移动到第一个缓存的记录之前的某个记录，将发生错误。因此，您可以通过支持仅向前滚动的提供程序来使用支持前后滚动的记录缓存。由于缓存的记录被加载到内存中，应该避免缓存超过所需数目的记录。即使仅向前的 **Recordset** 对象支持以这种方式向后移动，对任何仅向前的 **Recordset** 对象调用 [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 方法仍然会生成错误。</span><span class="sxs-lookup"><span data-stu-id="8bf53-p107">If the **Recordset** object is forward only, a user can still pass a *NumRecords* argument less than zero, provided the destination is within the current set of cached records. If the **Move** call would move the current record position to a record before the first cached record, an error will occur. Thus, you can use a record cache that supports full scrolling over a provider that supports only forward scrolling. Because cached records are loaded into memory, you should avoid caching more records than is necessary. Even if a forward-only **Recordset** object supports backward moves in this way, calling the [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) method on any forward-only **Recordset** object will still generate an error.</span></span>


> [!NOTE]
> <span data-ttu-id="8bf53-p108">[!注释] 对在仅向前的 **Recordset** 中向后移动的支持是不可预测的，具体取决于您的提供程序。如果当前记录已定位在 **Recordset** 中最后一个记录之后，则向后 **移动** 不会获得正确的当前位置。</span><span class="sxs-lookup"><span data-stu-id="8bf53-p108">Support for moving backwards in a forward-only **Recordset** is not predictable, depending upon your provider. If the current record has been postioned after the last record in the **Recordset**, **Move** backwards may not result in the correct current position.</span></span>


