---
title: 检索收件人属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 358f892b-54a7-4213-b3c0-94f28f99716f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 38063cebe70b153decce6713ac5fc31d6916dbf6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426672"
---
# <a name="retrieving-recipient-properties"></a><span data-ttu-id="5729b-103">检索收件人属性</span><span class="sxs-lookup"><span data-stu-id="5729b-103">Retrieving recipient properties</span></span>
  
<span data-ttu-id="5729b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5729b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
### <a name="to-access-one-or-more-properties-of-an-address-book-entry"></a><span data-ttu-id="5729b-105">访问通讯簿条目的一个或多个属性</span><span class="sxs-lookup"><span data-stu-id="5729b-105">To access one or more properties of an address book entry</span></span>
  
1. <span data-ttu-id="5729b-106">对于每个相关的通讯簿条目, 请调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md), 并传递目标邮件用户或通讯组列表的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="5729b-106">For each address book entry of interest, call [IAddrBook::OpenEntry](iaddrbook-openentry.md), passing the entry identifier of the target messaging user or distribution list.</span></span>
    
2. <span data-ttu-id="5729b-107">然后执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="5729b-107">Then do one of the following:</span></span>
    
   - <span data-ttu-id="5729b-108">使用要检索的一个或多个属性的列表, 为每个感兴趣的通讯簿条目调用邮件用户或通讯组列表的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5729b-108">Call the messaging user or distribution list's [IMAPIProp::GetProps](imapiprop-getprops.md) method for each address book entry of interest, with a list of the one or more properties to retrieve.</span></span> 
    
   - <span data-ttu-id="5729b-109">调用[IAddrBook::P reparerecips](iaddrbook-preparerecips.md), 并传递一个包含所有所需通讯簿条目的所有属性的[ADRLIST](adrlist.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5729b-109">Call [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md), passing an [ADRLIST](adrlist.md) structure that holds all of the properties for all of the desired address book entries.</span></span> <span data-ttu-id="5729b-110">由于对**PrepareRecips**的一次调用可以返回多个通讯簿条目的信息, 因此当您感兴趣多个收件人时, 这是可取的策略。</span><span class="sxs-lookup"><span data-stu-id="5729b-110">Because one call to **PrepareRecips** can return information for multiple address book entries, it is the preferable strategy when you are interested in more than one recipient.</span></span> 
    

