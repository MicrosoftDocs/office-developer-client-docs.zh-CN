---
title: LineSeparator 属性 (ADO)
TOCTitle: LineSeparator property (ADO)
ms:assetid: 9f1323cd-d4ed-2bfa-554b-faebab529548
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249729(v=office.15)
ms:contentKeyID: 48546676
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 831b6377ade43b3be04ed21add20fbd10e48ac2f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882502"
---
# <a name="lineseparator-property-ado"></a><span data-ttu-id="e22e9-102">LineSeparator 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e22e9-102">LineSeparator property (ADO)</span></span>


<span data-ttu-id="e22e9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e22e9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e22e9-104">指示要在文本 [Stream](stream-object-ado.md) 对象中用作行分隔符的二进制字符。</span><span class="sxs-lookup"><span data-stu-id="e22e9-104">Indicates the binary character to be used as the line separator in text [Stream](stream-object-ado.md) objects.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="e22e9-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="e22e9-105">Settings and return values</span></span>

<span data-ttu-id="e22e9-p101">设置或返回一个 [LineSeparatorsEnum](lineseparatorsenum.md) 值，指示在 **Stream** 中使用的分行符。默认值为 **adCRLF** 。</span><span class="sxs-lookup"><span data-stu-id="e22e9-p101">Sets or returns a [LineSeparatorsEnum](lineseparatorsenum.md) value that indicates the line separator character used in the **Stream**. The default value is **adCRLF**.</span></span>

## <a name="remarks"></a><span data-ttu-id="e22e9-108">备注</span><span class="sxs-lookup"><span data-stu-id="e22e9-108">Remarks</span></span>

<span data-ttu-id="e22e9-p102">**LineSeparator** 用于在读取文本 **Stream** 的内容时解释行。可通过 [SkipLine](skipline-method-ado.md) 方法进行跳行。</span><span class="sxs-lookup"><span data-stu-id="e22e9-p102">**LineSeparator** is used to interpret lines when reading the content of a text **Stream**. Lines can be skipped with the [SkipLine](skipline-method-ado.md) method.</span></span>

<span data-ttu-id="e22e9-p103">**LineSeparator** 仅用于文本 **Stream** 对象（[Type](type-property-ado-stream.md) 为 **adTypeText**）。如果 **Type** 为 **adTypeBinary**，则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="e22e9-p103">**LineSeparator** is used only with text **Stream** objects ([Type](type-property-ado-stream.md) is **adTypeText**). This property is ignored if **Type** is **adTypeBinary**.</span></span>

