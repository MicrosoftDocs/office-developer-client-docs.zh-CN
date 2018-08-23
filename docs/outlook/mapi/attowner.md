---
title: attOwner
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3c6a4050-fd97-42ce-abb1-118254b367bd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 865d929f3348710b7786f4182670f3304a3a9244
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578036"
---
# <a name="attowner"></a><span data-ttu-id="b2afe-103">attOwner</span><span class="sxs-lookup"><span data-stu-id="b2afe-103">attOwner</span></span>

  
  
<span data-ttu-id="b2afe-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b2afe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b2afe-105">为盘点的字符串分布的端到端编码**attOwner**属性。</span><span class="sxs-lookup"><span data-stu-id="b2afe-105">The **attOwner** attribute is encoded as counted strings laid end-to-end.</span></span> <span data-ttu-id="b2afe-106">**AttOwner**的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2afe-106">The format for **attOwner** is as follows:</span></span> 
  
 <span data-ttu-id="b2afe-107">**attOwner**:</span><span class="sxs-lookup"><span data-stu-id="b2afe-107">**attOwner**:</span></span> 
  
> <span data-ttu-id="b2afe-108">显示名称长度显示名称地址长度_电子邮件地址_</span><span class="sxs-lookup"><span data-stu-id="b2afe-108">display-name-length display-name address-length  _email-address_</span></span>
    
 <span data-ttu-id="b2afe-109">_电子邮件地址_</span><span class="sxs-lookup"><span data-stu-id="b2afe-109">_email-address_</span></span>
  
> <span data-ttu-id="b2afe-110">类型： **:** 地址</span><span class="sxs-lookup"><span data-stu-id="b2afe-110">type **:** address</span></span> 
    
<span data-ttu-id="b2afe-111">与其他长度不同值、 显示名称长度和地址长度是无符号的 16 位值，而不是无符号的长整数。</span><span class="sxs-lookup"><span data-stu-id="b2afe-111">Unlike other length values, the display-name-length and address-length are unsigned 16-bit values instead of unsigned long integers.</span></span> <span data-ttu-id="b2afe-112">它们仍包括但是终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="b2afe-112">They still include terminating null characters, however.</span></span> <span data-ttu-id="b2afe-113">使用原义冒号 （:） 字符，例如"smtp:joe@nowhere.com"分隔中的_电子邮件地址_条目的类型和地址字符串。</span><span class="sxs-lookup"><span data-stu-id="b2afe-113">The type and address strings in the  _email-address_ entry are separated by a literal colon (:) character, such as "smtp:joe@nowhere.com".</span></span> <span data-ttu-id="b2afe-114">合并的类型： **:** 的地址字符串以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="b2afe-114">Only the combined type **:** address string is null-terminated.</span></span>
  
<span data-ttu-id="b2afe-115">取决于要编码的邮件的邮件类**attOwner**属性相对应的 MAPI 属性的映射。</span><span class="sxs-lookup"><span data-stu-id="b2afe-115">The mapping of MAPI properties to the **attOwner** attribute is dependent on the message class of the message being encoded.</span></span> 
  

