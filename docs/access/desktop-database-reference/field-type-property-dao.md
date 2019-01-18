---
title: Field.Type 属性 (DAO)
TOCTitle: Type Property
ms:assetid: 1295ca40-78c1-bdd0-d407-e1b5be8adfd4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845405(v=office.15)
ms:contentKeyID: 48543345
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: c8f212c5e1f10f4270987c9453802575d88cebfa
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709479"
---
# <a name="fieldtype-property-dao"></a><span data-ttu-id="08cac-102">Field.Type 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="08cac-102">Field.Type property (DAO)</span></span>


<span data-ttu-id="08cac-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="08cac-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="08cac-p101">设置或返回一个值，该值指示对象的操作类型或数据类型。可读写 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="08cac-p101">Sets or returns a value that indicates the operational type or data type of an object. Read/write **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="08cac-106">语法</span><span class="sxs-lookup"><span data-stu-id="08cac-106">Syntax</span></span>

<span data-ttu-id="08cac-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="08cac-107">*expression* .Type</span></span>

<span data-ttu-id="08cac-108">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="08cac-108">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="08cac-109">注解</span><span class="sxs-lookup"><span data-stu-id="08cac-109">Remarks</span></span>

<span data-ttu-id="08cac-p102">设置或返回值是一个指示操作类型或数据类型的常量。对于 **Field** 对象，该属性是可读写的，直到该对象追加到集合或另一个对象中，该属性才变为只读。</span><span class="sxs-lookup"><span data-stu-id="08cac-p102">The setting or return value is a constant that indicates an operational or data type. For a **Field** object, this property is read/write until the object is appended to a collection or to another object, after which it's read-only.</span></span>

<span data-ttu-id="08cac-112">对于 **Field** 对象，下表中描述了可能的设置和返回值。</span><span class="sxs-lookup"><span data-stu-id="08cac-112">For a **Field** object, the possible settings and return values are described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="08cac-113">常量</span><span class="sxs-lookup"><span data-stu-id="08cac-113">Constant</span></span></p></th>
<th><p><span data-ttu-id="08cac-114">说明</span><span class="sxs-lookup"><span data-stu-id="08cac-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08cac-115"><strong>dbBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-115"><strong>dbBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-116">大整数</span><span class="sxs-lookup"><span data-stu-id="08cac-116">Big Integer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-117"><strong>dbBinary</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-117"><strong>dbBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-118">Binary</span><span class="sxs-lookup"><span data-stu-id="08cac-118">Binary</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-119"><strong>dbBoolean</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-119"><strong>dbBoolean</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-120">Boolean</span><span class="sxs-lookup"><span data-stu-id="08cac-120">Boolean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-121"><strong>dbByte</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-121"><strong>dbByte</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-122">字节</span><span class="sxs-lookup"><span data-stu-id="08cac-122">Byte</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-123"><strong>dbChar</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-123"><strong>dbChar</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-124">字符</span><span class="sxs-lookup"><span data-stu-id="08cac-124">Char</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-125"><strong>dbCurrency</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-125"><strong>dbCurrency</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-126">货币</span><span class="sxs-lookup"><span data-stu-id="08cac-126">Currency</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-127"><strong>dbDate</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-127"><strong>dbDate</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-128">日期/时间</span><span class="sxs-lookup"><span data-stu-id="08cac-128">Date/Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-129"><strong>dbDecimal</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-129"><strong>dbDecimal</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-130">小数</span><span class="sxs-lookup"><span data-stu-id="08cac-130">Decimal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-131"><strong>dbDouble</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-131"><strong>dbDouble</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-132">Double</span><span class="sxs-lookup"><span data-stu-id="08cac-132">Double</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-133"><strong>dbFloat</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-133"><strong>dbFloat</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-134">Float</span><span class="sxs-lookup"><span data-stu-id="08cac-134">Float</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-135"><strong>dbGUID</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-135"><strong>dbGUID</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-136">GUID</span><span class="sxs-lookup"><span data-stu-id="08cac-136">GUID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-137"><strong>dbInteger</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-137"><strong>dbInteger</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-138">整数</span><span class="sxs-lookup"><span data-stu-id="08cac-138">Integer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-139"><strong>dbLong</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-139"><strong>dbLong</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-140">Long</span><span class="sxs-lookup"><span data-stu-id="08cac-140">Long</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-141"><strong>dbLongBinary</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-141"><strong>dbLongBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-142">长二进制（OLE 对象）</span><span class="sxs-lookup"><span data-stu-id="08cac-142">Long Binary (OLE Object)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-143"><strong>dbMemo</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-143"><strong>dbMemo</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-144">Memo</span><span class="sxs-lookup"><span data-stu-id="08cac-144">Memo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-145"><strong>dbNumeric</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-145"><strong>dbNumeric</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-146">Numeric</span><span class="sxs-lookup"><span data-stu-id="08cac-146">Numeric</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-147"><strong>dbSingle</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-147"><strong>dbSingle</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-148">Single</span><span class="sxs-lookup"><span data-stu-id="08cac-148">Single</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-149"><strong>dbText</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-149"><strong>dbText</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-150">文本</span><span class="sxs-lookup"><span data-stu-id="08cac-150">Text</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-151"><strong>dbTime</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-151"><strong>dbTime</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-152">时间</span><span class="sxs-lookup"><span data-stu-id="08cac-152">Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08cac-153"><strong>dbTimeStamp</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-153"><strong>dbTimeStamp</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-154">时间戳</span><span class="sxs-lookup"><span data-stu-id="08cac-154">Time Stamp</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08cac-155"><strong>dbVarBinary</strong></span><span class="sxs-lookup"><span data-stu-id="08cac-155"><strong>dbVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="08cac-156">VarBinary</span><span class="sxs-lookup"><span data-stu-id="08cac-156">VarBinary</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="08cac-157">将新的 **Field**、 **Parameter** 或 **Property** 对象追加到 **[Index](index-object-dao.md)** 、 **QueryDef**、 **Recordset** 或 **TableDef** 对象集合中时，如果基础数据库不支持为新对象指定的数据类型，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="08cac-157">When you append a new **Field**, **Parameter**, or **Property** object to the collection of an **[Index](index-object-dao.md)**, **QueryDef**, **Recordset**, or **TableDef** object, an error occurs if the underlying database doesn't support the data type specified for the new object.</span></span>

