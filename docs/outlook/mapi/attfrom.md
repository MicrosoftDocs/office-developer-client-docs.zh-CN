---
title: attFrom
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2d405268-bb33-4863-be38-2d17e8fc956e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c7c0d1df32a0ad6359fad20128a6a1e3dd225143
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774594"
---
# <a name="attfrom"></a><span data-ttu-id="8f303-103">attFrom</span><span class="sxs-lookup"><span data-stu-id="8f303-103">attFrom</span></span>

<span data-ttu-id="8f303-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8f303-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8f303-105">**AttFrom**属性被编码为**TRP**结构，它将编码的发件人后, 跟的显示名称和发件人后, 跟任何必要的填充的地址的显示名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8f303-105">The **attFrom** attribute is encoded as a **TRP** structure which encodes the display name and email address of the sender, followed by the display name and address of the sender, followed by any necessary padding.</span></span> <span data-ttu-id="8f303-106">**AttFrom**的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f303-106">The format for **attFrom** is as follows:</span></span> 
  
<span data-ttu-id="8f303-107">**attFrom**: _TRP 结构_发件人显示名称 _ 发件人地址 _ 边距</span><span class="sxs-lookup"><span data-stu-id="8f303-107">**attFrom**: _TRP-structure_ sender-display-name  _ sender-address _ padding</span></span> 
    
<span data-ttu-id="8f303-108">发件人显示名称是以 null 结尾的字符串填充了其他空字符，如有必要，以到达 2 字节边界。</span><span class="sxs-lookup"><span data-stu-id="8f303-108">The sender-display-name is a null-terminated string that is padded with an additional null character, if necessary, to reach a 2-byte boundary.</span></span> <span data-ttu-id="8f303-109">**AttFrom**编码的末尾的空白包含尽可能多的 null 字符，根据需要到达**sizeof(TRP)** 边界。</span><span class="sxs-lookup"><span data-stu-id="8f303-109">The padding at the end of the **attFrom** encoding consists of as many null characters as needed to reach a **sizeof(TRP)** boundary.</span></span> 
  
<span data-ttu-id="8f303-110">_TRP 结构：_**trpidOneOff** cbgrtrp cch cb</span><span class="sxs-lookup"><span data-stu-id="8f303-110">_TRP-structure:_ **trpidOneOff** cbgrtrp cch cb</span></span> 
    
<span data-ttu-id="8f303-111">对于**attFrom**项， **TRP**-结构是始终一次性编码，因此关闭**TRP**trpid-结构字段总是**trpidOneOff**。</span><span class="sxs-lookup"><span data-stu-id="8f303-111">For the **attFrom** item, the **TRP**-structure is always a one-off encoding, so the trpid off the **TRP**-structure field is always **trpidOneOff**.</span></span> <span data-ttu-id="8f303-112">Cbgrtrp、 cch 和 cb 项目对应于**TRP**结构的剩余字段。</span><span class="sxs-lookup"><span data-stu-id="8f303-112">The cbgrtrp, cch, and cb items correspond to the remaining fields of the **TRP** structure.</span></span> 
  
<span data-ttu-id="8f303-113">Cbgrtrp 字段的计算公式为的总和 **(sizeof(TRP) \*2)**，名称的长度 null 结尾发件人-显示-具有其填充和 null 结尾发件人的地址的长度。</span><span class="sxs-lookup"><span data-stu-id="8f303-113">The cbgrtrp field is calculated as the sum of **(sizeof(TRP) \*2)**, the length of the null-terminated sender-display-name with its padding, and the length of the null-terminated sender-address.</span></span>
  
<span data-ttu-id="8f303-114">Cch 字段的计算公式为具有其填充 null 结尾显示名称的长度。</span><span class="sxs-lookup"><span data-stu-id="8f303-114">The cch field is calculated as the length of the null-terminated display-name with its padding.</span></span>
  
<span data-ttu-id="8f303-115">Cb 字段的计算公式为 null 结尾发件人的地址的长度。</span><span class="sxs-lookup"><span data-stu-id="8f303-115">The cb field is calculated as the length of the null-terminated sender-address.</span></span>
  
<span data-ttu-id="8f303-116">_发件人地址：_ 地址类型： **:** 地址**\0**</span><span class="sxs-lookup"><span data-stu-id="8f303-116">_sender-address:_ address-type **:** address **'\0'**</span></span>
    
<span data-ttu-id="8f303-117">发件人地址是一个字符串，其中包含四个部分、 地址类型、 文字冒号 （:）、 本身的地址和终止空字符。</span><span class="sxs-lookup"><span data-stu-id="8f303-117">The sender-address is a string that is composed of four parts, the address-type, a literal colon (:), the address itself, and a terminating null character.</span></span> <span data-ttu-id="8f303-118">例如，字符串`fax:1-909-555-1234\0`是一个合法发件人地址值。</span><span class="sxs-lookup"><span data-stu-id="8f303-118">For example, the string `fax:1-909-555-1234\0` would be a legal sender-address value.</span></span>
  

