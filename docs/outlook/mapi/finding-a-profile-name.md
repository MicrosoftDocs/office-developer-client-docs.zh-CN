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
  
在会话过程中，有几个方法可以检索配置文件的名称。 如果需要查找不一定用于会话的配置文件的名称，请使用第一个过程。 如果需要查找默认配置文件的名称，请使用第二个过程。 如果需要查找会话的当前配置文件的名称，请使用上一过程。 
  
 **查找任何配置文件的名称**
  
1. 调用 [MAPIAdminProfiles](mapiadminprofiles.md) 以检索 **IProfAdmin** 接口指针。 
    
2. 调用 [IProfAdmin：：GetProfileTable](iprofadmin-getprofiletable.md) 以访问配置文件表。 
    
3. 调用配置文件表的 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法来检索表中的所有行，并检查每个行以确定它是否表示目标配置文件。 
    
 **查找默认配置文件的名称**
  
1. 调用 [MAPIAdminProfiles](mapiadminprofiles.md)。
    
2. 调用 [IProfAdmin：：GetProfileTable](iprofadmin-getprofiletable.md) 以访问配置文件表。 
    
3. 使用[SPropertyRestriction](spropertyrestriction.md)结构构建一个属性限制，PR_DEFAULT_PROFILE ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 值 TRUE。
    
4. 调用 [IMAPITable：：FindRow](imapitable-findrow.md) 以查找配置文件表中表示默认配置文件的行。 **"PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 列包含默认配置文件的名称。
    
 **查找当前配置文件的名称**
  
若要查找当前配置文件的名称，请完成以下步骤之一：
  
- 假设您具有表示当前配置文件的其中一个节的 [MAPIUID](mapiuid.md) 结构，请用  _lpUID_ 参数将结构传递给 [IMAPISession：：OpenProfileSection](imapisession-openprofilesection.md)。 使用配置文件节的 [IMAPIProp：：PR_PROFILE_NAME](imapiprop-getprops.md) **(** 方法) [PidTagProfileName](pidtagprofilename-canonical-property.md)属性检索配置文件节的配置文件。 
    
- 调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 以访问状态表并查找其 **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 设置为 MAPI_SUBSYSTEM 的行。 该行 **PR_DISPLAY_NAME** 列是配置文件名称。 请勿在启动期间使用状态表，因为它会阻止应用程序，直到 MAPI 后台处理程序完成初始化所有传输提供程序。 这会降低性能。 
    

