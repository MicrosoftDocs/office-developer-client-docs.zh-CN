---
title: DateModified 属性 (ADOX)
TOCTitle: DateModified Property (ADOX)
ms:assetid: aebe8818-82e7-84a4-24d7-d97afa32e193
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249827(v=office.15)
ms:contentKeyID: 48547078
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ceafd13b33536a77a1d793e7167fe8042609be5e
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603327"
---
# <a name="datemodified-property-adox"></a><span data-ttu-id="d40fa-102">DateModified 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="d40fa-102">DateModified Property (ADOX)</span></span>


<span data-ttu-id="d40fa-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d40fa-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d40fa-104">指示上次修改对象的日期。</span><span class="sxs-lookup"><span data-stu-id="d40fa-104">Indicates the date the object was last modified.</span></span>

<span data-ttu-id="d40fa-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="d40fa-105"><<<<<<< HEAD</span></span>
## <a name="return-values"></a><span data-ttu-id="d40fa-106">返回值</span><span class="sxs-lookup"><span data-stu-id="d40fa-106">Return Values</span></span>
=======
## <a name="return-values"></a><span data-ttu-id="d40fa-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d40fa-107">Return values</span></span>
>>>>>>> <span data-ttu-id="d40fa-108">master</span><span class="sxs-lookup"><span data-stu-id="d40fa-108">master</span></span>

<span data-ttu-id="d40fa-p101">返回一个指定修改日期的 **Variant** 值。如果提供程序不支持 **DateModified** ，则该值为 null。</span><span class="sxs-lookup"><span data-stu-id="d40fa-p101">Returns a **Variant** value specifying the date modified. The value is null if **DateModified** is not supported by the provider.</span></span>

## <a name="remarks"></a><span data-ttu-id="d40fa-111">说明</span><span class="sxs-lookup"><span data-stu-id="d40fa-111">Remarks</span></span>

<span data-ttu-id="d40fa-p102">对于新追加的对象， **DateModified** 属性为 null。追加新的 [View](view-object-adox.md) 或 [Procedure](procedure-object-adox.md) 之后，必须调用 [Views](refresh-method-ado.md) 或 [Procedures](views-collection-adox.md) 集合的 [Refresh](procedures-collection-adox.md) 方法，以获取 **DateModified** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="d40fa-p102">The **DateModified** property is null for newly appended objects. After appending a new [View](view-object-adox.md) or [Procedure](procedure-object-adox.md), you must call the [Refresh](refresh-method-ado.md) method of the [Views](views-collection-adox.md) or [Procedures](procedures-collection-adox.md) collection to obtain values for the **DateModified** property.</span></span>

