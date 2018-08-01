---
title: 展开通讯组列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 44231a95-dafc-44f7-bfa9-9f73ea8cb8b7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 47a37683ac54bef72ebd50aaaa11a36bdfd28659
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774894"
---
# <a name="expanding-distribution-lists"></a><span data-ttu-id="2fb1e-103">展开通讯组列表</span><span class="sxs-lookup"><span data-stu-id="2fb1e-103">Expanding Distribution Lists</span></span>

  
  
<span data-ttu-id="2fb1e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2fb1e-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="2fb1e-105">**提示 MAPI 以展开通讯组列表**</span><span class="sxs-lookup"><span data-stu-id="2fb1e-105">**To prompt MAPI to expand a distribution list**</span></span>
  
- <span data-ttu-id="2fb1e-106">设置为 MAPIPDL 其**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2fb1e-106">Set its **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property to MAPIPDL.</span></span>
    
    <span data-ttu-id="2fb1e-107">MAPI 将消息发送到传输提供程序之前展开与此类型的地址。</span><span class="sxs-lookup"><span data-stu-id="2fb1e-107">MAPI expands addresses with this type before sending the message to the transport provider.</span></span>
    

