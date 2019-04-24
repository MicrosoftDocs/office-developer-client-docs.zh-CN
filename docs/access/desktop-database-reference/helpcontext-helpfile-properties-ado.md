---
title: HelpContext、帮助帮助属性 (ADO)
TOCTitle: HelpContext, HelpFile properties (ADO)
ms:assetid: 8a79f994-f17c-2983-0593-095801be762e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249608(v=office.15)
ms:contentKeyID: 48546194
ms.date: 10/17/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c90fee6b8525ab13c8a294f9b39c52c20f580a62
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291990"
---
# <a name="helpcontext-helpfile-properties-ado"></a><span data-ttu-id="63d80-102">HelpContext、帮助帮助属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="63d80-102">HelpContext, HelpFile properties (ADO)</span></span>

<span data-ttu-id="63d80-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="63d80-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="63d80-104">指示与 [Error](error-object-ado.md) 对象关联的帮助文件和主题。</span><span class="sxs-lookup"><span data-stu-id="63d80-104">Indicates the help file and topic associated with an [Error](error-object-ado.md) object.</span></span>

## <a name="return-values"></a><span data-ttu-id="63d80-105">返回值</span><span class="sxs-lookup"><span data-stu-id="63d80-105">Return values</span></span>

- <span data-ttu-id="63d80-106">**HelpContextID**  返回帮助文件中主题的上下文 ID，返回值的类型为 **Long** 。</span><span class="sxs-lookup"><span data-stu-id="63d80-106">**HelpContextID** — returns a context ID, as a **Long** value, for a topic in a Help file.</span></span>

- <span data-ttu-id="63d80-107">**HelpFile**  — 返回一个 **String** 类型的值，作为帮助文件完全解析路径的计算结果。</span><span class="sxs-lookup"><span data-stu-id="63d80-107">**HelpFile** — returns a **String** value that evaluates to a fully resolved path to a Help file.</span></span>

## <a name="remarks"></a><span data-ttu-id="63d80-108">注解</span><span class="sxs-lookup"><span data-stu-id="63d80-108">Remarks</span></span>

<span data-ttu-id="63d80-p101">如果在 **HelpFile** 属性中指定了帮助文件，则 **HelpContext** 属性用于自动显示其标识的帮助主题。如果没有相关的帮助主题可用，则 **HelpContext** 属性返回 0，并且 **HelpFile** 属性返回一个零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="63d80-p101">If a Help file is specified in the **HelpFile** property, the **HelpContext** property is used to automatically display the Help topic it identifies. If there is no relevant help topic available, the **HelpContext** property returns zero and the **HelpFile** property returns a zero-length string ("").</span></span>

