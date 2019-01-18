---
title: DateModified 属性 (ADOX)
TOCTitle: DateModified property (ADOX)
ms:assetid: aebe8818-82e7-84a4-24d7-d97afa32e193
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249827(v=office.15)
ms:contentKeyID: 48547078
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: daf72804d51c18b5875e607ce5fdb0dfe20f406c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726076"
---
# <a name="datemodified-property-adox"></a><span data-ttu-id="a5ba4-102">DateModified 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="a5ba4-102">DateModified property (ADOX)</span></span>


<span data-ttu-id="a5ba4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a5ba4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a5ba4-104">指示上次修改对象的日期。</span><span class="sxs-lookup"><span data-stu-id="a5ba4-104">Indicates the date the object was last modified.</span></span>

## <a name="return-values"></a><span data-ttu-id="a5ba4-105">返回值</span><span class="sxs-lookup"><span data-stu-id="a5ba4-105">Return values</span></span>

<span data-ttu-id="a5ba4-p101">返回一个指定修改日期的 **Variant** 值。如果提供程序不支持 **DateModified** ，则该值为 null。</span><span class="sxs-lookup"><span data-stu-id="a5ba4-p101">Returns a **Variant** value specifying the date modified. The value is null if **DateModified** is not supported by the provider.</span></span>

## <a name="remarks"></a><span data-ttu-id="a5ba4-108">说明</span><span class="sxs-lookup"><span data-stu-id="a5ba4-108">Remarks</span></span>

<span data-ttu-id="a5ba4-p102">对于新追加的对象， **DateModified** 属性为 null。追加新的 [View](view-object-adox.md) 或 [Procedure](procedure-object-adox.md) 之后，必须调用 [Views](refresh-method-ado.md) 或 [Procedures](views-collection-adox.md) 集合的 [Refresh](procedures-collection-adox.md) 方法，以获取 **DateModified** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="a5ba4-p102">The **DateModified** property is null for newly appended objects. After appending a new [View](view-object-adox.md) or [Procedure](procedure-object-adox.md), you must call the [Refresh](refresh-method-ado.md) method of the [Views](views-collection-adox.md) or [Procedures](procedures-collection-adox.md) collection to obtain values for the **DateModified** property.</span></span>

