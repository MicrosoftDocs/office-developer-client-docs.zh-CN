---
title: attSentFor
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aa8c8d64-d2a0-4cdf-a8aa-21c8d0a0a3fc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fd7f79ad7a36fd174bf9817ff463b00e6a334104
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774608"
---
# <a name="attsentfor"></a><span data-ttu-id="c9f73-103">attSentFor</span><span class="sxs-lookup"><span data-stu-id="c9f73-103">attSentFor</span></span>

  
  
<span data-ttu-id="c9f73-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c9f73-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c9f73-105">为盘点的字符串分布的端到端编码**attSentFor**属性。</span><span class="sxs-lookup"><span data-stu-id="c9f73-105">The **attSentFor** attribute is encoded as counted strings laid end-to-end.</span></span> <span data-ttu-id="c9f73-106">**AttSentFor**的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="c9f73-106">The format for **attSentFor** is as follows:</span></span> 
  
 <span data-ttu-id="c9f73-107">**attSentFor**:</span><span class="sxs-lookup"><span data-stu-id="c9f73-107">**attSentFor**:</span></span> 
  
> <span data-ttu-id="c9f73-108">显示名称长度显示名称地址长度_电子邮件地址_</span><span class="sxs-lookup"><span data-stu-id="c9f73-108">display-name-length display-name address-length  _email-address_</span></span>
    
 <span data-ttu-id="c9f73-109">_电子邮件地址_</span><span class="sxs-lookup"><span data-stu-id="c9f73-109">_email-address_</span></span>
  
> <span data-ttu-id="c9f73-110">类型： **:** 地址</span><span class="sxs-lookup"><span data-stu-id="c9f73-110">type **:** address</span></span> 
    
<span data-ttu-id="c9f73-111">与其他长度不同值、 显示名称长度和地址长度是无符号的 16 位值，而不是无符号的长整数。</span><span class="sxs-lookup"><span data-stu-id="c9f73-111">Unlike other length values, the display-name-length and address-length are unsigned 16-bit values instead of unsigned long integers.</span></span> <span data-ttu-id="c9f73-112">它们仍包括但是终止 null 字符。</span><span class="sxs-lookup"><span data-stu-id="c9f73-112">They still include terminating null characters, however.</span></span> <span data-ttu-id="c9f73-113">使用原义冒号 （:） 字符，例如"smtp:joe@nowhere.com"分隔中的_电子邮件地址_条目的类型和地址字符串。</span><span class="sxs-lookup"><span data-stu-id="c9f73-113">The type and address strings in the  _email-address_ entry are separated by a literal colon (:) character, such as "smtp:joe@nowhere.com".</span></span> <span data-ttu-id="c9f73-114">合并的类型： **:** 的地址字符串以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="c9f73-114">Only the combined type **:** address string is null-terminated.</span></span>
  

