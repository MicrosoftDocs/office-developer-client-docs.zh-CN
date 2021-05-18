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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408941"
---
# <a name="pidtagpstconfigurationflags-canonical-property"></a>PidTagPstConfigurationFlags 规范属性
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为个人存储表指定配置标志 (.pst 文件) 。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PST_CONFIG_FLAGS  <br/> |
|标识符:  <br/> |0x6770  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |内部存储表 (.pst) 存储表  <br/> |
   
## <a name="remarks"></a>备注

以下是此属性的有效值：
  
PST_CONFIG_UNICODE
  
> 指示 Unicode .pst 文件。 
    
   `#define PST_CONFIG_UNICODE 0x80000000`
    
PST_CONFIG_CREATE_NOWARN
  
> 从客户端标志设置为 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md) 方法时，将 **ConfigureMsgService** 视为 [IMsgServiceAdmin：：CreateMsgService](imsgserviceadmin-createmsgservice.md) 调用，并跳过"此信息服务尚未配置"警告。 
    
   `#define PST_CONFIG_CREATE_NOWARN 0x00000001`
    
PST_CONFIG_PRESERVE_DISPLAY_NAME
  
> 指示 **ConfigureMsgService** 不要更改 [PidTagDisplayName PR_DISPLAY_NAME (PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的值，即使已提供。  在这种情况下，仅为新的 .pst 文件提供它。
    
   `#define PST_CONFIG_PRESERVE_DISPLAY_NAME 0x00000002`
    
OST_CONFIG_POLICY_DELAY_IGNORE_OST
  
> 指示配置代码首先显示一个对话框，以确认是否找到脱机文件夹 (.ost) 文件，然后根据用户的响应，使用找到的脱机文件夹或允许用户浏览另一个脱机文件夹。
    
   `#define OST_CONFIG_POLICY_DELAY_IGNORE_OST 0x00000008`
    
OST_CONFIG_CREATE_NEW_DEFAULT
  
> 复制具有新唯一名称的 .ost 文件并放弃当前名称。 现有 .ost 文件仍保留在计算机上，但不再在此配置文件中使用。 这通常发生在 Microsoft Outlook不再允许特定的 .ost 文件，并且注册表策略不允许用户重命名该文件时。 
    
   `#define OST_CONFIG_CREATE_NEW_DEFAULT_OST 0x00000010`
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]] 
  
> 提供对相关协议Exchange Server的引用。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

