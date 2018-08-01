---
title: PidTagPriority 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPriority
api_type:
- COM
ms.assetid: 0f3a628f-5f8e-4716-98cc-868bd3400ba9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 67f482e347db1b69a248c542f2cb172c41d6f9f1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778051"
---
# <a name="pidtagpriority-canonical-property"></a>PidTagPriority 规范属性

  
  
**适用于**： Outlook 
  
包含一条消息的相对优先级。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PRIORITY  <br/> |
|标识符：  <br/> |0x0026  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>说明

此属性和**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md)) 属性不能混淆。 重要性表示到用户的值，而优先级表示订单设计 サ 频率邮件应发送的消息的系统软件的速度。 更高的优先级通常指示较高的开销。 更高重要性通常是与用户界面的不同显示相关联。
  
报告消息的优先级应与原始邮件报告的优先级相同。
  
此属性可以具有完全下列值之一：
  
PRIO_NONURGENT 
  
> 该邮件不紧急。
    
PRIO_NORMAL 
  
> 邮件具有正常优先级。
    
PRIO_URGENT 
  
> 紧急邮件。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象在允许的操作。
    
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

