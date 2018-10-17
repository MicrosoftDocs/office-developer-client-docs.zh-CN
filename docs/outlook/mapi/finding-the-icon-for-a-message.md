---
title: 查找邮件的图标
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 80a97c3d-4bca-4819-9da4-ca0fbf3a686f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 512c686a9e5afeadacd8edccedba2c257df48f71
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567809"
---
# <a name="finding-the-icon-for-a-message"></a><span data-ttu-id="d3af6-103">查找邮件的图标</span><span class="sxs-lookup"><span data-stu-id="d3af6-103">Finding the Icon for a Message</span></span>

  
  
<span data-ttu-id="d3af6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3af6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="d3af6-105">**若要查找与消息关联的图标**</span><span class="sxs-lookup"><span data-stu-id="d3af6-105">**To find the icon associated with a message**</span></span>
  
1. <span data-ttu-id="d3af6-106">调用消息的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d3af6-106">Call the message's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.</span></span>
    
2. <span data-ttu-id="d3af6-107">调用[MAPIOpenFormMgr](mapiopenformmgr.md)检索**IMAPIFormMgr**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="d3af6-107">Call [MAPIOpenFormMgr](mapiopenformmgr.md) to retrieve an **IMAPIFormMgr** interface pointer.</span></span> <span data-ttu-id="d3af6-108">_PSession_参数中传递**IMAPISession**指针。</span><span class="sxs-lookup"><span data-stu-id="d3af6-108">Pass your **IMAPISession** pointer in the  _pSession_ parameter.</span></span> 
    
3. <span data-ttu-id="d3af6-109">调用[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)检索**IMAPIFormInfo**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="d3af6-109">Call [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) to retrieve an **IMAPIFormInfo** interface pointer.</span></span> 
    
4. <span data-ttu-id="d3af6-110">使用**IMAPIFormInfo**指针调用[IMAPIProp::GetProps](imapiprop-getprops.md)和检索**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 和/或**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d3af6-110">Use the **IMAPIFormInfo** pointer to call [IMAPIProp::GetProps](imapiprop-getprops.md) and retrieve the **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) and/or **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) properties.</span></span> 
    
