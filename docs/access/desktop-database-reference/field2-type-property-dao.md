---
title: Field2 属性 (DAO)
TOCTitle: Type Property
ms:assetid: 057d6ec9-b72c-cee6-005a-6d916e3dda29
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844921(v=office.15)
ms:contentKeyID: 48543032
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4da32f18a2b3e9dddbb0ae04e3257de34ba09761
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292662"
---
# <a name="field2type-property-dao"></a><span data-ttu-id="b19aa-102">Field2 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="b19aa-102">Field2.Type property (DAO)</span></span>


<span data-ttu-id="b19aa-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b19aa-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b19aa-104">设置或返回一个值，该值指示对象的操作类型或数据类型。</span><span class="sxs-lookup"><span data-stu-id="b19aa-104">Sets or returns a value that indicates the operational type or data type of an object.</span></span> <span data-ttu-id="b19aa-105">可读/写 **Integer** 类型。</span><span class="sxs-lookup"><span data-stu-id="b19aa-105">Read/write **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="b19aa-106">语法</span><span class="sxs-lookup"><span data-stu-id="b19aa-106">Syntax</span></span>

<span data-ttu-id="b19aa-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="b19aa-107">*expression* .Type</span></span>

<span data-ttu-id="b19aa-108">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="b19aa-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="b19aa-109">注解</span><span class="sxs-lookup"><span data-stu-id="b19aa-109">Remarks</span></span>

<span data-ttu-id="b19aa-p102">设置值或返回值是一个指示操作类型或数据类型的常量。对于 **Field2** 对象，该属性是可读写的，直到该对象追加到集合或另一个对象中，该属性才变为只读。</span><span class="sxs-lookup"><span data-stu-id="b19aa-p102">The setting or return value is a constant that indicates an operational or data type. For a **Field2** object, this property is read/write until the object is appended to a collection or to another object, after which it's read-only.</span></span>

<span data-ttu-id="b19aa-112">对于 **Field2** 对象，下表中描述了可能的设置和返回值。</span><span class="sxs-lookup"><span data-stu-id="b19aa-112">For a **Field2** object, the possible settings and return values are described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b19aa-113">常量</span><span class="sxs-lookup"><span data-stu-id="b19aa-113">Constant</span></span></p></th>
<th><p><span data-ttu-id="b19aa-114">说明</span><span class="sxs-lookup"><span data-stu-id="b19aa-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-115"><strong>dbBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-115"><strong>dbBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-116">大整数</span><span class="sxs-lookup"><span data-stu-id="b19aa-116">Big Integer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-117"><strong>dbBinary</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-117"><strong>dbBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-118">Binary</span><span class="sxs-lookup"><span data-stu-id="b19aa-118">Binary</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-119"><strong>dbBoolean</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-119"><strong>dbBoolean</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-120">Boolean</span><span class="sxs-lookup"><span data-stu-id="b19aa-120">Boolean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-121"><strong>dbByte</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-121"><strong>dbByte</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-122">字节</span><span class="sxs-lookup"><span data-stu-id="b19aa-122">Byte</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-123"><strong>dbChar</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-123"><strong>dbChar</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-124">Char</span><span class="sxs-lookup"><span data-stu-id="b19aa-124">Char</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-125"><strong>dbCurrency</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-125"><strong>dbCurrency</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-126">货币</span><span class="sxs-lookup"><span data-stu-id="b19aa-126">Currency</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-127"><strong>dbDate</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-127"><strong>dbDate</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-128">日期/时间</span><span class="sxs-lookup"><span data-stu-id="b19aa-128">Date/Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-129"><strong>dbDecimal</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-129"><strong>dbDecimal</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-130">小数</span><span class="sxs-lookup"><span data-stu-id="b19aa-130">Decimal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-131"><strong>dbDouble</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-131"><strong>dbDouble</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-132">双精度</span><span class="sxs-lookup"><span data-stu-id="b19aa-132">Double</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-133"><strong>dbFloat</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-133"><strong>dbFloat</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-134">点数</span><span class="sxs-lookup"><span data-stu-id="b19aa-134">Float</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-135"><strong>dbGUID</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-135"><strong>dbGUID</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-136">GUID</span><span class="sxs-lookup"><span data-stu-id="b19aa-136">GUID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-137"><strong>dbInteger</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-137"><strong>dbInteger</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-138">整数</span><span class="sxs-lookup"><span data-stu-id="b19aa-138">Integer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-139"><strong>dbLong</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-139"><strong>dbLong</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-140">Long</span><span class="sxs-lookup"><span data-stu-id="b19aa-140">Long</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-141"><strong>dbLongBinary</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-141"><strong>dbLongBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-142">长二进制（OLE 对象）</span><span class="sxs-lookup"><span data-stu-id="b19aa-142">Long Binary (OLE Object)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-143"><strong>dbMemo</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-143"><strong>dbMemo</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-144">备注</span><span class="sxs-lookup"><span data-stu-id="b19aa-144">Memo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-145"><strong>dbNumeric</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-145"><strong>dbNumeric</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-146">Numeric</span><span class="sxs-lookup"><span data-stu-id="b19aa-146">Numeric</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-147"><strong>dbSingle</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-147"><strong>dbSingle</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-148">单倍行距</span><span class="sxs-lookup"><span data-stu-id="b19aa-148">Single</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-149"><strong>dbText</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-149"><strong>dbText</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-150">文本</span><span class="sxs-lookup"><span data-stu-id="b19aa-150">Text</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-151"><strong>dbTime</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-151"><strong>dbTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-152">Time</span><span class="sxs-lookup"><span data-stu-id="b19aa-152">Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b19aa-153"><strong>dbTimeStamp</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-153"><strong>dbTimeStamp</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-154">时间戳</span><span class="sxs-lookup"><span data-stu-id="b19aa-154">Time Stamp</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b19aa-155"><strong>dbVarBinary</strong></span><span class="sxs-lookup"><span data-stu-id="b19aa-155"><strong>dbVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="b19aa-156">VarBinary</span><span class="sxs-lookup"><span data-stu-id="b19aa-156">VarBinary</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b19aa-157">将新的 **Field2**、 **Parameter** 或 **Property** 对象追加到 **Index**、 **QueryDef**、 **Recordset** 或 **TableDef** 对象集合中时，如果基础数据库不支持为新对象指定的数据类型，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="b19aa-157">When you append a new **Field2**, **Parameter**, or **Property** object to the collection of an **Index**, **QueryDef**, **Recordset**, or **TableDef** object, an error occurs if the underlying database doesn't support the data type specified for the new object.</span></span>

