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
# <a name="attowner"></a><span data-ttu-id="c6fc8-103">attOwner</span><span class="sxs-lookup"><span data-stu-id="c6fc8-103">attOwner</span></span>

  
  
<span data-ttu-id="c6fc8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c6fc8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c6fc8-105">**attOwner** 属性编码为倒数字符串，端到端布局。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-105">The **attOwner** attribute is encoded as counted strings laid end-to-end.</span></span> <span data-ttu-id="c6fc8-106">**attOwner** 的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6fc8-106">The format for **attOwner** is as follows:</span></span> 
  
 <span data-ttu-id="c6fc8-107">**attOwner**：</span><span class="sxs-lookup"><span data-stu-id="c6fc8-107">**attOwner**:</span></span> 
  
> <span data-ttu-id="c6fc8-108">display-name-length display-name address-length  _email-address_</span><span class="sxs-lookup"><span data-stu-id="c6fc8-108">display-name-length display-name address-length  _email-address_</span></span>
    
 <span data-ttu-id="c6fc8-109">_email-address_</span><span class="sxs-lookup"><span data-stu-id="c6fc8-109">_email-address_</span></span>
  
> <span data-ttu-id="c6fc8-110">type **：** address</span><span class="sxs-lookup"><span data-stu-id="c6fc8-110">type **:** address</span></span> 
    
<span data-ttu-id="c6fc8-111">与其他长度值不同，display-name-length 和 address-length 是无符号 16 位值，而不是无符号长整型。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-111">Unlike other length values, the display-name-length and address-length are unsigned 16-bit values instead of unsigned long integers.</span></span> <span data-ttu-id="c6fc8-112">但是，它们仍包括以 null 字符结束。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-112">They still include terminating null characters, however.</span></span> <span data-ttu-id="c6fc8-113">电子邮件地址条目中的类型和地址字符串由文本冒号 (：) 字符分隔，如"smtp:joe@nowhere.com"。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-113">The type and address strings in the  _email-address_ entry are separated by a literal colon (:) character, such as "smtp:joe@nowhere.com".</span></span> <span data-ttu-id="c6fc8-114">只有组合类型 **：** 地址字符串以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-114">Only the combined type **:** address string is null-terminated.</span></span>
  
<span data-ttu-id="c6fc8-115">MAPI 属性到 **attOwner** 属性的映射取决于要编码的邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="c6fc8-115">The mapping of MAPI properties to the **attOwner** attribute is dependent on the message class of the message being encoded.</span></span> 
  

