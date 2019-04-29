---
title: 查找配置文件名称
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 18df25b7-16b7-44cd-a9a0-5276966c1fd4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b4efdd8d8238d4bc7e89a1153b9be34c7af76355
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407919"
---
# <a name="finding-a-profile-name"></a>查找配置文件名称

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端有时需要查找当前用于会话的配置文件的名称、默认配置文件的名称或计算机上安装的备用配置文件的名称。
  
在会话过程中, 有几种方法可以检索配置文件的名称。 如果需要查找不一定要用于会话的配置文件的名称, 请使用第一个过程。 如果需要查找默认配置文件的名称, 请使用第二个过程。 如果需要查找会话的当前配置文件的名称, 请使用最后的过程。 
  
 **查找任何配置文件的名称**
  
1. 调用[MAPIAdminProfiles](mapiadminprofiles.md)以检索**IProfAdmin**接口指针。 
    
2. 调用[IProfAdmin:: GetProfileTable](iprofadmin-getprofiletable.md)以访问配置文件表。 
    
3. 调用配置文件表的[IMAPITable:: QueryRows](imapitable-queryrows.md)方法以检索表中的所有行, 并检查每个行, 以确定它是否表示您的目标配置文件。 
    
 **查找默认配置文件的名称**
  
1. 调用[MAPIAdminProfiles](mapiadminprofiles.md)。
    
2. 调用[IProfAdmin:: GetProfileTable](iprofadmin-getprofiletable.md)以访问配置文件表。 
    
3. 生成具有[SPropertyRestriction](spropertyrestriction.md)结构的属性限制, 以匹配**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 值为 TRUE。
    
4. 调用[IMAPITable:: FindRow](imapitable-findrow.md)以查找表示默认配置文件的配置文件表中的行。 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 列包含默认配置文件的名称。
    
 **查找当前配置文件的名称**
  
若要查找当前配置文件的名称, 请完成以下步骤之一:
  
- 假定您具有表示当前配置文件的各个部分的[MAPIUID](mapiuid.md)结构, 请将其传递到[IMAPISession:: OpenProfileSection](imapisession-openprofilesection.md)的_lpUID_参数中。 使用[IMAPIProp:: GetProps](imapiprop-getprops.md)方法检索 profile 节的**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 属性。 
    
- 调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)以访问状态表, 并查找其**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列设置为 MAPI_SUBSYSTEM 的行。 此行的 " **PR_DISPLAY_NAME** " 列是配置文件名称。 不要在启动过程中使用状态表, 因为它会阻止应用程序, 直到 MAPI 后台处理程序已完成所有传输提供程序的初始化。 这可能会降低性能。 
    

