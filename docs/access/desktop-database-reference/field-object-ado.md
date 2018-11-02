---
title: Field 对象的 ActiveX 数据对象 (ADO)
TOCTitle: Field object (ADO)
ms:assetid: 1dbd535e-48ad-a5c8-a1b2-6776c1e3e19d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248968(v=office.15)
ms:contentKeyID: 48543600
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d131f2634551c9c2538a87cdc8f15cfa6cc96430
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924868"
---
# <a name="field-object-ado"></a><span data-ttu-id="59eee-102">Field 对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="59eee-102">Field object (ADO)</span></span>


<span data-ttu-id="59eee-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="59eee-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="59eee-104">表示具有常规数据类型的数据列。</span><span class="sxs-lookup"><span data-stu-id="59eee-104">Represents a column of data with a common data type.</span></span>

## <a name="remarks"></a><span data-ttu-id="59eee-105">说明</span><span class="sxs-lookup"><span data-stu-id="59eee-105">Remarks</span></span>

<span data-ttu-id="59eee-p101">每个 **Field** 对应于 [Recordset](recordset-object-ado.md) 中的一个列。使用 [Field](value-property-ado.md) 对象的 **Value** 属性可以设置或返回当前记录的数据。取决于提供程序所公开的功能， **Field** 对象的某些集合、方法或属性可能不可用。</span><span class="sxs-lookup"><span data-stu-id="59eee-p101">Each **Field** object corresponds to a column in the [Recordset](recordset-object-ado.md). You use the [Value](value-property-ado.md) property of **Field** objects to set or return data for the current record. Depending on the functionality the provider exposes, some collections, methods, or properties of a **Field** object may not be available.</span></span>

<span data-ttu-id="59eee-109">使用 **Field** 对象的集合、方法和属性，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="59eee-109">With the collections, methods, and properties of a **Field** object, you can do the following:</span></span>

  - <span data-ttu-id="59eee-110">使用 [Name](name-property-ado.md) 属性返回字段的名称。</span><span class="sxs-lookup"><span data-stu-id="59eee-110">Return the name of a field with the [Name](name-property-ado.md) property.</span></span>

  - <span data-ttu-id="59eee-p102">使用 **Value** 属性查看或更改字段中的数据。 **Value** 是 **Field** 对象的默认属性。</span><span class="sxs-lookup"><span data-stu-id="59eee-p102">View or change the data in the field with the **Value** property. **Value** is the default property of the **Field** object.</span></span>

  - <span data-ttu-id="59eee-113">使用 [Type](type-property-ado.md)、[Precision](precision-property-ado.md) 和 [NumericScale](numericscale-property-ado.md) 属性，返回字段的基本特征。</span><span class="sxs-lookup"><span data-stu-id="59eee-113">Return the basic characteristics of a field with the [Type](type-property-ado.md), [Precision](precision-property-ado.md), and [NumericScale](numericscale-property-ado.md) properties.</span></span>

  - <span data-ttu-id="59eee-114">使用 [DefinedSize](definedsize-property-ado.md) 属性，返回字段的声明大小。</span><span class="sxs-lookup"><span data-stu-id="59eee-114">Return the declared size of a field with the [DefinedSize](definedsize-property-ado.md) property.</span></span>

  - <span data-ttu-id="59eee-115">使用 [ActualSize](actualsize-property-ado.md) 属性，返回给定字段中数据的实际大小。</span><span class="sxs-lookup"><span data-stu-id="59eee-115">Return the actual size of the data in a given field with the [ActualSize](actualsize-property-ado.md) property.</span></span>

  - <span data-ttu-id="59eee-116">使用 [Attributes](attributes-property-ado.md) 属性和 [Properties](properties-collection-ado.md) 集合，确定给定字段所支持的功能类型。</span><span class="sxs-lookup"><span data-stu-id="59eee-116">Determine what types of functionality are supported for a given field with the [Attributes](attributes-property-ado.md) property and [Properties](properties-collection-ado.md) collection.</span></span>

  - <span data-ttu-id="59eee-117">使用 [AppendChunk](appendchunk-method-ado.md) 和 [GetChunk](getchunk-method-ado.md) 方法，对包含长二进制或长字符数据的字段的值进行操作。</span><span class="sxs-lookup"><span data-stu-id="59eee-117">Manipulate the values of fields containing long binary or long character data with the [AppendChunk](appendchunk-method-ado.md) and [GetChunk](getchunk-method-ado.md) methods.</span></span>

  - <span data-ttu-id="59eee-118">如果提供程序支持批更新，则在批更新过程中，使用 [OriginalValue](originalvalue-property-ado.md) 和 [UnderlyingValue](underlyingvalue-property-ado.md) 属性解决字段值中的差异。</span><span class="sxs-lookup"><span data-stu-id="59eee-118">If the provider supports batch updates, resolve discrepancies in field values during batch updating with the [OriginalValue](originalvalue-property-ado.md) and [UnderlyingValue](underlyingvalue-property-ado.md) properties.</span></span>

<span data-ttu-id="59eee-p103">打开 **Field** 对象的 **Recordset** 之前，所有元数据属性（**Name**、**Type**、**DefinedSize**、**Precision** 和 **NumericScale**）都可用。在此时设置它们有助于动态构造窗体。</span><span class="sxs-lookup"><span data-stu-id="59eee-p103">All of the metadata properties (**Name**, **Type**, **DefinedSize**, **Precision**, and **NumericScale**) are available before opening the **Field** object's **Recordset**. Setting them at that time is useful for dynamically constructing forms.</span></span>

