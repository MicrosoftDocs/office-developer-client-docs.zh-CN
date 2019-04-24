---
title: 查找邮件的图标
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 80a97c3d-4bca-4819-9da4-ca0fbf3a686f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b351cc68e3c3d9f9c01acb4b3d0e52158e302d7a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336951"
---
# <a name="finding-the-icon-for-a-message"></a><span data-ttu-id="b9083-103">查找邮件的图标</span><span class="sxs-lookup"><span data-stu-id="b9083-103">Finding the Icon for a Message</span></span>

  
  
<span data-ttu-id="b9083-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9083-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="b9083-105">**查找与邮件关联的图标**</span><span class="sxs-lookup"><span data-stu-id="b9083-105">**To find the icon associated with a message**</span></span>
  
1. <span data-ttu-id="b9083-106">调用邮件的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b9083-106">Call the message's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property.</span></span>
    
2. <span data-ttu-id="b9083-107">调用[MAPIOpenFormMgr](mapiopenformmgr.md)以检索**IMAPIFormMgr**接口指针。</span><span class="sxs-lookup"><span data-stu-id="b9083-107">Call [MAPIOpenFormMgr](mapiopenformmgr.md) to retrieve an **IMAPIFormMgr** interface pointer.</span></span> <span data-ttu-id="b9083-108">在_pSession_参数中传递**IMAPISession**指针。</span><span class="sxs-lookup"><span data-stu-id="b9083-108">Pass your **IMAPISession** pointer in the  _pSession_ parameter.</span></span> 
    
3. <span data-ttu-id="b9083-109">调用[IMAPIFormMgr:: ResolveMessageClass](imapiformmgr-resolvemessageclass.md)以检索**IMAPIFormInfo**接口指针。</span><span class="sxs-lookup"><span data-stu-id="b9083-109">Call [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) to retrieve an **IMAPIFormInfo** interface pointer.</span></span> 
    
4. <span data-ttu-id="b9083-110">使用**IMAPIFormInfo**指针调用[IMAPIProp:: GetProps](imapiprop-getprops.md)并检索**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 和/或**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b9083-110">Use the **IMAPIFormInfo** pointer to call [IMAPIProp::GetProps](imapiprop-getprops.md) and retrieve the **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) and/or **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) properties.</span></span> 
    

