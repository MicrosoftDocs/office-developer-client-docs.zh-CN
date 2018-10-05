---
title: PidLidMeetingType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidMeetingType
api_type:
- COM
ms.assetid: 290b290c-7836-4a7e-bf1a-8d0225a07e56
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d2b00c67984d090274a17028ee74e46bee482e2b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399632"
---
# <a name="pidlidmeetingtype-canonical-property"></a>PidLidMeetingType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示会议请求或会议更新的类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidMeetingType  <br/> |
|属性进行设置：  <br/> |PSETID_Meeting  <br/> |
|长 ID （盖）：  <br/> |0x00000026  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>说明

此属性的值必须设置为下列选项之一：
  
|**属性**|**值**|**说明**|
|:-----|:-----|:-----|
|mtgEmpty  <br/> |0x00000000  <br/> |未指定。  <br/> |
|mtgRequest  <br/> |0x00000001  <br/> |初始的会议请求。  <br/> |
|mtgFull  <br/> |0x00010000  <br/> |完全更新。  <br/> |
|mtgInfo  <br/> |0x00020000  <br/> |信息性更新。  <br/> |
|mtgOutOfDate  <br/> |0x00080000  <br/> |此之后收到较新的会议请求或会议更新。  <br/> |
|mtgDelegatorCopy  <br/> |0x00100000  <br/> |这是设置 delegator 副本时委托处理与会议相关的对象。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

