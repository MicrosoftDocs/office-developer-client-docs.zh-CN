---
title: GetRows 方法 (ADO)
TOCTitle: GetRows Method (ADO)
ms:assetid: 570e6f1c-c17a-7d9a-c172-387894a3a1f1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249292(v=office.15)
ms:contentKeyID: 48544963
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 99988383c40b84e1993582ad0d1c07491de82933
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879877"
---
# <a name="getrows-method-ado"></a><span data-ttu-id="b8dfa-102">GetRows 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b8dfa-102">GetRows Method (ADO)</span></span>


<span data-ttu-id="b8dfa-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b8dfa-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="b8dfa-104">用于将 [Recordset](recordset-object-ado.md) 对象的多个记录检索到数组中。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-104">Retrieves multiple records of a [Recordset](recordset-object-ado.md) object into an array.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8dfa-105">语法</span><span class="sxs-lookup"><span data-stu-id="b8dfa-105">Syntax</span></span>

<span data-ttu-id="b8dfa-106">*数组* = *recordset*。GetRows （*行*，*启动*，*字段*）</span><span class="sxs-lookup"><span data-stu-id="b8dfa-106">*array* = *recordset*.GetRows(*Rows*, *Start*, *Fields* )</span></span>

## <a name="return-value"></a><span data-ttu-id="b8dfa-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b8dfa-107">Return value</span></span>

<span data-ttu-id="b8dfa-108">返回一个 **变量** ，其值是二维数组。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-108">Returns a **Variant** whose value is a two-dimensional array.</span></span>

## <a name="parameters"></a><span data-ttu-id="b8dfa-109">参数</span><span class="sxs-lookup"><span data-stu-id="b8dfa-109">Parameters</span></span>

  - <span data-ttu-id="b8dfa-110">*Rows*</span><span class="sxs-lookup"><span data-stu-id="b8dfa-110">*Rows*</span></span>

  - <span data-ttu-id="b8dfa-p101">可选。[GetRowsOptionEnum](getrowsoptionenum.md) 值，指示要检索的记录数。默认值为 **adGetRowsRest** 。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-p101">Optional. A [GetRowsOptionEnum](getrowsoptionenum.md) value that indicates the number of records to retrieve. The default is **adGetRowsRest**.</span></span>

  - <span data-ttu-id="b8dfa-114">*Start*</span><span class="sxs-lookup"><span data-stu-id="b8dfa-114">*Start*</span></span>

  - <span data-ttu-id="b8dfa-p102">可选。 **字符串型** 值或 **变量** ，变量计算得出的值为应从该处开始 **GetRows** 操作的记录的书签。也可以使用 [BookmarkEnum](bookmarkenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-p102">Optional. A **String** value or **Variant** that evaluates to the bookmark for the record from which the **GetRows** operation should begin. You can also use a [BookmarkEnum](bookmarkenum.md) value.</span></span>

  - <span data-ttu-id="b8dfa-118">*Fields*</span><span class="sxs-lookup"><span data-stu-id="b8dfa-118">*Fields*</span></span>

  - <span data-ttu-id="b8dfa-p103">可选。 **变量** ，代表单个字段名或序号位置，或一个含一些字段名或序号位置编号的数组。ADO 仅返回这些字段中的数据。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-p103">Optional. A **Variant** that represents a single field name or ordinal position, or an array of field names or ordinal position numbers. ADO returns only the data in these fields.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8dfa-122">备注</span><span class="sxs-lookup"><span data-stu-id="b8dfa-122">Remarks</span></span>

<span data-ttu-id="b8dfa-123">使用 **GetRows** 方法可以将 **Recordset** 中的记录复制到一个二维数组中。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-123">Use the **GetRows** method to copy records from a **Recordset** into a two-dimensional array.</span></span> <span data-ttu-id="b8dfa-124">第一个下标标识字段，第二个下标标识记录号。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-124">The first subscript identifies the field and the second identifies the record number.</span></span> <span data-ttu-id="b8dfa-125">**GetRows**方法返回的数据时，*数组*变量是自动尺寸到正确的大小。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-125">The *array* variable is automatically dimensioned to the correct size when the **GetRows** method returns the data.</span></span>

<span data-ttu-id="b8dfa-126">如果不指定*行*参数的值， **GetRows**方法将自动检索**Recordset**对象中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-126">If you do not specify a value for the *Rows* argument, the **GetRows** method automatically retrieves all the records in the **Recordset** object.</span></span> <span data-ttu-id="b8dfa-127">如果请求的记录数大于可用记录数，则 **GetRows** 仅返回可用数目的记录。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-127">If you request more records than are available, **GetRows** returns only the number of available records.</span></span>

<span data-ttu-id="b8dfa-128">如果**Recordset**对象支持书签，则可以指定在哪些记录， **GetRows**方法应开始通过将该记录的[Bookmark](bookmark-property-ado.md)属性的值传递*Start*参数中检索数据。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-128">If the **Recordset** object supports bookmarks, you can specify at which record the **GetRows** method should begin retrieving data by passing the value of that record's [Bookmark](bookmark-property-ado.md) property in the *Start* argument.</span></span>

<span data-ttu-id="b8dfa-129">如果您想要限制**GetRows**调用返回的字段，则可以在*Fields*参数中传递的单个字段名/编号或字段名/编号的数组。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-129">If you want to restrict the fields that the **GetRows** call returns, you can pass either a single field name/number or an array of field names/numbers in the *Fields* argument.</span></span>

<span data-ttu-id="b8dfa-130">调用 **GetRows** 之后，下一个未读取的记录成为当前记录，如果没有更多记录，则 [EOF](bof-eof-properties-ado.md) 属性设置为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="b8dfa-130">After you call **GetRows**, the next unread record becomes the current record, or the [EOF](bof-eof-properties-ado.md) property is set to **True** if there are no more records.</span></span>

