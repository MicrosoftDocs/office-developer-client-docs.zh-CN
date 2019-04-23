---
title: Parameter 属性 (DAO)
TOCTitle: Type Property
ms:assetid: 68205cd6-eb45-56a3-593f-e1203472037b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195248(v=office.15)
ms:contentKeyID: 48545377
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 208d0a5097b8473fef60b94f972f2c8579150fc7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288019"
---
# <a name="parametertype-property-dao"></a><span data-ttu-id="aa613-102">Parameter 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="aa613-102">Parameter.Type property (DAO)</span></span>


<span data-ttu-id="aa613-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="aa613-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="aa613-104">设置或返回一个值，该值指示对象的操作类型或数据类型。</span><span class="sxs-lookup"><span data-stu-id="aa613-104">Sets or returns a value that indicates the operational type or data type of an object.</span></span> <span data-ttu-id="aa613-105">可读/写 **Integer** 类型。</span><span class="sxs-lookup"><span data-stu-id="aa613-105">Read/write **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa613-106">语法</span><span class="sxs-lookup"><span data-stu-id="aa613-106">Syntax</span></span>

<span data-ttu-id="aa613-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="aa613-107">*expression* .Type</span></span>

<span data-ttu-id="aa613-108">*表达式*一个代表**Parameter**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="aa613-108">*expression* A variable that represents a **Parameter** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa613-109">注解</span><span class="sxs-lookup"><span data-stu-id="aa613-109">Remarks</span></span>

<span data-ttu-id="aa613-p102">设置值或返回值是一个指示操作类型或数据类型的常量。对于 Microsoft Access 工作区中的 **[Parameter](parameter-object-dao.md)** 对象，该属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="aa613-p102">The setting or return value is a constant that indicates an operational or data type. For a **[Parameter](parameter-object-dao.md)** object in a Microsoft Access workspace the property is read-only.</span></span>

<span data-ttu-id="aa613-112">对于 **Parameter** 对象，下表中描述了可能的设置和返回值。</span><span class="sxs-lookup"><span data-stu-id="aa613-112">For a **Parameter** object, the possible settings and return values are described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="aa613-113">常量</span><span class="sxs-lookup"><span data-stu-id="aa613-113">Constant</span></span></p></th>
<th><p><span data-ttu-id="aa613-114">说明</span><span class="sxs-lookup"><span data-stu-id="aa613-114">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa613-115"><strong>dbBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-115"><strong>dbBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-116">大整数</span><span class="sxs-lookup"><span data-stu-id="aa613-116">Big Integer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-117"><strong>dbBinary</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-117"><strong>dbBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-118">Binary</span><span class="sxs-lookup"><span data-stu-id="aa613-118">Binary</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-119"><strong>dbBoolean</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-119"><strong>dbBoolean</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-120">Boolean</span><span class="sxs-lookup"><span data-stu-id="aa613-120">Boolean</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-121"><strong>dbByte</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-121"><strong>dbByte</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-122">字节</span><span class="sxs-lookup"><span data-stu-id="aa613-122">Byte</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-123"><strong>dbChar</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-123"><strong>dbChar</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-124">Char</span><span class="sxs-lookup"><span data-stu-id="aa613-124">Char</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-125"><strong>dbCurrency</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-125"><strong>dbCurrency</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-126">货币</span><span class="sxs-lookup"><span data-stu-id="aa613-126">Currency</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-127"><strong>dbDate</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-127"><strong>dbDate</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-128">日期/时间</span><span class="sxs-lookup"><span data-stu-id="aa613-128">Date/Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-129"><strong>dbDecimal</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-129"><strong>dbDecimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-130">小数</span><span class="sxs-lookup"><span data-stu-id="aa613-130">Decimal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-131"><strong>dbDouble</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-131"><strong>dbDouble</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-132">双精度</span><span class="sxs-lookup"><span data-stu-id="aa613-132">Double</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-133"><strong>dbFloat</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-133"><strong>dbFloat</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-134">点数</span><span class="sxs-lookup"><span data-stu-id="aa613-134">Float</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-135"><strong>dbGUID</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-135"><strong>dbGUID</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-136">GUID</span><span class="sxs-lookup"><span data-stu-id="aa613-136">GUID</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-137"><strong>dbInteger</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-137"><strong>dbInteger</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-138">整数</span><span class="sxs-lookup"><span data-stu-id="aa613-138">Integer</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-139"><strong>dbLong</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-139"><strong>dbLong</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-140">Long</span><span class="sxs-lookup"><span data-stu-id="aa613-140">Long</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-141"><strong>dbLongBinary</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-141"><strong>dbLongBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-142">长二进制（OLE 对象）</span><span class="sxs-lookup"><span data-stu-id="aa613-142">Long Binary (OLE Object)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-143"><strong>dbMemo</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-143"><strong>dbMemo</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-144">备注</span><span class="sxs-lookup"><span data-stu-id="aa613-144">Memo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-145"><strong>dbNumeric</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-145"><strong>dbNumeric</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-146">Numeric</span><span class="sxs-lookup"><span data-stu-id="aa613-146">Numeric</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-147"><strong>dbSingle</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-147"><strong>dbSingle</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-148">单倍行距</span><span class="sxs-lookup"><span data-stu-id="aa613-148">Single</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-149"><strong>dbText</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-149"><strong>dbText</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-150">文本</span><span class="sxs-lookup"><span data-stu-id="aa613-150">Text</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-151"><strong>dbTime</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-151"><strong>dbTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-152">Time</span><span class="sxs-lookup"><span data-stu-id="aa613-152">Time</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa613-153"><strong>dbTimeStamp</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-153"><strong>dbTimeStamp</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-154">时间戳</span><span class="sxs-lookup"><span data-stu-id="aa613-154">Time Stamp</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa613-155"><strong>dbVarBinary</strong></span><span class="sxs-lookup"><span data-stu-id="aa613-155"><strong>dbVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="aa613-156">VarBinary</span><span class="sxs-lookup"><span data-stu-id="aa613-156">VarBinary</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa613-157">将新的 **Field**、 **Parameter** 或 **Property** 对象追加到 **[Index](index-object-dao.md)** 、 **QueryDef**、 **Recordset** 或 **TableDef** 对象集合中时，如果基础数据库不支持为新对象指定的数据类型，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="aa613-157">When you append a new **Field**, **Parameter**, or **Property** object to the collection of an **[Index](index-object-dao.md)**, **QueryDef**, **Recordset**, or **TableDef** object, an error occurs if the underlying database doesn't support the data type specified for the new object.</span></span>

