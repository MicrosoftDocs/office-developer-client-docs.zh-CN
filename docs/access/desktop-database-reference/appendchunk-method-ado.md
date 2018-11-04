---
title: AppendChunk 方法 (ADO)
TOCTitle: AppendChunk method (ADO)
ms:assetid: 3fa931a3-2cd7-a3b0-a750-40e18bc9937e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249179(v=office.15)
ms:contentKeyID: 48544405
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9103135100c5a10931ee63bfbdeabe9d97119fd2
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949262"
---
# <a name="appendchunk-method-ado"></a><span data-ttu-id="f099e-102">AppendChunk 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="f099e-102">AppendChunk method (ADO)</span></span>

<span data-ttu-id="f099e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f099e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f099e-104">用于将数据追加到大型文本或二进制数据 [Field](field-object-ado.md) 或 [Parameter](parameter-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="f099e-104">Appends data to a large text or binary data [Field](field-object-ado.md), or to a [Parameter](parameter-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="f099e-105">语法</span><span class="sxs-lookup"><span data-stu-id="f099e-105">Syntax</span></span>

<span data-ttu-id="f099e-106">*对象。* AppendChunk*数据*</span><span class="sxs-lookup"><span data-stu-id="f099e-106">*object.* AppendChunk *Data*</span></span>

## <a name="parameters"></a><span data-ttu-id="f099e-107">参数</span><span class="sxs-lookup"><span data-stu-id="f099e-107">Parameters</span></span>

|<span data-ttu-id="f099e-108">参数</span><span class="sxs-lookup"><span data-stu-id="f099e-108">Parameter</span></span>|<span data-ttu-id="f099e-109">说明</span><span class="sxs-lookup"><span data-stu-id="f099e-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="f099e-110">*object*</span><span class="sxs-lookup"><span data-stu-id="f099e-110">*object*</span></span> |<span data-ttu-id="f099e-111">**Field** 或 **Parameter** 对象。</span><span class="sxs-lookup"><span data-stu-id="f099e-111">A **Field** or **Parameter** object.</span></span>|
|<span data-ttu-id="f099e-112">*Data*</span><span class="sxs-lookup"><span data-stu-id="f099e-112">*Data*</span></span> |<span data-ttu-id="f099e-113">**变量型** ，包含要追加到对象的数据。</span><span class="sxs-lookup"><span data-stu-id="f099e-113">A **Variant** that contains the data to append to the object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f099e-114">备注</span><span class="sxs-lookup"><span data-stu-id="f099e-114">Remarks</span></span>

<span data-ttu-id="f099e-p101">可以对 **Field** 或 **Parameter** 对象使用 **AppendChunk** 方法，用长型二进制或字符数据来填充该对象。如果系统内存有限，那么在处理长型数值时可以用 **AppendChunk** 方法将整个数据分成若干部分。</span><span class="sxs-lookup"><span data-stu-id="f099e-p101">Use the **AppendChunk** method on a **Field** or **Parameter** object to fill it with long binary or character data. In situations where system memory is limited, you can use the **AppendChunk** method to manipulate long values in portions rather than in their entirety.</span></span>

<span data-ttu-id="f099e-117">**Field**</span><span class="sxs-lookup"><span data-stu-id="f099e-117">**Field**</span></span>

<span data-ttu-id="f099e-118">如果 **Field** 对象的 [Attributes](attributes-property-ado.md) 属性中的 **adFldLong** 位设置为 True，那么可以对该字段使用 **AppendChunk** 方法。</span><span class="sxs-lookup"><span data-stu-id="f099e-118">If the **adFldLong** bit in the [Attributes](attributes-property-ado.md) property of a **Field** object is set to true, you can use the **AppendChunk** method for that field.</span></span>

<span data-ttu-id="f099e-p102">对 **Field** 对象第一次调用 **AppendChunk** 时，将数据写入字段，覆盖所有现有数据。之后调用 **AppendChunk** 时，在现有数据基础上进行添加。如果将数据追加到某个字段，然后设置或读取当前记录中另一个字段的值，那么 ADO 会假设您已完成了对第一个字段的数据追加。此时如果对第一个字段再次调用 **AppendChunk** 方法，则 ADO 会将调用解释为新的 **AppendChunk** 操作并覆盖现有数据。访问并非第一个 [Recordset](recordset-object-ado.md) 对象克隆的其他 **Recordset** 对象中的字段时，不会中断 **AppendChunk** 操作。</span><span class="sxs-lookup"><span data-stu-id="f099e-p102">The first **AppendChunk** call on a **Field** object writes data to the field, overwriting any existing data. Subsequent **AppendChunk** calls add to existing data. If you are appending data to one field and then you set or read the value of another field in the current record, ADO assumes that you are finished appending data to the first field. If you call the **AppendChunk** method on the first field again, ADO interprets the call as a new **AppendChunk** operation and overwrites the existing data. Accessing fields in other [Recordset](recordset-object-ado.md) objects that are not clones of the first **Recordset** object will not disrupt **AppendChunk** operations.</span></span>

<span data-ttu-id="f099e-124">如果在对 **Field** 对象调用 **AppendChunk** 时当前没有记录，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="f099e-124">If there is no current record when you call **AppendChunk** on a **Field** object, an error occurs.</span></span>


> [!NOTE]
> <span data-ttu-id="f099e-p103">[!注释] **AppendChunk** 方法不能对 **Record** 对象的 [Field](record-object-ado.md) 对象进行操作。它不执行任何操作，并将产生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="f099e-p103">The **AppendChunk** method does not operate on **Field** objects of a [Record](record-object-ado.md) object. It does not perform any operation and will produce a run-time error.</span></span>



<span data-ttu-id="f099e-127">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="f099e-127">**Parameter**</span></span>

<span data-ttu-id="f099e-128">如果 **Parameter** 对象的 **Attributes** 属性中的 **adParamLong** 位设置为 True，那么可以对该参数使用 **AppendChunk** 方法。</span><span class="sxs-lookup"><span data-stu-id="f099e-128">If the **adParamLong** bit in the **Attributes** property of a **Parameter** object is set to true, you can use the **AppendChunk** method for that parameter.</span></span>

<span data-ttu-id="f099e-p104">对 **Parameter** 对象第一次调用 **AppendChunk** 时，将数据写入参数，覆盖所有现有数据。之后对 **Parameter** 对象调用 **AppendChunk** 时，在现有参数数据基础上进行添加。如果 **AppendChunk** 调用传递的是 Null 值，则将放弃所有参数数据。</span><span class="sxs-lookup"><span data-stu-id="f099e-p104">The first **AppendChunk** call on a **Parameter** object writes data to the parameter, overwriting any existing data. Subsequent **AppendChunk** calls on a **Parameter** object add to existing parameter data. An **AppendChunk** call that passes a null value discards all of the parameter data.</span></span>

