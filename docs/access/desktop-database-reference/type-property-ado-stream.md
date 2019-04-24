---
title: Type 属性 (ADO Stream)
TOCTitle: Type Property (ADO Stream)
ms:assetid: 43872c74-51bf-47ae-6bdc-55d25b0dc84a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249203(v=office.15)
ms:contentKeyID: 48544505
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: bb4cebdb8b4aff1413ec60fe4ebb1e05931f6476
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306249"
---
# <a name="type-property-ado-stream"></a><span data-ttu-id="b56b2-102">Type 属性（ADO 流）</span><span class="sxs-lookup"><span data-stu-id="b56b2-102">Type property (ADO Stream)</span></span>


<span data-ttu-id="b56b2-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b56b2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b56b2-104">指示 [Stream](stream-object-ado.md) 中包含的数据类型（二进制或文本）。</span><span class="sxs-lookup"><span data-stu-id="b56b2-104">Indicates the type of data contained in the [Stream](stream-object-ado.md) (binary or text).</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="b56b2-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="b56b2-105">Settings and return values</span></span>

<span data-ttu-id="b56b2-p101">设置或返回一个 [StreamTypeEnum](streamtypeenum.md) 值，该值指定 **Stream** 对象中包含的数据类型。默认值是 **adTypeText**。但是，如果最初将二进制数据写入新的空 **Stream** 中，则 **Type** 将更改为 **adTypeBinary**。</span><span class="sxs-lookup"><span data-stu-id="b56b2-p101">Sets or returns a [StreamTypeEnum](streamtypeenum.md) value that specifies the type of data contained in the **Stream** object. The default value is **adTypeText**. However, if binary data is initially written to a new, empty **Stream**, the **Type** will be changed to **adTypeBinary**.</span></span>

## <a name="remarks"></a><span data-ttu-id="b56b2-109">注解</span><span class="sxs-lookup"><span data-stu-id="b56b2-109">Remarks</span></span>

<span data-ttu-id="b56b2-110">仅在当前位置在 **Stream** 的开始处（[Position](position-property-ado.md) 为 0）时，**Type** 属性才为可读/写属性，在任何其他位置时都为只读属性。</span><span class="sxs-lookup"><span data-stu-id="b56b2-110">The **Type** property is read/write only when the current position is at the beginning of the **Stream** ([Position](position-property-ado.md) is 0), and read-only at any other position.</span></span>

<span data-ttu-id="b56b2-p102">**Type** 属性确定对 **Stream** 执行读写操作时应使用的方法。对于文本 **Streams**，应使用 [ReadText](readtext-method-ado.md) 和 [WriteText](writetext-method-ado.md)。对于二进制 **Streams**，应使用 [Read](read-method-ado.md) 和 [Write](write-method-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="b56b2-p102">The **Type** property determines which methods should be used for reading and writing the **Stream**. For text **Streams**, use [ReadText](readtext-method-ado.md) and [WriteText](writetext-method-ado.md). For binary **Streams**, use [Read](read-method-ado.md) and [Write](write-method-ado.md).</span></span>

