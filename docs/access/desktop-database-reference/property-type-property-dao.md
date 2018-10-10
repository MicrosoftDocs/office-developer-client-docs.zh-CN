---
title: Property.Type Property (DAO)
TOCTitle: Type Property
ms:assetid: bf8258ca-08b5-c4f9-e6d7-114e4300b2ef
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822796(v=office.15)
ms:contentKeyID: 48547490
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c52f03d0e2fc541cb15397d0c924859cd31ccb17
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25469025"
---
# <a name="propertytype-property-dao"></a><span data-ttu-id="d53a1-102">Property.Type Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="d53a1-102">Property.Type Property (DAO)</span></span>


<span data-ttu-id="d53a1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d53a1-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d53a1-p101">设置或返回一个值，该值指示对象的操作类型或数据类型。可读写 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="d53a1-p101">Sets or returns a value that indicates the operational type or data type of an object. Read/write **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="d53a1-106">语法</span><span class="sxs-lookup"><span data-stu-id="d53a1-106">Syntax</span></span>

<span data-ttu-id="d53a1-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="d53a1-107">*expression* .Type</span></span>

<span data-ttu-id="d53a1-108">*表达式*一个代表**Property**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="d53a1-108">*expression* A variable that represents a **Property** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="d53a1-109">注解</span><span class="sxs-lookup"><span data-stu-id="d53a1-109">Remarks</span></span>

<span data-ttu-id="d53a1-p102">设置或返回值是一个指示操作类型或数据类型的常量。对于 **[Property](property-object-dao.md)** 对象，该属性是可读写的，直到该对象追加到集合或另一个对象中，该属性才变为只读。</span><span class="sxs-lookup"><span data-stu-id="d53a1-p102">The setting or return value is a constant that indicates an operational or data type. For a **[Property](property-object-dao.md)** object, this property is read/write until the object is appended to a collection or to another object, after which it's read-only.</span></span>

<span data-ttu-id="d53a1-112">对于 **Property** 对象，下表中描述了可能的设置和返回值。</span><span class="sxs-lookup"><span data-stu-id="d53a1-112">For a **Property** object, the possible settings and return values are described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d53a1-113">常量</span><span class="sxs-lookup"><span data-stu-id="d53a1-113">Constant</span></span></p></th>
<th><p><span data-ttu-id="d53a1-114">说明</span><span class="sxs-lookup"><span data-stu-id="d53a1-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-115"><strong>dbBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-115"><strong>dbBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-116">大整数</span><span class="sxs-lookup"><span data-stu-id="d53a1-116">Big Integer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-117"><strong>dbBinary</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-117"><strong>dbBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-118">二进制数</span><span class="sxs-lookup"><span data-stu-id="d53a1-118">Binary</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-119"><strong>dbBoolean</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-119"><strong>dbBoolean</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-120">Boolean</span><span class="sxs-lookup"><span data-stu-id="d53a1-120">Boolean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-121"><strong>dbByte</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-121"><strong>dbByte</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-122">字节</span><span class="sxs-lookup"><span data-stu-id="d53a1-122">Byte</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-123"><strong>dbChar</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-123"><strong>dbChar</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-124">字符</span><span class="sxs-lookup"><span data-stu-id="d53a1-124">Char</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-125"><strong>dbCurrency</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-125"><strong>dbCurrency</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-126">货币</span><span class="sxs-lookup"><span data-stu-id="d53a1-126">Currency</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-127"><strong>dbDate</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-127"><strong>dbDate</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-128">日期/时间</span><span class="sxs-lookup"><span data-stu-id="d53a1-128">Date/Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-129"><strong>dbDecimal</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-129"><strong>dbDecimal</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-130">小数</span><span class="sxs-lookup"><span data-stu-id="d53a1-130">Decimal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-131"><strong>dbDouble</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-131"><strong>dbDouble</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-132">双精度数</span><span class="sxs-lookup"><span data-stu-id="d53a1-132">Double</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-133"><strong>dbFloat</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-133"><strong>dbFloat</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-134">Float</span><span class="sxs-lookup"><span data-stu-id="d53a1-134">Float</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-135"><strong>dbGUID</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-135"><strong>dbGUID</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-136">GUID</span><span class="sxs-lookup"><span data-stu-id="d53a1-136">GUID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-137"><strong>dbInteger</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-137"><strong>dbInteger</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-138">整数</span><span class="sxs-lookup"><span data-stu-id="d53a1-138">Integer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-139"><strong>dbLong</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-139"><strong>dbLong</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-140">Long</span><span class="sxs-lookup"><span data-stu-id="d53a1-140">Long</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-141"><strong>dbLongBinary</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-141"><strong>dbLongBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-142">长二进制（OLE 对象）</span><span class="sxs-lookup"><span data-stu-id="d53a1-142">Long Binary (OLE Object)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-143"><strong>dbMemo</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-143"><strong>dbMemo</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-144">Memo</span><span class="sxs-lookup"><span data-stu-id="d53a1-144">Memo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-145"><strong>dbNumeric</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-145"><strong>dbNumeric</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-146">Numeric</span><span class="sxs-lookup"><span data-stu-id="d53a1-146">Numeric</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-147"><strong>dbSingle</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-147"><strong>dbSingle</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-148">Single</span><span class="sxs-lookup"><span data-stu-id="d53a1-148">Single</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-149"><strong>dbText</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-149"><strong>dbText</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-150">文本</span><span class="sxs-lookup"><span data-stu-id="d53a1-150">Text</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-151"><strong>dbTime</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-151"><strong>dbTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-152">Time</span><span class="sxs-lookup"><span data-stu-id="d53a1-152">Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d53a1-153"><strong>dbTimeStamp</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-153"><strong>dbTimeStamp</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-154">时间戳</span><span class="sxs-lookup"><span data-stu-id="d53a1-154">Time Stamp</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d53a1-155"><strong>dbVarBinary</strong></span><span class="sxs-lookup"><span data-stu-id="d53a1-155"><strong>dbVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="d53a1-156">VarBinary</span><span class="sxs-lookup"><span data-stu-id="d53a1-156">VarBinary</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d53a1-157">将新的 **Field**、 **Parameter** 或 **Property** 对象追加到 **[Index](index-object-dao.md)** 、 **QueryDef**、 **Recordset** 或 **TableDef** 对象集合中时，如果基础数据库不支持为新对象指定的数据类型，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="d53a1-157">When you append a new **Field**, **Parameter**, or **Property** object to the collection of an **[Index](index-object-dao.md)**, **QueryDef**, **Recordset**, or **TableDef** object, an error occurs if the underlying database doesn't support the data type specified for the new object.</span></span>

