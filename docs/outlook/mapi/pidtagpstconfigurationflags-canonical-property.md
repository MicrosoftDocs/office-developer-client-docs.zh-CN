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
ms.openlocfilehash: b5a3978741f7ecb871e3c3de28e52dffdcf3a74f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778090"
---
# <a name="pidtagpstconfigurationflags-canonical-property"></a>PidTagPstConfigurationFlags 规范属性
  
**适用于**： Outlook 
  
指定配置个人存储表 （.pst 文件） 的标志。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PST_CONFIG_FLAGS  <br/> |
|标识符：  <br/> |0x6770  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |个人存储表 (.pst) 内部  <br/> |
   
## <a name="remarks"></a>说明

此属性的有效值如下：
  
PST_CONFIG_UNICODE
  
> 指示 Unicode.pst 文件。 
    
   `#define PST_CONFIG_UNICODE 0x80000000`
    
PST_CONFIG_CREATE_NOWARN
  
> 当从客户端设置[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法的标志、 类似[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)调用处理**ConfigureMsgService**和跳过"此信息服务尚未配置"警告。 
    
   `#define PST_CONFIG_CREATE_NOWARN 0x00000001`
    
PST_CONFIG_PRESERVE_DISPLAY_NAME
  
> 即使在提供通知**ConfigureMsgService**未更改，则**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值。 在这种情况下，在提供只为新的.pst 文件。
    
   `#define PST_CONFIG_PRESERVE_DISPLAY_NAME 0x00000002`
    
OST_CONFIG_POLICY_DELAY_IGNORE_OST
  
> 通知配置代码首先显示一个对话框，确认是否已脱机文件夹 (.ost) 文件找到，根据用户的解答，可以使用找到的脱机文件夹或允许用户浏览另一个脱机文件夹。
    
   `#define OST_CONFIG_POLICY_DELAY_IGNORE_OST 0x00000008`
    
OST_CONFIG_CREATE_NEW_DEFAULT
  
> 复制新的唯一名称的.ost 文件，并放弃的当前名称。 现有的.ost 文件的计算机上，但已不再使用此配置文件中。 这通常发生在 Microsoft Outlook 不再允许一个特定的.ost 文件，并且注册表策略不允许用户重命名该文件。 
    
   `#define OST_CONFIG_CREATE_NEW_DEFAULT_OST 0x00000010`
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]] 
  
> 提供了相关的 Exchange Server 协议规范参考。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

