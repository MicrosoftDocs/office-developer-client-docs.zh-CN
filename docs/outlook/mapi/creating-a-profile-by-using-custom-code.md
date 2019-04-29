---
title: 使用自定义代码创建配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5632cd25-58f5-4b9c-906c-cd377abc3daf
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f3270528194b3cc3429d3afec153355349dabbff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413302"
---
# <a name="creating-a-profile-by-using-custom-code"></a>使用自定义代码创建配置文件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果选择编写代码来创建配置文件, 请确保了解如何对配置文件条目进行排序, 以及每个条目所需的信息类型和数量。 在配置文件中对条目进行排序的含义将在[MAPI 配置文件](mapi-profiles.md)中进行说明。
  
 **使用 C 或 c + + 代码创建配置文件**
  
1. 读取每个邮件服务的头文件。 了解需要配置的属性以及将使用的值。
    
2. 调用[MAPIAdminProfiles](mapiadminprofiles.md)函数以检索**IProfAdmin**接口指针。 
    
3. 调用[IProfAdmin:: CreateProfile](iprofadmin-createprofile.md)以创建您的配置文件。 如果要使用 mapisvc.inf 的 **[默认服务]** 部分列出的邮件服务创建配置文件。INF 文件, 请设置 MAPI_DEFAULT_SERVICE 标志。 如果要使用户能够输入配置信息, 请设置 MAPI_DIALOG 标志。 如果并非所有必需的信息都可通过 mapisvc.inf, 请确保您设置此标志。INF 文件。 **CreateProfile**调用要添加到配置文件中的每个邮件服务的入口点函数, 并将 MSG_SERVICE_CREATE 设置为_ulContext_参数。 
    
4. 调用[IProfAdmin:: AdminServices](iprofadmin-adminservices.md)以获取邮件服务管理对象。 
    
5. 使用邮件服务管理对象将邮件服务添加到配置文件中。 对于要添加的每个邮件服务:
    
1. 调用[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)方法以创建新的邮件服务。 
    
2. 调用[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md), 并将您刚创建的服务的**MAPIUID**结构和属性值数组与其配置属性进行传递。 
    
6. 若要检索新添加的服务的标识符 (它是其**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性), 请调用[IMsgServiceAdmin:: GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)以访问邮件服务表, 并搜索表示的行邮件服务。 表中的最后一行表示最近添加的邮件服务。 
    
若要将新的配置文件设为临时, 请在登录后立即调用[IProfAdmin::D eleteprofile](iprofadmin-deleteprofile.md)方法。 **DeleteProfile**会将新配置文件标记为已删除, 同时使其在会话期间可用。 由于它不会包含在会话的配置文件表中, 因此其他客户端将无法使用它。 
  

