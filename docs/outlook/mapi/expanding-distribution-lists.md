---
title: 展开通讯组列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 44231a95-dafc-44f7-bfa9-9f73ea8cb8b7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5731a35b5d570669d8606be6dd6ca1a23fb87e88
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414135"
---
# <a name="expanding-distribution-lists"></a><span data-ttu-id="3fc72-103">展开通讯组列表</span><span class="sxs-lookup"><span data-stu-id="3fc72-103">Expanding Distribution Lists</span></span>

  
  
<span data-ttu-id="3fc72-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3fc72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="3fc72-105">**提示 MAPI 展开通讯组列表**</span><span class="sxs-lookup"><span data-stu-id="3fc72-105">**To prompt MAPI to expand a distribution list**</span></span>
  
- <span data-ttu-id="3fc72-106">将其**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性设置为 MAPIPDL。</span><span class="sxs-lookup"><span data-stu-id="3fc72-106">Set its **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) property to MAPIPDL.</span></span>
    
    <span data-ttu-id="3fc72-107">MAPI 在将邮件发送到传输提供程序之前, 使用此类型展开地址。</span><span class="sxs-lookup"><span data-stu-id="3fc72-107">MAPI expands addresses with this type before sending the message to the transport provider.</span></span>
    

