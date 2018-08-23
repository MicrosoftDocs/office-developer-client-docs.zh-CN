---
title: 使用自定义代码创建配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5632cd25-58f5-4b9c-906c-cd377abc3daf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c14d58e8a03633615798b50b256b9cc54fcc4f4c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594731"
---
# <a name="creating-a-profile-by-using-custom-code"></a>使用自定义代码创建配置文件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
如果您选择编写代码来创建一个配置文件，请确保您了解如何进行排序的配置文件条目的类型和数量的所需的每个项的信息。 排序配置文件中的条目的含义是[MAPI 配置文件](mapi-profiles.md)中所述。
  
 **使用 C 或 c + + 代码创建一个配置文件**
  
1. 读取每个消息服务的标头文件。 了解您需要配置的属性和您值将使用什么。
    
2. 调用[MAPIAdminProfiles](mapiadminprofiles.md)函数以检索**IProfAdmin**接口的指针。 
    
3. 调用[IProfAdmin::CreateProfile](iprofadmin-createprofile.md)创建您的配置文件。 如果您想要创建一个具有 MAPISVC **[默认服务]** 节中列出的消息服务配置。INF 文件设置 MAPI_DEFAULT_SERVICE 标志。 如果您想要让用户能够输入配置信息，设置 MAPI_DIALOG 标志。 请确保您设置此标志，如果不是所有必要信息都可通过 MAPISVC。INF 文件。 **CreateProfile**调用入口点函数添加到配置文件与 MSG_SERVICE_CREATE 作为_ulContext_参数设置每个邮件服务。 
    
4. 调用[IProfAdmin::AdminServices](iprofadmin-adminservices.md)获取消息服务管理对象。 
    
5. 使用消息服务管理对象添加到配置文件的消息服务。 为每个要添加的消息服务：
    
1. 调用[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)方法以创建新的邮件服务。 
    
2. 调用[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)，传递的您刚才创建的服务**MAPIUID**结构和配置属性的属性值数组。 
    
6. 若要检索的一个新添加的服务，它是其**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性，标识符调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)访问邮件服务表和行值，该值代表搜索邮件服务。 表中的最后一行将表示最近添加的邮件服务。 
    
将使新的配置文件设置为临时，可在登录后立即调用[IProfAdmin::DeleteProfile](iprofadmin-deleteprofile.md)方法。 为使其会话的持续时间内可用时已删除， **DeleteProfile**将标记新配置文件。 因为它不会将会话的配置文件表中，其他客户端将无法使用它。 
  

