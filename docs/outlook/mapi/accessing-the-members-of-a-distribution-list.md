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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412385"
---
# <a name="accessing-the-members-of-a-distribution-list"></a>访问通讯组列表的成员

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **获取通讯组列表的成员**
  
1. 使用要检索的成员的属性（如 PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md) **) 、PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和 **PR_DISPLAY_TYPE**  ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) ）创建大小属性标记数组。
    
2. 调用 [IAddrBook：：OpenEntry](iaddrbook-openentry.md) 打开通讯组列表。 
    
3. 调用通讯组列表的 **IABContainer：：GetContentsTable** 方法以访问其内容表。 
    
4. 调用 [HrQueryAllRows](hrqueryallrows.md) 以检索表示通讯组列表成员的表的所有行。 
    

