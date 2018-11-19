---
title: NumericScale 属性 (ADOX)
TOCTitle: NumericScale property (ADOX)
ms:assetid: ebe73bdc-2570-f54a-3d2f-85a2a4634c9a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250197(v=office.15)
ms:contentKeyID: 48548501
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1b1a15f78463ca0ff6e690b600b9cdca7cc194c7
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025957"
---
# <a name="numericscale-property-adox"></a><span data-ttu-id="4c7cb-102">NumericScale 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="4c7cb-102">NumericScale property (ADOX)</span></span>


<span data-ttu-id="4c7cb-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4c7cb-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4c7cb-104">指示列中数值的小数位数。</span><span class="sxs-lookup"><span data-stu-id="4c7cb-104">Indicates the scale of a numeric value in the column.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="4c7cb-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="4c7cb-105">Settings and return values</span></span>

<span data-ttu-id="4c7cb-p101">设置和返回一个 **Byte** 值，该值为当列的 [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) 属性为 **adNumeric** 或 **adDecimal** 时列中的数据值的小数位数。对于所有其他数据类型，都忽略 **NumericScale** 。</span><span class="sxs-lookup"><span data-stu-id="4c7cb-p101">Sets and returns a **Byte** value that is the scale of data values in the column when the [Type](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/type-property-columnadox) property is **adNumeric** or **adDecimal**. **NumericScale** is ignored for all other data types.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c7cb-108">备注</span><span class="sxs-lookup"><span data-stu-id="4c7cb-108">Remarks</span></span>

<span data-ttu-id="4c7cb-109">默认值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="4c7cb-109">The default value is zero (0).</span></span>

<span data-ttu-id="4c7cb-110">对于已追加到集合中的 **Column** 对象， [NumericScale](column-object-adox.md) 为只读。</span><span class="sxs-lookup"><span data-stu-id="4c7cb-110">**NumericScale** is read-only for [Column](column-object-adox.md) objects already appended to a collection.</span></span>

