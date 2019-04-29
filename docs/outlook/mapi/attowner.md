---
title: attOwner
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3c6a4050-fd97-42ce-abb1-118254b367bd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 17e900ac28481388379133a95b4b206ca4bc1805
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427652"
---
# <a name="attowner"></a><span data-ttu-id="f6ad9-103">attOwner</span><span class="sxs-lookup"><span data-stu-id="f6ad9-103">attOwner</span></span>

  
  
<span data-ttu-id="f6ad9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f6ad9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f6ad9-105">**attOwner**属性被编码为端到端布局的计数字符串。</span><span class="sxs-lookup"><span data-stu-id="f6ad9-105">The **attOwner** attribute is encoded as counted strings laid end-to-end.</span></span> <span data-ttu-id="f6ad9-106">**attOwner**的格式如下所示:</span><span class="sxs-lookup"><span data-stu-id="f6ad9-106">The format for **attOwner** is as follows:</span></span> 
  
 <span data-ttu-id="f6ad9-107">**attOwner**:</span><span class="sxs-lookup"><span data-stu-id="f6ad9-107">**attOwner**:</span></span> 
  
> <span data-ttu-id="f6ad9-108">显示-名称-长度显示名称地址-长度_电子邮件地址_</span><span class="sxs-lookup"><span data-stu-id="f6ad9-108">display-name-length display-name address-length  _email-address_</span></span>
    
 <span data-ttu-id="f6ad9-109">_电子邮件地址_</span><span class="sxs-lookup"><span data-stu-id="f6ad9-109">_email-address_</span></span>
  
> <span data-ttu-id="f6ad9-110">类型 **:** address</span><span class="sxs-lookup"><span data-stu-id="f6ad9-110">type **:** address</span></span> 
    
<span data-ttu-id="f6ad9-111">与其他长度值不同, 显示名称-长度和地址长度是无符号的16位值, 而不是无符号长整数。</span><span class="sxs-lookup"><span data-stu-id="f6ad9-111">Unlike other length values, the display-name-length and address-length are unsigned 16-bit values instead of unsigned long integers.</span></span> <span data-ttu-id="f6ad9-112">但是, 它们仍包括终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="f6ad9-112">They still include terminating null characters, however.</span></span> <span data-ttu-id="f6ad9-113">_电子邮件地址_条目中的类型和地址字符串之间用文字冒号 (:)字符, 如 "smtp:joe@nowhere.com"。</span><span class="sxs-lookup"><span data-stu-id="f6ad9-113">The type and address strings in the  _email-address_ entry are separated by a literal colon (:) character, such as "smtp:joe@nowhere.com".</span></span> <span data-ttu-id="f6ad9-114">仅组合类型 **:** 地址字符串以空值终止。</span><span class="sxs-lookup"><span data-stu-id="f6ad9-114">Only the combined type **:** address string is null-terminated.</span></span>
  
<span data-ttu-id="f6ad9-115">MAPI 属性到**attOwner**属性的映射取决于正在编码的邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="f6ad9-115">The mapping of MAPI properties to the **attOwner** attribute is dependent on the message class of the message being encoded.</span></span> 
  

