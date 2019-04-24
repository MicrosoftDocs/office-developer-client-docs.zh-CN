---
title: LineSeparator 属性 (ADO)
TOCTitle: LineSeparator property (ADO)
ms:assetid: 9f1323cd-d4ed-2bfa-554b-faebab529548
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249729(v=office.15)
ms:contentKeyID: 48546676
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4e941339ad1c8622d1c87ada848a44fa82a9ef2d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289947"
---
# <a name="lineseparator-property-ado"></a><span data-ttu-id="13227-102">LineSeparator 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="13227-102">LineSeparator property (ADO)</span></span>


<span data-ttu-id="13227-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="13227-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="13227-104">指示要在文本 [Stream](stream-object-ado.md) 对象中用作行分隔符的二进制字符。</span><span class="sxs-lookup"><span data-stu-id="13227-104">Indicates the binary character to be used as the line separator in text [Stream](stream-object-ado.md) objects.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="13227-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="13227-105">Settings and return values</span></span>

<span data-ttu-id="13227-106">设置或返回一个 [LineSeparatorsEnum](lineseparatorsenum.md) 值，指示在 **Stream** 中使用的分行符。</span><span class="sxs-lookup"><span data-stu-id="13227-106">Sets or returns a [LineSeparatorsEnum](lineseparatorsenum.md) value that indicates the line separator character used in the **Stream**.</span></span> <span data-ttu-id="13227-107">默认值为 **adCRLF**。</span><span class="sxs-lookup"><span data-stu-id="13227-107">The default value is **adCRLF**.</span></span>

## <a name="remarks"></a><span data-ttu-id="13227-108">注解</span><span class="sxs-lookup"><span data-stu-id="13227-108">Remarks</span></span>

<span data-ttu-id="13227-p102">**LineSeparator** 用于在读取文本 **Stream** 的内容时解释行。可通过 [SkipLine](skipline-method-ado.md) 方法进行跳行。</span><span class="sxs-lookup"><span data-stu-id="13227-p102">**LineSeparator** is used to interpret lines when reading the content of a text **Stream**. Lines can be skipped with the [SkipLine](skipline-method-ado.md) method.</span></span>

<span data-ttu-id="13227-111">**LineSeparator** 仅用于文本 **Stream** 对象（[Type](type-property-ado-stream.md) 为 **adTypeText**）。</span><span class="sxs-lookup"><span data-stu-id="13227-111">**LineSeparator** is used only with text **Stream** objects ([Type](type-property-ado-stream.md) is **adTypeText**).</span></span> <span data-ttu-id="13227-112">如果 **Type** 为 **adTypeBinary**，则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="13227-112">This property is ignored if **Type** is **adTypeBinary**.</span></span>

