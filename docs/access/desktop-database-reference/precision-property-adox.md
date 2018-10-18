---
title: Precision 属性 (ADOX)
TOCTitle: Precision Property (ADOX)
ms:assetid: 5d8ca497-572a-52e0-18aa-f82deaea0813
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249330(v=office.15)
ms:contentKeyID: 48545117
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 77b1083cd9625ded4360311ce9cd0a6d557a3698
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606526"
---
# <a name="precision-property-adox"></a><span data-ttu-id="495ad-102">Precision 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="495ad-102">Precision Property (ADOX)</span></span>


<span data-ttu-id="495ad-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="495ad-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="495ad-104">指示列中的数据值的最大精度。</span><span class="sxs-lookup"><span data-stu-id="495ad-104">Indicates the maximum precision of data values in the column.</span></span>

<span data-ttu-id="495ad-105"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="495ad-105"><<<<<<< HEAD</span></span>
## <a name="settings-and-return-values"></a><span data-ttu-id="495ad-106">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="495ad-106">Settings and Return Values</span></span>
=======
## <a name="settings-and-return-values"></a><span data-ttu-id="495ad-107">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="495ad-107">Settings and return values</span></span>
>>>>>>> <span data-ttu-id="495ad-108">master</span><span class="sxs-lookup"><span data-stu-id="495ad-108">master</span></span>

<span data-ttu-id="495ad-p101">设置和返回一个 **Long** 值，该值为当列的 [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) 属性为数值类型时数据值的最大精度。对于所有其他数据类型将忽略 **Precision** 。</span><span class="sxs-lookup"><span data-stu-id="495ad-p101">Sets and returns a **Long** value that is the maximum precision of data values in the column when the [Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\)) property is a numeric type. **Precision** is ignored for all other data types.</span></span>

## <a name="remarks"></a><span data-ttu-id="495ad-111">备注</span><span class="sxs-lookup"><span data-stu-id="495ad-111">Remarks</span></span>

<span data-ttu-id="495ad-112">默认值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="495ad-112">The default value is zero (0).</span></span>

<span data-ttu-id="495ad-113">对于已追加到集合中的 [Column](column-object-adox.md) 对象，此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="495ad-113">This property is read-only for [Column](column-object-adox.md) objects already appended to a collection.</span></span>

