---
title: 访问通讯组列表的成员
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f724cac8-2d5d-42bc-a15e-99f77a99ce21
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 21975482c458998cbe158a84d535f911156ac392
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774504"
---
# <a name="accessing-the-members-of-a-distribution-list"></a>访问通讯组列表的成员

  
  
**适用于**： Outlook 
  
 **若要获取的通讯组列表成员**
  
1. 创建具有您想要检索，如**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_DISPLAY_TYPE** ([的成员属性的大小的属性标记数组PidTagDisplayType](pidtagdisplaytype-canonical-property.md))。
    
2. 调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)打开通讯组列表。 
    
3. 调用该通讯组列表**IABContainer::GetContentsTable**方法，以访问其内容表。 
    
4. 调用[HrQueryAllRows](hrqueryallrows.md)检索所有表的行代表通讯组列表的成员。 
    

