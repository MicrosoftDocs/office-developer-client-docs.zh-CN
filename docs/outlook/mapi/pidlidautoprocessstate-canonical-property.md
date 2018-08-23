---
title: PidLidAutoProcessState 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAutoProcessState
api_type:
- COM
ms.assetid: 9e724af6-5b56-4eb3-a94c-1015ebce197c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b7e2db23b43383ca405ac58216b94a23d3257fe1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578337"
---
# <a name="pidlidautoprocessstate-canonical-property"></a>PidLidAutoProcessState 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指定的电子邮件的自动处理中所使用的选项。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSniffState  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x0000851A  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

该属性可能不存在，在这种情况下使用"0x00000000"的默认值。 如果设置，此属性必须设置为下表中的值之一。
  
|**值**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |不自动处理邮件。  <br/> |
|0x00000001  <br/> |自动处理邮件，或打开邮件时。  <br/> |
|0x00000002  <br/> |仅当打开邮件时处理该消息。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

