---
title: 更新 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: faafde3d-3989-4182-91f1-a0cf0f1b5388
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6c2c733b87b85971fad8060040e713b41b0f5616
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407520"
---
# <a name="updating-mapi-properties"></a><span data-ttu-id="85b94-103">更新 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="85b94-103">Updating MAPI properties</span></span>

<span data-ttu-id="85b94-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="85b94-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="85b94-105">客户端和服务提供程序可以通过调用以下内容来更新属性值:</span><span class="sxs-lookup"><span data-stu-id="85b94-105">Clients and service providers can update a property value by calling:</span></span>
  
- <span data-ttu-id="85b94-106">一个对象的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法, 用于更新一个或多个对象属性的值。</span><span class="sxs-lookup"><span data-stu-id="85b94-106">An object's [IMAPIProp::SetProps](imapiprop-setprops.md) method to update the value of one or more of an object's properties.</span></span> 
    
- <span data-ttu-id="85b94-107">[HrSetOneProp](hrsetoneprop.md)函数一次只更新一个属性。</span><span class="sxs-lookup"><span data-stu-id="85b94-107">The [HrSetOneProp](hrsetoneprop.md) function to update only one property at a time.</span></span> <span data-ttu-id="85b94-108">仅当目标对象是本地对象时, 才使用**HrSetOneProp** ;在与远程对象一起使用时, 此函数可能会导致性能下降。</span><span class="sxs-lookup"><span data-stu-id="85b94-108">Use **HrSetOneProp** only if the target object is local; this function can cause performance degradation when used with remote objects.</span></span> 
    
<span data-ttu-id="85b94-109">下面的过程演示如何使用**SetProps**更新邮件的邮件类或 PR_MESSAGE_CLASS_A ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="85b94-109">The following procedure illustrates how to use **SetProps** to update the message class, or PR_MESSAGE_CLASS_A ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property, of a message.</span></span> 
  
### <a name="to-update-the-message-class-of-a-message"></a><span data-ttu-id="85b94-110">更新邮件的邮件类别</span><span class="sxs-lookup"><span data-stu-id="85b94-110">To update the message class of a message</span></span> 
  
1. <span data-ttu-id="85b94-111">为邮件类分配一个[SPropValue](spropvalue.md)结构, 并根据需要设置其成员。</span><span class="sxs-lookup"><span data-stu-id="85b94-111">Allocate an [SPropValue](spropvalue.md) structure for the message class and set its members as appropriate.</span></span> 
    
  ```cpp
    SPropValue spvMsgClass;
    spvMsgClass.ulPropTag = PR_MESSAGE_CLASS_A;
    spvMsgClass.Value.lpszA = "IPM.NewClass";
    
  ```

2. <span data-ttu-id="85b94-112">调用邮件的**IMAPIProp:: SetProps**方法来设置新的邮件类别。</span><span class="sxs-lookup"><span data-stu-id="85b94-112">Call the message's **IMAPIProp::SetProps** method to set the new message class.</span></span> 
    
  ```cpp
    hRes = lpMessage->SetProps(1, (LPSPropValue) &spvMsgClass, NULL);
  ```

## <a name="see-also"></a><span data-ttu-id="85b94-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85b94-113">See also</span></span>

- [<span data-ttu-id="85b94-114">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="85b94-114">MAPI Property Overview</span></span>](mapi-property-overview.md)

