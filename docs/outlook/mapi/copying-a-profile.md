---
title: 复制配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b722a157-0d92-404d-9075-39547241dbb7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 53b7099ae74828a97eb703b865ba30ab385e9a5f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564932"
---
# <a name="copying-a-profile"></a>复制配置文件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建一个配置文件的一种方法是从现有的配置文件复制和更改的必要消息服务和服务提供商。 复制一个配置文件包括使用通过[MAPIAdminProfiles](mapiadminprofiles.md)函数提供 MAPI 配置文件管理对象。 
  
 **若要将配置文件复制**
  
1. 调用**MAPIAdminProfiles**检索**IProfAdmin**接口的指针。 
    
2. 调用[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)访问 profile 表。 
    
3. 生成与[SPropertyRestriction](spropertyrestriction.md)结构，以匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性限制要复制的配置文件的名称。 
    
4. 调用[IMAPITable::FindRow](imapitable-findrow.md) profile 表中查找相应的行。 
    
5. 调用[IProfAdmin::CopyProfile](iprofadmin-copyprofile.md)，作为_lpszOldProfileName_参数传递**PR_DISPLAY_NAME**列的值。 
    

