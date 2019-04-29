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
# <a name="attfrom"></a><span data-ttu-id="cca78-103">attFrom</span><span class="sxs-lookup"><span data-stu-id="cca78-103">attFrom</span></span>

<span data-ttu-id="cca78-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cca78-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cca78-105">**attFrom**属性被编码为**TRP**结构, 该结构对发件人的显示名称和电子邮件地址进行编码, 后跟发件人的显示名称和地址, 后跟任何必需的填充。</span><span class="sxs-lookup"><span data-stu-id="cca78-105">The **attFrom** attribute is encoded as a **TRP** structure which encodes the display name and email address of the sender, followed by the display name and address of the sender, followed by any necessary padding.</span></span> <span data-ttu-id="cca78-106">**attFrom**的格式如下所示:</span><span class="sxs-lookup"><span data-stu-id="cca78-106">The format for **attFrom** is as follows:</span></span> 
  
<span data-ttu-id="cca78-107">**attFrom**: _TRP-结构_发件人-显示名称 _ 发件人-地址 _ 填充</span><span class="sxs-lookup"><span data-stu-id="cca78-107">**attFrom**: _TRP-structure_ sender-display-name  _ sender-address _ padding</span></span> 
    
<span data-ttu-id="cca78-108">发件人-显示名称是以 null 结尾的字符串, 如果需要, 使用额外的 null 字符填充, 以达到2字节边界。</span><span class="sxs-lookup"><span data-stu-id="cca78-108">The sender-display-name is a null-terminated string that is padded with an additional null character, if necessary, to reach a 2-byte boundary.</span></span> <span data-ttu-id="cca78-109">**attFrom**编码结尾的边距由所需的任意多个 null 字符组成, 以达到**sizeof (TRP)** 边界。</span><span class="sxs-lookup"><span data-stu-id="cca78-109">The padding at the end of the **attFrom** encoding consists of as many null characters as needed to reach a **sizeof(TRP)** boundary.</span></span> 
  
<span data-ttu-id="cca78-110">_TRP:_**trpidOneOff** cbgrtrp cch cb</span><span class="sxs-lookup"><span data-stu-id="cca78-110">_TRP-structure:_ **trpidOneOff** cbgrtrp cch cb</span></span> 
    
<span data-ttu-id="cca78-111">对于**attFrom**项, **TRP**始终是一次性编码, 因此**TRP**结构字段的 trpid 始终为**trpidOneOff**。</span><span class="sxs-lookup"><span data-stu-id="cca78-111">For the **attFrom** item, the **TRP**-structure is always a one-off encoding, so the trpid off the **TRP**-structure field is always **trpidOneOff**.</span></span> <span data-ttu-id="cca78-112">cbgrtrp、cch 和 cb 项目对应于**TRP**结构的其余字段。</span><span class="sxs-lookup"><span data-stu-id="cca78-112">The cbgrtrp, cch, and cb items correspond to the remaining fields of the **TRP** structure.</span></span> 
  
<span data-ttu-id="cca78-113">cbgrtrp 字段的计算公式为 **(sizeof (TRP \*) 2)**、以 null 结尾的发件人的显示名称的填充长度以及以 null 结尾的发件人地址的长度。</span><span class="sxs-lookup"><span data-stu-id="cca78-113">The cbgrtrp field is calculated as the sum of **(sizeof(TRP) \*2)**, the length of the null-terminated sender-display-name with its padding, and the length of the null-terminated sender-address.</span></span>
  
<span data-ttu-id="cca78-114">cch 字段是以以 null 结尾的显示名称的长度作为填充的长度计算的。</span><span class="sxs-lookup"><span data-stu-id="cca78-114">The cch field is calculated as the length of the null-terminated display-name with its padding.</span></span>
  
<span data-ttu-id="cca78-115">cb 字段作为以空值终止的发件人地址的长度计算。</span><span class="sxs-lookup"><span data-stu-id="cca78-115">The cb field is calculated as the length of the null-terminated sender-address.</span></span>
  
<span data-ttu-id="cca78-116">_发件人-地址:_ 地址-类型 **:** 地址 **"\ 0"**</span><span class="sxs-lookup"><span data-stu-id="cca78-116">_sender-address:_ address-type **:** address **'\0'**</span></span>
    
<span data-ttu-id="cca78-117">发件人地址是一个字符串, 由四部分组成: 地址类型、文本冒号 (:)、地址本身以及终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="cca78-117">The sender-address is a string that is composed of four parts, the address-type, a literal colon (:), the address itself, and a terminating null character.</span></span> <span data-ttu-id="cca78-118">例如, 字符串`fax:1-909-555-1234\0`将是合法的发件人地址值。</span><span class="sxs-lookup"><span data-stu-id="cca78-118">For example, the string `fax:1-909-555-1234\0` would be a legal sender-address value.</span></span>
  

