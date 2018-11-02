---
title: Property 对象 (ADO)
TOCTitle: Property object (ADO)
ms:assetid: eec318fd-f5ed-d9ef-9830-848439a8914d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250210(v=office.15)
ms:contentKeyID: 48548567
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b26a305557e2b7244399c6c2c5513909846eaaff
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929565"
---
# <a name="property-object-ado"></a><span data-ttu-id="9e49c-102">Property 对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="9e49c-102">Property object (ADO)</span></span>


<span data-ttu-id="9e49c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9e49c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9e49c-104">表示提供程序所定义的 ADO 对象的动态特征。</span><span class="sxs-lookup"><span data-stu-id="9e49c-104">Represents a dynamic characteristic of an ADO object that is defined by the provider.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e49c-105">说明</span><span class="sxs-lookup"><span data-stu-id="9e49c-105">Remarks</span></span>

<span data-ttu-id="9e49c-106">ADO 对象有两种类型的属性：内置和动态。</span><span class="sxs-lookup"><span data-stu-id="9e49c-106">ADO objects have two types of properties: built-in and dynamic.</span></span>

<span data-ttu-id="9e49c-107">内置属性是这些属性在 ADO 中实现并且立即可用到任何新的对象，使用语法。</span><span class="sxs-lookup"><span data-stu-id="9e49c-107">Built-in properties are those properties implemented in ADO and immediately available to any new object, using the syntax.</span></span> <span data-ttu-id="9e49c-108">内置属性不会作为 **Property** 对象出现在对象的 [Properties](properties-collection-ado.md) 集合中，因此，尽管可以更改属性值，但不能修改属性的特征。</span><span class="sxs-lookup"><span data-stu-id="9e49c-108">They do not appear as **Property** objects in an object's [Properties](properties-collection-ado.md) collection, so although you can change their values, you cannot modify their characteristics.</span></span>

<span data-ttu-id="9e49c-109">动态属性是由基础数据提供程序定义的，它们出现在相应的 ADO 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="9e49c-109">Dynamic properties are defined by the underlying data provider, and appear in the **Properties** collection for the appropriate ADO object.</span></span> <span data-ttu-id="9e49c-110">例如，特定于提供程序的属性可以指示 [Recordset](recordset-object-ado.md) 对象是否支持事务或更新。</span><span class="sxs-lookup"><span data-stu-id="9e49c-110">For example, a property specific to the provider may indicate if a [Recordset](recordset-object-ado.md) object supports transactions or updating.</span></span> <span data-ttu-id="9e49c-111">这些额外的属性将作为 **Property** 对象出现在 **Recordset** 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="9e49c-111">These additional properties will appear as **Property** objects in that **Recordset** object's **Properties** collection.</span></span> <span data-ttu-id="9e49c-112">动态属性可以仅通过集合，并使用 MyObject.Properties(0) 引用或 MyObject.Properties("Name") 语法。</span><span class="sxs-lookup"><span data-stu-id="9e49c-112">Dynamic properties can be referenced only through the collection, using the MyObject.Properties(0) or or MyObject.Properties("Name") syntax.</span></span>

<span data-ttu-id="9e49c-113">这两种属性都是不可删除的。</span><span class="sxs-lookup"><span data-stu-id="9e49c-113">You cannot delete either kind of property.</span></span>

<span data-ttu-id="9e49c-114">动态 **Property** 对象有四个它自己的内置属性：</span><span class="sxs-lookup"><span data-stu-id="9e49c-114">A dynamic **Property** object has four built-in properties of its own:</span></span>

  - <span data-ttu-id="9e49c-115">[Name](name-property-ado.md) 属性是用于标识该属性的字符串。</span><span class="sxs-lookup"><span data-stu-id="9e49c-115">The [Name](name-property-ado.md) property is a string that identifies the property.</span></span>

  - <span data-ttu-id="9e49c-116">[Type](type-property-ado.md) 属性是用于指定属性数据类型的整数。</span><span class="sxs-lookup"><span data-stu-id="9e49c-116">The [Type](type-property-ado.md) property is an integer that specifies the property data type.</span></span>

  - <span data-ttu-id="9e49c-p103">[Value](value-property-ado.md) 属性是包含属性设置的变量型。 **Value** 是 **Property** 对象的默认属性。</span><span class="sxs-lookup"><span data-stu-id="9e49c-p103">The [Value](value-property-ado.md) property is a variant that contains the property setting. **Value** is the default property for a **Property** object.</span></span>

  - <span data-ttu-id="9e49c-119">[Attributes](attributes-property-ado.md) 属性是长值，用于指示特定于提供程序的属性的特征。</span><span class="sxs-lookup"><span data-stu-id="9e49c-119">The [Attributes](attributes-property-ado.md) property is a long value that indicates characteristics of the property specific to the provider.</span></span>

