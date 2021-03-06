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
ms.openlocfilehash: e9aee3280edbed60e97ef6e00e61f3086f6f07ce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436333"
---
# <a name="pidtagresourcemethods-canonical-property"></a>PidTagResourceMethods 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含指示 **IMAPIStatus** 接口中 status 对象支持的方法的位掩码标志。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOURCE_METHODS  <br/> |
|标识符:  <br/> |0x3E02  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>备注

此属性指示状态对象的 **IMAPIStatus** 实现中支持哪些方法。 Status 对象允许从不受MAPI_E_NO_SUPPORT返回值。 
  
客户端使用 status 对象的 **PR_RESOURCE_METHODS** 属性，以避免调用不受支持的方法。 如果设置了与特定方法对应的标志，则该方法存在并可以调用。 如果该标志是明确的，则不应调用 该方法。 
  
MAPI 实现的状态对象支持以下方法：
  
|**Status 对象**|**支持的方法**|
|:-----|:-----|
|MAPI 子系统  <br/> |**仅 ValidateState**  <br/> |
|MAPI 通讯簿  <br/> |**仅 ValidateState**  <br/> |
|MAPI 后台处理程序  <br/> |**ValidateState** 和 **FlushQueues** <br/> |
   
可以在以下值中设置以下一个或多个 **PR_RESOURCE_METHODS：**
  
STATUS_CHANGE_PASSWORD 
  
> 指示 [IMAPIStatus：：ChangePassword](imapistatus-changepassword.md) 方法受支持。 
    
STATUS_FLUSH_QUEUES 
  
> 指示 [IMAPIStatus：：FlushQueues](imapistatus-flushqueues.md) 方法受支持。 
    
STATUS_SETTINGS_DIALOG 
  
> 指示 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 方法受支持。 
    
STATUS_VALIDATE_STATE 
  
> 指示 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法受支持。 
    
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

