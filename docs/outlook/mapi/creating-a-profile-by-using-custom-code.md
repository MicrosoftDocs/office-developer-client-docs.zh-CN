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
  
如果您选择编写代码来创建配置文件，请确保您了解如何对配置文件条目排序以及每个条目所需的类型和信息量。 MAPI Profiles 中介绍了对配置文件中的条目 [排序的含义](mapi-profiles.md)。
  
 **使用 C 或 C++ 代码创建配置文件**
  
1. 读取每个邮件服务的标题文件。 了解需要配置的属性以及将使用的值。
    
2. 调用 [MAPIAdminProfiles](mapiadminprofiles.md) 函数以检索 **IProfAdmin** 接口指针。 
    
3. 调用 [IProfAdmin：：CreateProfile](iprofadmin-createprofile.md) 以创建配置文件。 如果要使用 MAPISVC **的 [默认服务]** 部分中列出的邮件服务创建配置文件。INF 文件，设置MAPI_DEFAULT_SERVICE标记。 如果要允许用户输入配置信息，请设置MAPI_DIALOG标记。 如果并非所有必要信息都可以通过 MAPISVC 获取，请确保设置此标志。INF 文件。 **CreateProfile** 调用要添加到配置文件（将 MSG_SERVICE_CREATE  _ulContext_ 参数）的每个邮件服务的入口点函数。 
    
4. 调用 [IProfAdmin：：AdminServices](iprofadmin-adminservices.md) 以获取邮件服务管理对象。 
    
5. 使用邮件服务管理对象将邮件服务添加到配置文件。 对于要添加的每个邮件服务：
    
1. 调用 [IMsgServiceAdmin：：CreateMsgService](imsgserviceadmin-createmsgservice.md) 方法来创建新的邮件服务。 
    
2. 调用 [IMsgServiceAdmin：：ConfigureMsgService，](imsgserviceadmin-configuremsgservice.md)传递刚创建的服务的 **MAPIUID** 结构以及一个属性值数组及其配置属性。 
    
6. 若要检索新添加的服务（即 **其 PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性）的标识符，请调用 [IMsgServiceAdmin：：GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) 以访问邮件服务表并搜索表示邮件服务的行。 表中的最后一行将表示最近添加的邮件服务。 
    
若要使新配置文件成为临时配置文件，请在您登录后立即调用 [IProfAdmin：:D eleteProfile](iprofadmin-deleteprofile.md) 方法。 **DeleteProfile** 将新配置文件标记为已删除，同时使其在会话期间可用。 因为它不会包含在会话的配置文件表中，所以其他客户端将无法使用它。 
  

