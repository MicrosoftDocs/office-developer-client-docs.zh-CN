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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2fb9eed0beaf7269ac90a021dae650355484ebc2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330182"
---
# <a name="pidtagresourceflags-canonical-property"></a>PidTagResourceFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件服务和提供程序的标志的位掩码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOURCE_FLAGS  <br/> |
|标识符:  <br/> |0x3009  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 通用  <br/> |
   
## <a name="remarks"></a>注解

此属性描述邮件服务、服务提供程序或状态对象的特征。 为此属性设置的标志取决于其上下文。 例如, 一些标志仅对 status 对象和仅适用于邮件服务表中的列的其他标志有效。 
  
这些标志分为三个类: 静态、可修改和动态。 静态标志由 MAPI 从 mapisvc.inf 中的数据进行设置。INF, 永远不会改变。 可修改的标志由 MAPI 从 mapisvc.inf 进行设置。INF, 但随后可以更改。 可以通过 MAPI 方法设置和重置动态标志。
  
对于邮件服务, 可以在此属性中设置以下一个或多个标志:
  
SERVICE_CREATE_WITH_STORE 
  
> 保留。 请勿使用。
    
SERVICE_DEFAULT_STORE 
  
> 动态. 邮件服务包含默认存储区。 应显示一个用户界面, 提示用户在删除或将此服务从配置文件移出之前进行确认。 
    
SERVICE_NO_PRIMARY_IDENTITY 
  
> 静止. 应设置的服务级别标志, 以指示邮件服务中的任何提供程序都不能用于提供标识。 应设置此标志或 SERVICE_PRIMARY_IDENTITY, 但不能同时设置这两者。
    
SERVICE_PRIMARY_IDENTITY 
  
> 可. 相应的邮件服务包含用于此会话的主要标识的提供程序。 使用[IMsgServiceAdmin:: SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)设置此标志。 应设置此标志或 SERVICE_NO_PRIMARY_IDENTITY, 但不能同时设置这两者。 
    
SERVICE_SINGLE_COPY 
  
> 静止. 任何尝试在服务已存在的配置文件中创建或复制此邮件服务的尝试都将失败。 若要创建单个副本邮件服务, 请将**PR_RESOURCE_FLAGS**属性添加到 mapisvc.inf 中的服务部分。INF 并设置此标志。 
    
对于服务提供商, 可以在**PR_RESOURCE_FLAGS**中设置以下一个或多个标志:
  
HOOK_INBOUND 
  
> 静止. 后台打印程序挂钩需要处理入站邮件。
    
HOOK_OUTBOUND 
  
> 静止. 后台打印程序挂钩需要处理出站邮件。 
    
STATUS_DEFAULT_OUTBOUND 
  
> 可. 如果配置文件包含此传输提供程序的多个实例, 则应将此标识应用于出站邮件。 如果一个传输提供程序的多个实例显示在配置文件中, 则会发生这种情况。
    
STATUS_DEFAULT_STORE 
  
> 可. 此邮件存储区是配置文件的默认存储区。 
    
STATUS_NEED_IPM_TREE 
  
> 动态. 此邮件存储区中的标准文件夹 (包括人际邮件 (IPM) 根文件夹) 尚未验证。 MAPI 设置并清除此标志。 
    
STATUS_NO_DEFAULT_STORE 
  
> 静止. 此邮件存储无法成为配置文件的默认邮件存储区。
    
STATUS_NO_PRIMARY_IDENTITY 
  
> 静止. 此提供程序不在其状态行中提供标识。 必须设置此标志或 STATUS_PRIMARY_IDENTITY。
    
STATUS_OWN_STORE 
  
> 静止. 此传输提供程序与邮件存储紧密结合, 并在其状态行中提供**PR_OWN_STORE_ENTRYID** ([PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)) 属性。
    
STATUS_PRIMARY_IDENTITY 
  
> 可. 此提供程序提供会话的主标识;提供标识的对象的条目标识符是从[IMAPISession:: QueryIdentity](imapisession-queryidentity.md)返回的。 必须设置此标志或**STATUS_NO_PRIMARY_IDENTITY** 。 
    
STATUS_PRIMARY_STORE 
  
> 可. 当客户端应用程序登录时, 将使用此消息存储库。 打开后, 应将此存储区设置为配置文件的默认存储区。 
    
STATUS_SECONDARY_STORE 
  
> 可. 如果客户端应用程序登录时主存储不可用, 则使用此邮件存储。 打开后, 应将此存储区设置为配置文件的默认存储区。 
    
STATUS_SIMPLE_STORE 
  
> 动态. 此邮件存储将由简单 MAPI 用作其默认邮件存储区。
    
STATUS_TEMP_SECTION 
  
> 动态. 此邮件存储库不应在邮件存储表中发布, 并将在注销后从配置文件中删除。 
    
STATUS_XP_PREFER_LAST 
  
> 静止. 当多个传输提供程序能够传输邮件时, 此传输应是选择发送邮件的最后一个传输。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)
  
[PidTagIdentityEntryId 规范属性](pidtagidentityentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

