---
title: attFrom
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2d405268-bb33-4863-be38-2d17e8fc956e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 496bd5439b9f004d3b13d2d73b31b5cac3f9eec9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432413"
---
# <a name="attfrom"></a><span data-ttu-id="ff50e-103">attFrom</span><span class="sxs-lookup"><span data-stu-id="ff50e-103">attFrom</span></span>

<span data-ttu-id="ff50e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff50e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff50e-105">**attFrom** 属性编码为 **TRP** 结构，该结构对发件人的 显示名称 和电子邮件地址进行编码，后跟发件人的 显示名称 和地址，然后是任何必要的填充。</span><span class="sxs-lookup"><span data-stu-id="ff50e-105">The **attFrom** attribute is encoded as a **TRP** structure which encodes the display name and email address of the sender, followed by the display name and address of the sender, followed by any necessary padding.</span></span> <span data-ttu-id="ff50e-106">**attFrom 的格式** 如下所示：</span><span class="sxs-lookup"><span data-stu-id="ff50e-106">The format for **attFrom** is as follows:</span></span> 
  
<span data-ttu-id="ff50e-107">**attFrom**： _TRP-structure_ sender-display-name _ sender-address _ padding</span><span class="sxs-lookup"><span data-stu-id="ff50e-107">**attFrom**: _TRP-structure_ sender-display-name  _ sender-address _ padding</span></span> 
    
<span data-ttu-id="ff50e-108">sender-display-name 是一个以 null 结尾的字符串，如有必要，该字符串会填充一个额外的 null 字符，以达到 2 字节的边界。</span><span class="sxs-lookup"><span data-stu-id="ff50e-108">The sender-display-name is a null-terminated string that is padded with an additional null character, if necessary, to reach a 2-byte boundary.</span></span> <span data-ttu-id="ff50e-109">**attFrom** 编码末尾的填充由达到 **TRP** 边界大小所需的 (null) 组成。</span><span class="sxs-lookup"><span data-stu-id="ff50e-109">The padding at the end of the **attFrom** encoding consists of as many null characters as needed to reach a **sizeof(TRP)** boundary.</span></span> 
  
<span data-ttu-id="ff50e-110">_TRP-structure：trpidOneOff_  cbgrtrp cch cb</span><span class="sxs-lookup"><span data-stu-id="ff50e-110">_TRP-structure:_ **trpidOneOff** cbgrtrp cch cb</span></span> 
    
<span data-ttu-id="ff50e-111">对于 **attFrom** 项 **，TRP**-structure 始终是一次一次编码，因此 **TRP**-structure 字段的 trpid 始终为 **trpidOneOff**。</span><span class="sxs-lookup"><span data-stu-id="ff50e-111">For the **attFrom** item, the **TRP**-structure is always a one-off encoding, so the trpid off the **TRP**-structure field is always **trpidOneOff**.</span></span> <span data-ttu-id="ff50e-112">cbgrtrp、cch 和 cb 项对应于 **TRP** 结构的其余字段。</span><span class="sxs-lookup"><span data-stu-id="ff50e-112">The cbgrtrp, cch, and cb items correspond to the remaining fields of the **TRP** structure.</span></span> 
  
<span data-ttu-id="ff50e-113">cbgrtrp 字段的计算公式为 (**sizeof (TRP) \* 2) 、** 以 null 终止的 sender-display-name 的长度及其填充以及以 null 终止的发件人地址的长度。</span><span class="sxs-lookup"><span data-stu-id="ff50e-113">The cbgrtrp field is calculated as the sum of **(sizeof(TRP) \*2)**, the length of the null-terminated sender-display-name with its padding, and the length of the null-terminated sender-address.</span></span>
  
<span data-ttu-id="ff50e-114">cch 字段的计算公式为具有填充的以 null 终止的显示名称的长度。</span><span class="sxs-lookup"><span data-stu-id="ff50e-114">The cch field is calculated as the length of the null-terminated display-name with its padding.</span></span>
  
<span data-ttu-id="ff50e-115">cb 字段的计算公式为以 null 终止的发件人地址的长度。</span><span class="sxs-lookup"><span data-stu-id="ff50e-115">The cb field is calculated as the length of the null-terminated sender-address.</span></span>
  
<span data-ttu-id="ff50e-116">_sender-address：_ address-type **：** address **'\0'**</span><span class="sxs-lookup"><span data-stu-id="ff50e-116">_sender-address:_ address-type **:** address **'\0'**</span></span>
    
<span data-ttu-id="ff50e-117">发件人地址是一个字符串，由四个部分组成：地址类型、文本冒号 (：) 、地址本身和终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="ff50e-117">The sender-address is a string that is composed of four parts, the address-type, a literal colon (:), the address itself, and a terminating null character.</span></span> <span data-ttu-id="ff50e-118">例如，字符串 `fax:1-909-555-1234\0` 将是合法发件人地址值。</span><span class="sxs-lookup"><span data-stu-id="ff50e-118">For example, the string `fax:1-909-555-1234\0` would be a legal sender-address value.</span></span>
  

