---
title: PidTagSwappedToDoData 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSwappedToDoData
api_type:
- COM
ms.assetid: d2a82fc8-de5d-4819-906e-b8314fd06ea0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dedb60c5356e1dbb6d35f27372a09c152da0fed0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778490"
---
# <a name="pidtagswappedtododata-canonical-property"></a>PidTagSwappedToDoData 规范属性

  
  
**适用于**： Outlook 
  
维护第二个组不会影响已标记的状态的消息对象的属性值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SWAPPED_TODO_DATA  <br/> |
|标识符：  <br/> |0x0E2D  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 非可传送  <br/> |
   
## <a name="remarks"></a>说明

作为辅助标志存储位置，如果发件人标志或发件人提醒受支持，此结构提供中用来存储的所有发件人标志中支持的信息的标记协议与相关属性和所有的位置属性与提醒设置协议有关支持的发件人提醒而无需公开的标志发件人或收件人的邮件的发件人提醒信息。
  
同样，此结构提供中用于存储所有到信息性标记协议有关的属性的受支持的收件人的标志和提醒设置协议与相关的属性的受支持的收件人的位置以前发送的消息的提醒。
  
有关此属性的详细信息，请参阅[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定的属性和与标记的操作。
    
[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定属性和电子邮件和其他对象提醒的交互模型。
    
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

