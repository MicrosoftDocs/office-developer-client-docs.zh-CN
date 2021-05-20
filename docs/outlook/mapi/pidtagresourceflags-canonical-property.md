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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436228"
---
# <a name="pidtagresourceflags-canonical-property"></a>PidTagResourceFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件服务和提供程序标志的位掩码。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOURCE_FLAGS  <br/> |
|标识符:  <br/> |0x3009  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI common  <br/> |
   
## <a name="remarks"></a>备注

此属性描述邮件服务、服务提供商或状态对象的特征。 为此属性设置的标志取决于其上下文。 例如，某些标志仅对状态对象有效，其他标志仅对邮件服务表中的列有效。 
  
标志有三个类：静态、可修改和动态。 静态标志由 MAPI 从 MAPISVC 数据设置。INF，从不更改。 可修改标志由 MAPISVC 中的 MAPI 设置。INF，但可以随后更改。 可通过 MAPI 方法设置和重置动态标志。
  
对于邮件服务，可以在此属性中设置以下一个或多个标志：
  
SERVICE_CREATE_WITH_STORE 
  
> 保留。 请勿使用。
    
SERVICE_DEFAULT_STORE 
  
> 动态。 邮件服务包含默认存储。 在从配置文件中删除或移动此服务之前，应显示一个用户界面，提示用户进行确认。 
    
SERVICE_NO_PRIMARY_IDENTITY 
  
> 静态。 应设置为指示邮件服务中任何提供程序均不能用于提供标识的服务级别标志。 应设置此SERVICE_PRIMARY_IDENTITY，但不能同时设置这两者。
    
SERVICE_PRIMARY_IDENTITY 
  
> 可修改。 相应的邮件服务包含用于此会话的主标识的提供程序。 使用 [IMsgServiceAdmin：：SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) 设置此标志。 应设置此SERVICE_NO_PRIMARY_IDENTITY，但不能同时设置这两者。 
    
SERVICE_SINGLE_COPY 
  
> 静态。 创建此邮件服务或将其复制到已存在该服务的配置文件的任何尝试都将失败。 若要创建单个副本邮件服务 **，PR_RESOURCE_FLAGS属性** 添加到 MAPISVC 中的服务部分。INF 并设置此标志。 
    
对于服务提供商，可以在"服务"中设置以下一个或多个 **PR_RESOURCE_FLAGS：**
  
HOOK_INBOUND 
  
> 静态。 后台处理程序挂钩需要处理入站邮件。
    
HOOK_OUTBOUND 
  
> 静态。 后台处理程序挂钩需要处理出站邮件。 
    
STATUS_DEFAULT_OUTBOUND 
  
> 可修改。 如果配置文件包含此传输提供程序的多个实例，则此标识应应用于出站邮件。 如果单个传输提供程序的多个实例出现在配置文件中，则可能会发生这种情况。
    
STATUS_DEFAULT_STORE 
  
> 可修改。 此消息存储是配置文件的默认存储。 
    
STATUS_NEED_IPM_TREE 
  
> 动态。 此邮件存储中的标准文件夹（包括 iPM (IPM) 文件夹）尚未验证。 MAPI 设置并清除此标志。 
    
STATUS_NO_DEFAULT_STORE 
  
> 静态。 此邮件存储无法成为配置文件的默认邮件存储。
    
STATUS_NO_PRIMARY_IDENTITY 
  
> 静态。 此提供程序不在其状态行中提供标识。 必须设置此STATUS_PRIMARY_IDENTITY或标记。
    
STATUS_OWN_STORE 
  
> 静态。 此传输提供程序与邮件存储紧密结合，并在其状态PR_OWN_STORE_ENTRYID ( [PidTagOwnStoreEntryId) PidTagOwnStoreEntryId](pidtagownstoreentryid-canonical-property.md)属性。
    
STATUS_PRIMARY_IDENTITY 
  
> 可修改。 此提供程序提供会话的主标识;提供标识的对象的条目标识符从 [IMAPISession：：QueryIdentity 返回](imapisession-queryidentity.md)。 必须设置此 **STATUS_NO_PRIMARY_IDENTITY** 或标记。 
    
STATUS_PRIMARY_STORE 
  
> 可修改。 此消息存储是在客户端应用程序登录时使用的。 打开后，此存储应设置为配置文件的默认存储。 
    
STATUS_SECONDARY_STORE 
  
> 可修改。 如果主存储在客户端应用程序登录时不可用，则使用此消息存储。 打开后，此存储应设置为配置文件的默认存储。 
    
STATUS_SIMPLE_STORE 
  
> 动态。 简单 MAPI 将此消息存储用作其默认邮件存储。
    
STATUS_TEMP_SECTION 
  
> 动态。 此消息存储不应在邮件存储表中发布，并且将在注销后从配置文件中删除。 
    
STATUS_XP_PREFER_LAST 
  
> 静态。 当多个传输提供程序能够传输邮件时，此传输预期是最后一次选择发送邮件的传输。
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)
  
[PidTagIdentityEntryId 规范属性](pidtagidentityentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

