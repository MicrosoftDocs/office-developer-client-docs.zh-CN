---
title: Precision 属性 (ADOX)
TOCTitle: Precision property (ADOX)
ms:assetid: 5d8ca497-572a-52e0-18aa-f82deaea0813
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249330(v=office.15)
ms:contentKeyID: 48545117
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f05f6880a9599421189519f263cfb27bf1432325
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287480"
---
# <a name="precision-property-adox"></a><span data-ttu-id="3fab2-102">Precision 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="3fab2-102">Precision property (ADOX)</span></span>


<span data-ttu-id="3fab2-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="3fab2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3fab2-104">指示列中的数据值的最大精度。</span><span class="sxs-lookup"><span data-stu-id="3fab2-104">Indicates the maximum precision of data values in the column.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="3fab2-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="3fab2-105">Settings and return values</span></span>

<span data-ttu-id="3fab2-p101">设置和返回一个 **Long** 值，该值为当列的 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) 属性为数值类型时数据值的最大精度。对于所有其他数据类型将忽略 **Precision** 。</span><span class="sxs-lookup"><span data-stu-id="3fab2-p101">Sets and returns a **Long** value that is the maximum precision of data values in the column when the [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) property is a numeric type. **Precision** is ignored for all other data types.</span></span>

## <a name="remarks"></a><span data-ttu-id="3fab2-108">注解</span><span class="sxs-lookup"><span data-stu-id="3fab2-108">Remarks</span></span>

<span data-ttu-id="3fab2-109">默认值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="3fab2-109">The default value is zero (0).</span></span>

<span data-ttu-id="3fab2-110">对于已追加到集合中的 [Column](column-object-adox.md) 对象，此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="3fab2-110">This property is read-only for [Column](column-object-adox.md) objects already appended to a collection.</span></span>

