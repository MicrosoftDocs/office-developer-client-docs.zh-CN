---
title: PidTagPstConfigurationFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: e4234ddf-d9dc-4dc9-8eda-dbbee151b5d7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e881c8eeffa29706591e07113d70a3670606f2be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286406"
---
# <a name="pidtagpstconfigurationflags-canonical-property"></a>PidTagPstConfigurationFlags 规范属性
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定个人存储表 (.pst 文件) 的配置标志。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PST_CONFIG_FLAGS  <br/> |
|标识符:  <br/> |0x6770  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |个人存储表 (.pst) 内部  <br/> |
   
## <a name="remarks"></a>注解

以下是此属性的有效值:
  
PST_CONFIG_UNICODE
  
> 指示 Unicode .pst 文件。 
    
   `#define PST_CONFIG_UNICODE 0x80000000`
    
PST_CONFIG_CREATE_NOWARN
  
> 从客户端标志设置为[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法时, 会将**ConfigureMsgService**视为[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)调用, 并跳过 "此信息服务尚未配置"通知. 
    
   `#define PST_CONFIG_CREATE_NOWARN 0x00000001`
    
PST_CONFIG_PRESERVE_DISPLAY_NAME
  
> 指示**ConfigureMsgService**不更改**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值, 即使提供了该属性也是如此。 在这种情况下, 它只提供给新的 .pst 文件。
    
   `#define PST_CONFIG_PRESERVE_DISPLAY_NAME 0x00000002`
    
OST_CONFIG_POLICY_DELAY_IGNORE_OST
  
> 通知配置代码首先显示一个对话框, 以确认是否找到了脱机文件夹 (.ost) 文件, 并且根据用户的响应, 可以使用找到的脱机文件夹或允许用户浏览其他脱机文件夹。
    
   `#define OST_CONFIG_POLICY_DELAY_IGNORE_OST 0x00000008`
    
OST_CONFIG_CREATE_NEW_DEFAULT
  
> 使用新的唯一名称复制 .ost 文件, 并丢弃当前名称。 现有 .ost 文件仍保留在计算机上, 但不再用于此配置文件。 如果 Microsoft Outlook 不再允许使用特定的 .ost 文件, 并且注册表策略不允许用户重命名该文件, 则通常会发生这种情况。 
    
   `#define OST_CONFIG_CREATE_NEW_DEFAULT_OST 0x00000010`
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]] 
  
> 提供对相关 Exchange Server 协议规范的引用。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

