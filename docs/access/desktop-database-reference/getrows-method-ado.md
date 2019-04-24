---
title: GetRows 方法 (ADO)
TOCTitle: GetRows method (ADO)
ms:assetid: 570e6f1c-c17a-7d9a-c172-387894a3a1f1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249292(v=office.15)
ms:contentKeyID: 48544963
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 61f7ce441eb837b76e824b55393741e0cf821bb5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292221"
---
# <a name="getrows-method-ado"></a><span data-ttu-id="bd53d-102">GetRows 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bd53d-102">GetRows method (ADO)</span></span>

<span data-ttu-id="bd53d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bd53d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bd53d-104">用于将 [Recordset](recordset-object-ado.md) 对象的多个记录检索到数组中。</span><span class="sxs-lookup"><span data-stu-id="bd53d-104">Retrieves multiple records of a [Recordset](recordset-object-ado.md) object into an array.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd53d-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd53d-105">Syntax</span></span>

<span data-ttu-id="bd53d-106">*数组* = *recordset*。GetRows (*行*、*开始*、*字段*)</span><span class="sxs-lookup"><span data-stu-id="bd53d-106">*array* = *recordset*.GetRows(*Rows*, *Start*, *Fields* )</span></span>

## <a name="return-value"></a><span data-ttu-id="bd53d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="bd53d-107">Return value</span></span>

<span data-ttu-id="bd53d-108">返回一个**变量**，其值是二维数组。</span><span class="sxs-lookup"><span data-stu-id="bd53d-108">Returns a **Variant** whose value is a two-dimensional array.</span></span>

## <a name="parameters"></a><span data-ttu-id="bd53d-109">参数</span><span class="sxs-lookup"><span data-stu-id="bd53d-109">Parameters</span></span>

|<span data-ttu-id="bd53d-110">参数</span><span class="sxs-lookup"><span data-stu-id="bd53d-110">Parameter</span></span>|<span data-ttu-id="bd53d-111">描述</span><span class="sxs-lookup"><span data-stu-id="bd53d-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="bd53d-112">*Rows*</span><span class="sxs-lookup"><span data-stu-id="bd53d-112">*Rows*</span></span> |<span data-ttu-id="bd53d-p101">可选。[GetRowsOptionEnum](getrowsoptionenum.md) 值，指示要检索的记录数。默认值为 **adGetRowsRest** 。</span><span class="sxs-lookup"><span data-stu-id="bd53d-p101">Optional. A [GetRowsOptionEnum](getrowsoptionenum.md) value that indicates the number of records to retrieve. The default is **adGetRowsRest**.</span></span>|
|<span data-ttu-id="bd53d-116">*Start*</span><span class="sxs-lookup"><span data-stu-id="bd53d-116">*Start*</span></span> |<span data-ttu-id="bd53d-p102">可选。 **字符串型** 值或 **变量** ，变量计算得出的值为应从该处开始 **GetRows** 操作的记录的书签。也可以使用 [BookmarkEnum](bookmarkenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="bd53d-p102">Optional. A **String** value or **Variant** that evaluates to the bookmark for the record from which the **GetRows** operation should begin. You can also use a [BookmarkEnum](bookmarkenum.md) value.</span></span>|
|<span data-ttu-id="bd53d-120">*Fields*</span><span class="sxs-lookup"><span data-stu-id="bd53d-120">*Fields*</span></span> |<span data-ttu-id="bd53d-p103">可选。 **变量** ，代表单个字段名或序号位置，或一个含一些字段名或序号位置编号的数组。ADO 仅返回这些字段中的数据。</span><span class="sxs-lookup"><span data-stu-id="bd53d-p103">Optional. A **Variant** that represents a single field name or ordinal position, or an array of field names or ordinal position numbers. ADO returns only the data in these fields.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bd53d-124">注解</span><span class="sxs-lookup"><span data-stu-id="bd53d-124">Remarks</span></span>

<span data-ttu-id="bd53d-p104">使用 **GetRows** 方法可以将 **Recordset** 中的记录复制到一个二维数组中。第一个下标标识字段，第二个下标标识记录号。当 **GetRows** 方法返回数据时，*array* 变量的维度将自动设为正确的大小。</span><span class="sxs-lookup"><span data-stu-id="bd53d-p104">Use the **GetRows** method to copy records from a **Recordset** into a two-dimensional array. The first subscript identifies the field and the second identifies the record number. The *array* variable is automatically dimensioned to the correct size when the **GetRows** method returns the data.</span></span>

<span data-ttu-id="bd53d-p105">如果不指定 *Rows* 参数的值，**GetRows** 方法将自动检索 **Recordset** 对象中的所有记录。如果请求的记录数大于可用记录数，则 **GetRows** 仅返回可用数目的记录。</span><span class="sxs-lookup"><span data-stu-id="bd53d-p105">If you do not specify a value for the *Rows* argument, the **GetRows** method automatically retrieves all the records in the **Recordset** object. If you request more records than are available, **GetRows** returns only the number of available records.</span></span>

<span data-ttu-id="bd53d-130">如果 **Recordset** 对象支持书签，则可以指定 **GetRows** 方法应从哪个记录开始检索数据，方法是在 *Start* 参数中传递该记录的 [Bookmark](bookmark-property-ado.md) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="bd53d-130">If the **Recordset** object supports bookmarks, you can specify at which record the **GetRows** method should begin retrieving data by passing the value of that record's [Bookmark](bookmark-property-ado.md) property in the *Start* argument.</span></span>

<span data-ttu-id="bd53d-131">如果要限制 **GetRows** 调用返回的字段数，可以在 *Fields* 参数中传递单个字段名/编号或一个含多个字段名/编号的数组。</span><span class="sxs-lookup"><span data-stu-id="bd53d-131">If you want to restrict the fields that the **GetRows** call returns, you can pass either a single field name/number or an array of field names/numbers in the *Fields* argument.</span></span>

<span data-ttu-id="bd53d-132">调用 **GetRows** 之后，下一个未读取的记录成为当前记录，如果没有更多记录，则 [EOF](bof-eof-properties-ado.md) 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="bd53d-132">After you call **GetRows**, the next unread record becomes the current record, or the [EOF](bof-eof-properties-ado.md) property is set to **True** if there are no more records.</span></span>

