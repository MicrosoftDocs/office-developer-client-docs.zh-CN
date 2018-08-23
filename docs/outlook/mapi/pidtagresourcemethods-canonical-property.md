---
title: PidTagResourceMethods 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResourceMethods
api_type:
- COM
ms.assetid: 60ebbcd5-b758-4c96-b8ec-089e0aae1a5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2e1cff8148815c3e03b92e4d57d1c6a303943c9c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578162"
---
# <a name="pidtagresourcemethods-canonical-property"></a>PidTagResourceMethods 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含这些标志指示**IMAPIStatus**接口中支持的状态对象的方法的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOURCE_METHODS  <br/> |
|标识符：  <br/> |0x3E02  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

此属性指示支持哪种中**IMAPIStatus**状态对象实现的方法。 允许从不受支持方法返回 MAPI_E_NO_SUPPORT 状态对象。 
  
客户端使用状态对象的**PR_RESOURCE_METHODS**属性可避免对不受支持的方法的调用。 如果设置对应于特定方法的标志，此方法存在且可调用它。 如果清除该标志，则不应调用方法。 
  
状态对象实现 MAPI 支持以下方法：
  
|**状态对象**|**受支持的方法**|
|:-----|:-----|
|MAPI 子系统  <br/> |仅**ValidateState**  <br/> |
|MAPI 通讯簿  <br/> |仅**ValidateState**  <br/> |
|MAPI 后台处理程序  <br/> |**ValidateState**和**FlushQueues** <br/> |
   
一个或多个以下标志可以**PR_RESOURCE_METHODS**设置：
  
STATUS_CHANGE_PASSWORD 
  
> 表示支持[IMAPIStatus::ChangePassword](imapistatus-changepassword.md)方法。 
    
STATUS_FLUSH_QUEUES 
  
> 表示支持[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法。 
    
STATUS_SETTINGS_DIALOG 
  
> 表示支持[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法。 
    
STATUS_VALIDATE_STATE 
  
> 表示支持[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。 
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

