---
title: PidLidLogStart 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLogStart
api_type:
- COM
ms.assetid: b8c0c871-51d8-4752-ad4b-607463a9f837
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 359eb4ea4cbbcf6244bf3cca2f3a66b369bce6e0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586674"
---
# <a name="pidlidlogstart-canonical-property"></a>PidLidLogStart 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
表示的开始日期和时间的日记邮件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidLogStart  <br/> |
|属性进行设置：  <br/> |PSETID_Log  <br/> |
|长 ID （盖）：  <br/> |0x00008706  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |日记  <br/> |
   
## <a name="remarks"></a>注解

以协调世界时 (UTC) 活动开始时的时间必须等于**dispidCommonStart** ([PidLidCommonStart](pidlidcommonstart-canonical-property.md)) 属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的日志。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

