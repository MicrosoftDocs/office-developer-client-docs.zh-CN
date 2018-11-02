---
title: Move 方法-ActiveX 数据对象 (ADO)
TOCTitle: Move method (ADO)
ms:assetid: 1f858654-5fa3-273d-7cdc-574c5f09a420
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248982(v=office.15)
ms:contentKeyID: 48543645
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 55439f14cd2a498ec2592c533dd308f82798b1e8
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929445"
---
# <a name="move-method-ado"></a><span data-ttu-id="55fa5-102">Move 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="55fa5-102">Move method (ADO)</span></span>


<span data-ttu-id="55fa5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="55fa5-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="55fa5-104">用于移动 [Recordset](recordset-object-ado.md) 对象中当前记录的位置。</span><span class="sxs-lookup"><span data-stu-id="55fa5-104">Moves the position of the current record in a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="55fa5-105">语法</span><span class="sxs-lookup"><span data-stu-id="55fa5-105">Syntax</span></span>

<span data-ttu-id="55fa5-106">*记录集*。移动*NumRecords*，*启动*</span><span class="sxs-lookup"><span data-stu-id="55fa5-106">*recordset*.Move *NumRecords*, *Start*</span></span>

## <a name="parameters"></a><span data-ttu-id="55fa5-107">参数</span><span class="sxs-lookup"><span data-stu-id="55fa5-107">Parameters</span></span>

  - <span data-ttu-id="55fa5-108">*NumRecords*</span><span class="sxs-lookup"><span data-stu-id="55fa5-108">*NumRecords*</span></span>

  - <span data-ttu-id="55fa5-109">有符号的 **长整型** 表达式，指定当前记录位置移动的记录数。</span><span class="sxs-lookup"><span data-stu-id="55fa5-109">A signed **Long** expression that specifies the number of records that the current record position moves.</span></span>

  - <span data-ttu-id="55fa5-110">*Start*</span><span class="sxs-lookup"><span data-stu-id="55fa5-110">*Start*</span></span>

  - <span data-ttu-id="55fa5-p101">可选。 **字符串型** 值或值为书签的 **变量型** 值。也可以使用 [BookmarkEnum](bookmarkenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="55fa5-p101">Optional. A **String** value or **Variant** that evaluates to a bookmark. You can also use a [BookmarkEnum](bookmarkenum.md) value.</span></span>

## <a name="remarks"></a><span data-ttu-id="55fa5-114">备注</span><span class="sxs-lookup"><span data-stu-id="55fa5-114">Remarks</span></span>

<span data-ttu-id="55fa5-115">所有的 **Recordset** 对象都支持 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="55fa5-115">The **Move** method is supported on all **Recordset** objects.</span></span>

<span data-ttu-id="55fa5-p102">如果 *NumRecords* 参数大于零，则当前记录的位置会（朝着 **Recordset** 的末尾）向前移动；如果 *NumRecords* 小于零，则当前记录的位置会（朝着 **Recordset** 的开头）向后移动。</span><span class="sxs-lookup"><span data-stu-id="55fa5-p102">If the *NumRecords* argument is greater than zero, the current record position moves forward (toward the end of the **Recordset**). If *NumRecords* is less than zero, the current record position moves backward (toward the beginning of the **Recordset**).</span></span>

<span data-ttu-id="55fa5-118">如果**Move**调用会将当前记录位置移动到第一个记录之前的点，ADO 会将当前记录设置为第一个记录之前记录集中的位置 （[BOF](bof-eof-properties-ado.md)为**True**）。</span><span class="sxs-lookup"><span data-stu-id="55fa5-118">If the **Move** call would move the current record position to a point before the first record, ADO sets the current record to the position before the first record in the recordset ([BOF](bof-eof-properties-ado.md) is **True**).</span></span> <span data-ttu-id="55fa5-119">当 **BOF** 属性已经为 **True** 时，尝试向后移动将生成错误。</span><span class="sxs-lookup"><span data-stu-id="55fa5-119">An attempt to move backward when the **BOF** property is already **True** generates an error.</span></span>

<span data-ttu-id="55fa5-120">如果**Move**调用会后的最后一个记录移动了到某个点的当前记录位置，ADO 将当前记录位置设置 （[EOF](bof-eof-properties-ado.md)为**True**） 将 recordset 中的最后一个记录之后。</span><span class="sxs-lookup"><span data-stu-id="55fa5-120">If the **Move** call would move the current record position to a point after the last record, ADO sets the current record to the position after the last record in the recordset ([EOF](bof-eof-properties-ado.md) is **True**).</span></span> <span data-ttu-id="55fa5-121">当 **EOF** 属性已经为 **True** 时尝试向前移动将生成错误。</span><span class="sxs-lookup"><span data-stu-id="55fa5-121">An attempt to move forward when the **EOF** property is already **True** generates an error.</span></span>

<span data-ttu-id="55fa5-122">从空 **Recordset** 对象调用 **Move** 方法将生成错误。</span><span class="sxs-lookup"><span data-stu-id="55fa5-122">Calling the **Move** method from an empty **Recordset** object generates an error.</span></span>

<span data-ttu-id="55fa5-123">如果*Start*参数传递，移动是相对于包含该书签，假定**Recordset**对象支持书签记录。</span><span class="sxs-lookup"><span data-stu-id="55fa5-123">If you pass the *Start* argument, the move is relative to the record with this bookmark, assuming the **Recordset** object supports bookmarks.</span></span> <span data-ttu-id="55fa5-124">如果未指定该参数，则将相对于当前的记录进行移动。</span><span class="sxs-lookup"><span data-stu-id="55fa5-124">If not specified, the move is relative to the current record.</span></span>

<span data-ttu-id="55fa5-125">如果您正在从提供程序，将移动外部的缓存记录当前的组的当前记录位置*NumRecords*参数传递到本地缓存记录使用[CacheSize](cachesize-property-ado.md)属性强制 ADO 检索一组新记录，从目标记录开始。</span><span class="sxs-lookup"><span data-stu-id="55fa5-125">If you are using the [CacheSize](cachesize-property-ado.md) property to locally cache records from the provider, passing a *NumRecords* argument that moves the current record position outside the current group of cached records forces ADO to retrieve a new group of records, starting from the destination record.</span></span> <span data-ttu-id="55fa5-126">**CacheSize** 属性确定新检索组的大小，目标记录是检索到的第一个记录。</span><span class="sxs-lookup"><span data-stu-id="55fa5-126">The **CacheSize** property determines the size of the newly retrieved group, and the destination record is the first record retrieved.</span></span>

<span data-ttu-id="55fa5-127">如果**Recordset**对象仅转接，则用户提供当前的缓存记录集内的目标是仍可以传递*NumRecords*参数小于零。</span><span class="sxs-lookup"><span data-stu-id="55fa5-127">If the **Recordset** object is forward only, a user can still pass a *NumRecords* argument less than zero, provided the destination is within the current set of cached records.</span></span> <span data-ttu-id="55fa5-128">如果 **Move** 调用会使当前记录位置移动到第一个缓存的记录之前的某个记录，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="55fa5-128">If the **Move** call would move the current record position to a record before the first cached record, an error will occur.</span></span> <span data-ttu-id="55fa5-129">因此，您可以通过支持仅向前滚动的提供程序来使用支持前后滚动的记录缓存。</span><span class="sxs-lookup"><span data-stu-id="55fa5-129">Thus, you can use a record cache that supports full scrolling over a provider that supports only forward scrolling.</span></span> <span data-ttu-id="55fa5-130">由于缓存的记录被加载到内存中，应该避免缓存超过所需数目的记录。</span><span class="sxs-lookup"><span data-stu-id="55fa5-130">Because cached records are loaded into memory, you should avoid caching more records than is necessary.</span></span> <span data-ttu-id="55fa5-131">即使仅向前的 **Recordset** 对象支持以这种方式向后移动，对任何仅向前的 [Recordset](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 对象调用 **MovePrevious** 方法仍然会生成错误。</span><span class="sxs-lookup"><span data-stu-id="55fa5-131">Even if a forward-only **Recordset** object supports backward moves in this way, calling the [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) method on any forward-only **Recordset** object will still generate an error.</span></span>


> [!NOTE]
> <span data-ttu-id="55fa5-p108">[!注释] 对在仅向前的 **Recordset** 中向后移动的支持是不可预测的，具体取决于您的提供程序。如果当前记录已定位在 **Recordset** 中最后一个记录之后，则向后 **移动** 不会获得正确的当前位置。</span><span class="sxs-lookup"><span data-stu-id="55fa5-p108">Support for moving backwards in a forward-only **Recordset** is not predictable, depending upon your provider. If the current record has been postioned after the last record in the **Recordset**, **Move** backwards may not result in the correct current position.</span></span>


