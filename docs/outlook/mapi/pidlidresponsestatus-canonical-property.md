---
title: PidLidResponseStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidResponseStatus
api_type:
- COM
ms.assetid: e56142fd-204b-497e-83b9-59f9acda6cb4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8c8e284752c6fd47eb7a8f227e2dbfeceebea596
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345757"
---
# <a name="pidlidresponsestatus-canonical-property"></a>PidLidResponseStatus 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定与会者的响应状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidResponseStatus  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x00008218  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>注解

响应状态必须是下表中的值之一。
  
|**响应状态**|**Value**|**说明**|
|:-----|:-----|:-----|
|respNone  <br/> |0x00000000  <br/> |此对象不需要响应。 这就是约会对象和会议响应对象的情况。  <br/> |
|respOrganized  <br/> |0x00000001  <br/> |此会议属于组织者。  <br/> |
|respTentative  <br/> |0x00000002  <br/> |与会者会议上的此值表示与会者暂时接受了会议请求。  <br/> |
|respAccepted  <br/> |0x00000003  <br/> |与会者的会议 t 上的此值表示与会者已接受会议请求。  <br/> |
|respDeclined  <br/> |0x00000004  <br/> |与会者会议上的此值表示与会者已谢绝会议请求。  <br/> |
|respNotResponded  <br/> |0x00000005  <br/> |与会者会议上的此值表示与会者尚未响应。 此值在会议请求、会议更新和会议取消中。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

