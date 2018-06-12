---
title: PidTagResourceFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResourceFlags
api_type:
- COM
ms.assetid: 69be9ad3-006a-459e-9cd4-eb3f609d71ad
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: dae917b3e536aee5f24879edc3ccf0736e7c9f34
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778222"
---
# <a name="pidtagresourceflags-canonical-property"></a>PidTagResourceFlags 规范属性

  
  
**适用于**： Outlook 
  
包含消息服务和提供程序的标志的位掩码。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_RESOURCE_FLAGS  <br/> |
|标识符:  <br/> |0x3009  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常见的 MAPI  <br/> |
   
## <a name="remarks"></a>备注

此属性描述了消息服务、 服务提供商或状态对象的特征。 为此属性设置的标志取决于其上下文。 例如，一些标志是仅供状态对象和其他标志仅用于邮件服务表中的列。 
  
标志是三个类： 静态和动态的可修改。 通过 MAPI 从 MAPISVC 数据设置静态标志。INF 和永远不会改变。 从 MAPISVC 通过 MAPI 设置可修改标志。INF 但可以随后更改。 可以设置并通过 MAPI 方法来重置动态的标志。
  
对于邮件服务，可以在此属性设置一个或多个以下标志：
  
SERVICE_CREATE_WITH_STORE 
  
> 保留。 请勿使用。
    
SERVICE_DEFAULT_STORE 
  
> 动态。 邮件服务包含默认存储。 提示用户确认删除或移动配置文件利用此服务之前，应显示的用户界面。 
    
SERVICE_NO_PRIMARY_IDENTITY 
  
> 静态。 应设置为指示无邮件服务中的提供程序可以使用提供标识服务级别标记。 此标志或 SERVICE_PRIMARY_IDENTITY 应设置，但不是能同时。
    
SERVICE_PRIMARY_IDENTITY 
  
> 可修改。 相应的消息服务包含一些主要标识用于此会话的提供程序。 使用[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)来设置此标志。 此标志或 SERVICE_NO_PRIMARY_IDENTITY 应设置，但不是能同时。 
    
SERVICE_SINGLE_COPY 
  
> 静态。 创建或将此消息服务复制到配置文件服务已存在任何尝试将失败。 若要创建的单个副本消息服务，请添加到 MAPISVC 中的服务一节的**PR_RESOURCE_FLAGS**属性。INF 和设置此标志。 
    
对于服务提供商，一个或多个以下标志可以设置**PR_RESOURCE_FLAGS**中：
  
HOOK_INBOUND 
  
> 静态。 后台处理程序挂接需要处理入站的邮件。
    
HOOK_OUTBOUND 
  
> 静态。 后台处理程序挂接需要处理出站邮件。 
    
STATUS_DEFAULT_OUTBOUND 
  
> 可修改。 如果配置文件包含此传输提供程序的多个实例，此标识应该应用于出站邮件。 如果在配置文件中显示单个传输提供程序的多个实例，则可以发生此错误。
    
STATUS_DEFAULT_STORE 
  
> 可修改。 此消息存储是配置文件的默认存储。 
    
STATUS_NEED_IPM_TREE 
  
> 动态。 此消息存储，包括人际邮件 (IPM) 根文件夹中的标准文件夹尚未验证。 MAPI 设置，并清除此标志。 
    
STATUS_NO_DEFAULT_STORE 
  
> 静态。 此消息存储不能成为默认的邮件存储配置文件。
    
STATUS_NO_PRIMARY_IDENTITY 
  
> 静态。 此提供程序不提供其状态行中的标识。 必须设置此标志或 STATUS_PRIMARY_IDENTITY。
    
STATUS_OWN_STORE 
  
> 静态。 此传输提供程序紧密结合的消息存储，并提供其状态行中的**PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) 属性。
    
STATUS_PRIMARY_IDENTITY 
  
> 可修改。 此提供程序提供的主要标识会话;从[IMAPISession::QueryIdentity](imapisession-queryidentity.md)返回 furnishing 标识的对象的项标识符。 必须设置此标志或**STATUS_NO_PRIMARY_IDENTITY** 。 
    
STATUS_PRIMARY_STORE 
  
> 可修改。 此消息存储是用于客户端应用程序登录。 打开后，应将此存储设置为默认配置文件存储。 
    
STATUS_SECONDARY_STORE 
  
> 可修改。 此消息存储是用于如果客户端应用程序在登录时，主存储不可用。 打开后，应将此存储设置为默认配置文件存储。 
    
STATUS_SIMPLE_STORE 
  
> 动态。 此消息存储将使用任务的简单 MAPI 作为其默认邮件存储区。
    
STATUS_TEMP_SECTION 
  
> 动态。 此消息存储不应该发布消息存储表中，注销后将删除其从配置文件。 
    
STATUS_XP_PREFER_LAST 
  
> 静态。 此传输要求选择多个传输提供程序时能够将邮件传输发送消息的最后一个传输。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)
  
[PidTagIdentityEntryId 规范属性](pidtagidentityentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

