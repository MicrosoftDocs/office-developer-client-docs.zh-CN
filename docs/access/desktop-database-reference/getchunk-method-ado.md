---
title: GetChunk 方法 (ADO)
TOCTitle: GetChunk method (ADO)
ms:assetid: 1ef1c37a-8453-8d3b-251a-d16e0d519fd7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248979(v=office.15)
ms:contentKeyID: 48543629
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 44cd0cb5632e64811de14f9abd3c78aac9203705
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698181"
---
# <a name="getchunk-method-ado"></a><span data-ttu-id="09720-102">GetChunk 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="09720-102">GetChunk method (ADO)</span></span>

<span data-ttu-id="09720-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="09720-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="09720-104">用于返回较大文本或二进制数据 [Field](field-object-ado.md) 对象的全部内容或部分内容。</span><span class="sxs-lookup"><span data-stu-id="09720-104">Returns all, or a portion, of the contents of a large text or binary data [Field](field-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="09720-105">语法</span><span class="sxs-lookup"><span data-stu-id="09720-105">Syntax</span></span>

<span data-ttu-id="09720-106">*变量* = *字段*。GetChunk （*大小*）</span><span class="sxs-lookup"><span data-stu-id="09720-106">*variable* = *field*.GetChunk(*Size* )</span></span>

## <a name="return-value"></a><span data-ttu-id="09720-107">返回值</span><span class="sxs-lookup"><span data-stu-id="09720-107">Return value</span></span>

<span data-ttu-id="09720-108">返回 **变量型** 值。</span><span class="sxs-lookup"><span data-stu-id="09720-108">Returns a **Variant**.</span></span>

## <a name="parameters"></a><span data-ttu-id="09720-109">参数</span><span class="sxs-lookup"><span data-stu-id="09720-109">Parameters</span></span>

|<span data-ttu-id="09720-110">参数</span><span class="sxs-lookup"><span data-stu-id="09720-110">Parameter</span></span>|<span data-ttu-id="09720-111">说明</span><span class="sxs-lookup"><span data-stu-id="09720-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="09720-112">*Size*</span><span class="sxs-lookup"><span data-stu-id="09720-112">*Size*</span></span> |<span data-ttu-id="09720-113">**长整型** 表达式，等于您要检索的字节数或字符数。</span><span class="sxs-lookup"><span data-stu-id="09720-113">A **Long** expression that is equal to the number of bytes or characters that you want to retrieve.</span></span>|

## <a name="remarks"></a><span data-ttu-id="09720-114">备注</span><span class="sxs-lookup"><span data-stu-id="09720-114">Remarks</span></span>

<span data-ttu-id="09720-p101">对 **Field** 对象使用 **GetChunk** 方法可以检索其部分或全部长整型二进制数据或字符数据。如果系统内存有限，则可以使用 **GetChunk** 方法对部分（而不是全部）长整型值进行操作。</span><span class="sxs-lookup"><span data-stu-id="09720-p101">Use the **GetChunk** method on a **Field** object to retrieve part or all of its long binary or character data. In situations where system memory is limited, you can use the **GetChunk** method to manipulate long values in portions, rather than in their entirety.</span></span>

<span data-ttu-id="09720-p102">**GetChunk** 调用返回的数据会分配给*变量*。如果 *Size* 大于剩余的数据，则 **GetChunk** 方法仅返回剩余的数据，而不会使用空格来填充*变量*。如果字段空白，则 **GetChunk** 方法返回一个 Null 值。</span><span class="sxs-lookup"><span data-stu-id="09720-p102">The data that a **GetChunk** call returns is assigned to *variable*. If *Size* is greater than the remaining data, the **GetChunk** method returns only the remaining data without padding *variable* with empty spaces. If the field is empty, the **GetChunk** method returns a null value.</span></span>

<span data-ttu-id="09720-p103">每个随后的 **GetChunk** 调用从上一个 **GetChunk** 调用停止的地方开始检索数据。但是，如果您从某个字段检索数据，随后设置或读取当前记录中另一个字段的值，ADO 将假定您已经从第一个字段检索完数据。如果再次对第一个字段调用 **GetChunk** 方法，ADO 将把调用解释为新的 **GetChunk** 操作，并从数据的开头开始读取。如果访问其他 [Recordset](recordset-object-ado.md) 对象中的字段，且这些字段不是第一个 **Recordset** 对象的克隆，则不会中断 **GetChunk** 操作。</span><span class="sxs-lookup"><span data-stu-id="09720-p103">Each subsequent **GetChunk** call retrieves data starting from where the previous **GetChunk** call left off. However, if you are retrieving data from one field and then you set or read the value of another field in the current record, ADO assumes you have finished retrieving data from the first field. If you call the **GetChunk** method on the first field again, ADO interprets the call as a new **GetChunk** operation and starts reading from the beginning of the data. Accessing fields in other [Recordset](recordset-object-ado.md) objects that are not clones of the first **Recordset** object will not disrupt **GetChunk** operations.</span></span>

<span data-ttu-id="09720-124">如果将 **Field** 对象的 [Attributes](attributes-property-ado.md) 属性的 **adFldLong** 位设置为 **True** ，则可以对该字段使用 **GetChunk** 方法。</span><span class="sxs-lookup"><span data-stu-id="09720-124">If the **adFldLong** bit in the [Attributes](attributes-property-ado.md) property of a **Field** object is set to **True**, you can use the **GetChunk** method for that field.</span></span>

<span data-ttu-id="09720-125">如果对 **Field** 对象使用 **GetChunk** 方法时没用当前记录，将发生错误 3021（无当前记录）。</span><span class="sxs-lookup"><span data-stu-id="09720-125">If there is no current record when you use the **GetChunk** method on a **Field** object, error 3021 (no current record) occurs.</span></span>


> [!NOTE]
> <span data-ttu-id="09720-p104">[!注释] **GetChunk** 方法不会作用于 **Record** 对象的 [Field](record-object-ado.md) 对象。它不会执行任何操作，并且将生成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="09720-p104">The **GetChunk** method does not operate on **Field** objects of a [Record](record-object-ado.md) object. It does not perform any operation and will produce a run-time error.</span></span>


