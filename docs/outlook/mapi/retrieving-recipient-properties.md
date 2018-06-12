---
title: 检索收件人属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 358f892b-54a7-4213-b3c0-94f28f99716f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a7bdcf133b8b2b5d8eb906cc0f5b5803838e27a3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778631"
---
# <a name="retrieving-recipient-properties"></a><span data-ttu-id="a687a-103">检索收件人属性</span><span class="sxs-lookup"><span data-stu-id="a687a-103">Retrieving recipient properties</span></span>
  
<span data-ttu-id="a687a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a687a-104">**Applies to**: Outlook</span></span> 
  
### <a name="to-access-one-or-more-properties-of-an-address-book-entry"></a><span data-ttu-id="a687a-105">若要访问的通讯簿条目的一个或多个属性</span><span class="sxs-lookup"><span data-stu-id="a687a-105">To access one or more properties of an address book entry</span></span>
  
1. <span data-ttu-id="a687a-106">感兴趣的每个通讯簿条目，调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)，传递的目标邮件用户或通讯组列表项标识符。</span><span class="sxs-lookup"><span data-stu-id="a687a-106">For each address book entry of interest, call [IAddrBook::OpenEntry](iaddrbook-openentry.md), passing the entry identifier of the target messaging user or distribution list.</span></span>
    
2. <span data-ttu-id="a687a-107">然后执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="a687a-107">Then do one of the following:</span></span>
    
   - <span data-ttu-id="a687a-108">要检索的一个或多个属性的列表与每个通讯簿条目感兴趣，呼叫消息的用户或通讯组列表[IMAPIProp::GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a687a-108">Call the messaging user or distribution list's [IMAPIProp::GetProps](imapiprop-getprops.md) method for each address book entry of interest, with a list of the one or more properties to retrieve.</span></span> 
    
   - <span data-ttu-id="a687a-109">调用[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)，传递包含所有所需的通讯簿条目的所有属性的[ADRLIST](adrlist.md)结构。</span><span class="sxs-lookup"><span data-stu-id="a687a-109">Call [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md), passing an [ADRLIST](adrlist.md) structure that holds all of the properties for all of the desired address book entries.</span></span> <span data-ttu-id="a687a-110">一次调用**PrepareRecips**可以返回信息的多个地址簿条目，因为它是最好的策略时您感兴趣多个收件人。</span><span class="sxs-lookup"><span data-stu-id="a687a-110">Because one call to **PrepareRecips** can return information for multiple address book entries, it is the preferable strategy when you are interested in more than one recipient.</span></span> 
    

