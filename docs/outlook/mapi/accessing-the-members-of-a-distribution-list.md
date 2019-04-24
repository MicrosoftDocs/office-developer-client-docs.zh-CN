---
title: 访问通讯组列表的成员
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f724cac8-2d5d-42bc-a15e-99f77a99ce21
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2944a53d27bc916ccafcfa649d79e3c00afaf622
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331239"
---
# <a name="accessing-the-members-of-a-distribution-list"></a>访问通讯组列表的成员

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **获取通讯组列表的成员**
  
1. 使用要检索的成员的属性创建大小的属性标记数组, 如**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))。
    
2. 调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md)以打开通讯组列表。 
    
3. 调用通讯组列表的**IABContainer:: GetContentsTable**方法以访问其内容表。 
    
4. 调用[HrQueryAllRows](hrqueryallrows.md)以检索表示通讯组列表成员的所有表的行。 
    

