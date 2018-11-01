---
title: DateCreated 属性 (ADOX)
TOCTitle: DateCreated Property (ADOX)
ms:assetid: ee975bf5-7d44-a993-d1c0-077993515698
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250209(v=office.15)
ms:contentKeyID: 48548564
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fea3e83f9a171a95eb844d9ba721039969804acf
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876468"
---
# <a name="datecreated-property-adox"></a><span data-ttu-id="27628-102">DateCreated 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="27628-102">DateCreated Property (ADOX)</span></span>


<span data-ttu-id="27628-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="27628-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="27628-104">指示创建对象的日期。</span><span class="sxs-lookup"><span data-stu-id="27628-104">Indicates the date the object was created.</span></span>

## <a name="return-values"></a><span data-ttu-id="27628-105">返回值</span><span class="sxs-lookup"><span data-stu-id="27628-105">Return values</span></span>

<span data-ttu-id="27628-p101">返回一个指定创建日期的 **Variant** 值。如果提供程序不支持 **DateCreated** ，则该值为 null。</span><span class="sxs-lookup"><span data-stu-id="27628-p101">Returns a **Variant** value specifying the date created. The value is null if **DateCreated** is not supported by the provider.</span></span>

## <a name="remarks"></a><span data-ttu-id="27628-108">说明</span><span class="sxs-lookup"><span data-stu-id="27628-108">Remarks</span></span>

<span data-ttu-id="27628-p102">对于新追加的对象， **DateCreated** 属性为 null。追加新的 [View](view-object-adox.md) 或 [Procedure](procedure-object-adox.md) 之后，必须调用 [Views](refresh-method-ado.md) 或 [Procedures](views-collection-adox.md) 集合的 [Refresh](procedures-collection-adox.md) 方法，以获取 **DateCreated** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="27628-p102">The **DateCreated** property is null for newly appended objects. After appending a new [View](view-object-adox.md) or [Procedure](procedure-object-adox.md), you must call the [Refresh](refresh-method-ado.md) method of the [Views](views-collection-adox.md) or [Procedures](procedures-collection-adox.md) collection to obtain values for the **DateCreated** property.</span></span>

