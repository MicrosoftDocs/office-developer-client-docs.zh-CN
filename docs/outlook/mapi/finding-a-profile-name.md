---
title: 查找配置文件名称
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 18df25b7-16b7-44cd-a9a0-5276966c1fd4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 332b78bcebbcd54de43376553ec4aea386c1c359
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774928"
---
# <a name="finding-a-profile-name"></a>查找配置文件名称

  
  
**适用于**： Outlook 
  
有时，客户端需要查找当前正在使用的会话、 默认配置文件的名称或其他计算机上安装的配置文件的名称的配置文件的名称。
  
有几种方法在会话过程中的过程中检索一个配置文件的名称。 如果您需要查找不一定是一个会话所用的配置文件的名称，请使用第一个过程。 如果您需要查找默认配置文件的名称，请使用第二个过程。 如果您需要为会话中查找当前配置文件的名称，请使用上一过程。 
  
 **若要查找的任何配置文件名称**
  
1. 调用[MAPIAdminProfiles](mapiadminprofiles.md)检索**IProfAdmin**接口的指针。 
    
2. 调用[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)访问 profile 表。 
    
3. 调用 profile 表的[IMAPITable::QueryRows](imapitable-queryrows.md)方法来检索所有表中的行和检查每个以确定它是否代表您目标的配置文件。 
    
 **若要查找的默认配置文件的名称**
  
1. 调用[MAPIAdminProfiles](mapiadminprofiles.md)。
    
2. 调用[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)访问 profile 表。 
    
3. 生成与[SPropertyRestriction](spropertyrestriction.md)结构，以匹配的值为 TRUE **PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 的属性限制。
    
4. 调用[IMAPITable::FindRow](imapitable-findrow.md)以表示的默认配置文件的配置文件表中找到的行。 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 列中包含的默认配置文件的名称。
    
 **若要查找的当前配置文件名称**
  
若要查找当前配置文件的名称，请完成以下步骤之一：
  
- 假定您有[MAPIUID](mapiuid.md)结构，它表示当前配置文件的部分之一，将其传递_lpUID_参数中给[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)。 检索使用其[IMAPIProp::GetProps](imapiprop-getprops.md)方法的配置文件部分的**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 属性。 
    
- 调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表和查找已设置为 MAPI_SUBSYSTEM 其**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列的行。 此行**PR_DISPLAY_NAME**列是配置文件名称。 不要使用状态表期间开始因为它会阻止应用程序直到 MAPI 后台处理程序完成初始化所有传输提供程序。 这样做会降低性能。 
    

