---
title: Field2.Type Property (DAO)
TOCTitle: Type Property
ms:assetid: 057d6ec9-b72c-cee6-005a-6d916e3dda29
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844921(v=office.15)
ms:contentKeyID: 48543032
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9fee97fe9df4665ce726de7c63984d8f34d70aa3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466388"
---
# <a name="field2type-property-dao"></a><span data-ttu-id="aeaec-102">Field2.Type Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="aeaec-102">Field2.Type Property (DAO)</span></span>


<span data-ttu-id="aeaec-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="aeaec-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="aeaec-p101">设置或返回一个值，该值指示对象的操作类型或数据类型。可读写 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="aeaec-p101">Sets or returns a value that indicates the operational type or data type of an object. Read/write **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="aeaec-106">语法</span><span class="sxs-lookup"><span data-stu-id="aeaec-106">Syntax</span></span>

<span data-ttu-id="aeaec-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="aeaec-107">*expression* .Type</span></span>

<span data-ttu-id="aeaec-108">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="aeaec-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="aeaec-109">注解</span><span class="sxs-lookup"><span data-stu-id="aeaec-109">Remarks</span></span>

<span data-ttu-id="aeaec-p102">设置值或返回值是一个指示操作类型或数据类型的常量。对于 **Field2** 对象，该属性是可读写的，直到该对象追加到集合或另一个对象中，该属性才变为只读。</span><span class="sxs-lookup"><span data-stu-id="aeaec-p102">The setting or return value is a constant that indicates an operational or data type. For a **Field2** object, this property is read/write until the object is appended to a collection or to another object, after which it's read-only.</span></span>

<span data-ttu-id="aeaec-112">对于 **Field2** 对象，下表中描述了可能的设置和返回值。</span><span class="sxs-lookup"><span data-stu-id="aeaec-112">For a **Field2** object, the possible settings and return values are described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="aeaec-113">常量</span><span class="sxs-lookup"><span data-stu-id="aeaec-113">Constant</span></span></p></th>
<th><p><span data-ttu-id="aeaec-114">说明</span><span class="sxs-lookup"><span data-stu-id="aeaec-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-115"><strong>dbBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-115"><strong>dbBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-116">大整数</span><span class="sxs-lookup"><span data-stu-id="aeaec-116">Big Integer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-117"><strong>dbBinary</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-117"><strong>dbBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-118">二进制数</span><span class="sxs-lookup"><span data-stu-id="aeaec-118">Binary</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-119"><strong>dbBoolean</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-119"><strong>dbBoolean</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-120">Boolean</span><span class="sxs-lookup"><span data-stu-id="aeaec-120">Boolean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-121"><strong>dbByte</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-121"><strong>dbByte</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-122">字节</span><span class="sxs-lookup"><span data-stu-id="aeaec-122">Byte</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-123"><strong>dbChar</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-123"><strong>dbChar</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-124">字符</span><span class="sxs-lookup"><span data-stu-id="aeaec-124">Char</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-125"><strong>dbCurrency</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-125"><strong>dbCurrency</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-126">货币</span><span class="sxs-lookup"><span data-stu-id="aeaec-126">Currency</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-127"><strong>dbDate</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-127"><strong>dbDate</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-128">日期/时间</span><span class="sxs-lookup"><span data-stu-id="aeaec-128">Date/Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-129"><strong>dbDecimal</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-129"><strong>dbDecimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-130">小数</span><span class="sxs-lookup"><span data-stu-id="aeaec-130">Decimal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-131"><strong>dbDouble</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-131"><strong>dbDouble</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-132">双精度数</span><span class="sxs-lookup"><span data-stu-id="aeaec-132">Double</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-133"><strong>dbFloat</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-133"><strong>dbFloat</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-134">Float</span><span class="sxs-lookup"><span data-stu-id="aeaec-134">Float</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-135"><strong>dbGUID</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-135"><strong>dbGUID</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-136">GUID</span><span class="sxs-lookup"><span data-stu-id="aeaec-136">GUID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-137"><strong>dbInteger</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-137"><strong>dbInteger</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-138">整数</span><span class="sxs-lookup"><span data-stu-id="aeaec-138">Integer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-139"><strong>dbLong</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-139"><strong>dbLong</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-140">Long</span><span class="sxs-lookup"><span data-stu-id="aeaec-140">Long</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-141"><strong>dbLongBinary</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-141"><strong>dbLongBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-142">长二进制（OLE 对象）</span><span class="sxs-lookup"><span data-stu-id="aeaec-142">Long Binary (OLE Object)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-143"><strong>dbMemo</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-143"><strong>dbMemo</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-144">Memo</span><span class="sxs-lookup"><span data-stu-id="aeaec-144">Memo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-145"><strong>dbNumeric</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-145"><strong>dbNumeric</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-146">Numeric</span><span class="sxs-lookup"><span data-stu-id="aeaec-146">Numeric</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-147"><strong>dbSingle</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-147"><strong>dbSingle</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-148">Single</span><span class="sxs-lookup"><span data-stu-id="aeaec-148">Single</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-149"><strong>dbText</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-149"><strong>dbText</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-150">文本</span><span class="sxs-lookup"><span data-stu-id="aeaec-150">Text</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-151"><strong>dbTime</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-151"><strong>dbTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-152">Time</span><span class="sxs-lookup"><span data-stu-id="aeaec-152">Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aeaec-153"><strong>dbTimeStamp</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-153"><strong>dbTimeStamp</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-154">时间戳</span><span class="sxs-lookup"><span data-stu-id="aeaec-154">Time Stamp</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aeaec-155"><strong>dbVarBinary</strong></span><span class="sxs-lookup"><span data-stu-id="aeaec-155"><strong>dbVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="aeaec-156">VarBinary</span><span class="sxs-lookup"><span data-stu-id="aeaec-156">VarBinary</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aeaec-157">将新的 **Field2**、 **Parameter** 或 **Property** 对象追加到 **Index**、 **QueryDef**、 **Recordset** 或 **TableDef** 对象集合中时，如果基础数据库不支持为新对象指定的数据类型，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="aeaec-157">When you append a new **Field2**, **Parameter**, or **Property** object to the collection of an **Index**, **QueryDef**, **Recordset**, or **TableDef** object, an error occurs if the underlying database doesn't support the data type specified for the new object.</span></span>

