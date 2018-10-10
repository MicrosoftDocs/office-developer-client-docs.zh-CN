---
title: NumericScale 属性 (ADOX)
TOCTitle: NumericScale Property (ADOX)
ms:assetid: ebe73bdc-2570-f54a-3d2f-85a2a4634c9a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250197(v=office.15)
ms:contentKeyID: 48548501
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4229a318c4eb855b86164f02f1075d29a915d718
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467770"
---
# <a name="numericscale-property-adox"></a><span data-ttu-id="c6b58-102">NumericScale 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="c6b58-102">NumericScale Property (ADOX)</span></span>


<span data-ttu-id="c6b58-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c6b58-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c6b58-104">指示列中数值的小数位数。</span><span class="sxs-lookup"><span data-stu-id="c6b58-104">Indicates the scale of a numeric value in the column.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="c6b58-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="c6b58-105">Settings and Return Values</span></span>

<span data-ttu-id="c6b58-p101">设置和返回一个 **Byte** 值，该值为当列的 [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) 属性为 **adNumeric** 或 **adDecimal** 时列中的数据值的小数位数。对于所有其他数据类型，都忽略 **NumericScale** 。</span><span class="sxs-lookup"><span data-stu-id="c6b58-p101">Sets and returns a **Byte** value that is the scale of data values in the column when the [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) property is **adNumeric** or **adDecimal**. **NumericScale** is ignored for all other data types.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6b58-108">备注</span><span class="sxs-lookup"><span data-stu-id="c6b58-108">Remarks</span></span>

<span data-ttu-id="c6b58-109">默认值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="c6b58-109">The default value is zero (0).</span></span>

<span data-ttu-id="c6b58-110">对于已追加到集合中的 **Column** 对象， [NumericScale](column-object-adox.md) 为只读。</span><span class="sxs-lookup"><span data-stu-id="c6b58-110">**NumericScale** is read-only for [Column](column-object-adox.md) objects already appended to a collection.</span></span>

