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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726160"
---
# <a name="precision-property-adox"></a><span data-ttu-id="717b5-102">Precision 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="717b5-102">Precision property (ADOX)</span></span>


<span data-ttu-id="717b5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="717b5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="717b5-104">指示列中的数据值的最大精度。</span><span class="sxs-lookup"><span data-stu-id="717b5-104">Indicates the maximum precision of data values in the column.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="717b5-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="717b5-105">Settings and return values</span></span>

<span data-ttu-id="717b5-p101">设置和返回一个 **Long** 值，该值为当列的 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) 属性为数值类型时数据值的最大精度。对于所有其他数据类型将忽略 **Precision** 。</span><span class="sxs-lookup"><span data-stu-id="717b5-p101">Sets and returns a **Long** value that is the maximum precision of data values in the column when the [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) property is a numeric type. **Precision** is ignored for all other data types.</span></span>

## <a name="remarks"></a><span data-ttu-id="717b5-108">备注</span><span class="sxs-lookup"><span data-stu-id="717b5-108">Remarks</span></span>

<span data-ttu-id="717b5-109">默认值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="717b5-109">The default value is zero (0).</span></span>

<span data-ttu-id="717b5-110">对于已追加到集合中的 [Column](column-object-adox.md) 对象，此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="717b5-110">This property is read-only for [Column](column-object-adox.md) objects already appended to a collection.</span></span>

