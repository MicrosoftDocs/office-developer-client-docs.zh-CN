---
title: PidLidSideEffects 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSideEffects
api_type:
- COM
ms.assetid: 90d601d9-5eeb-40b6-885d-ccd8a95ae322
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fa29a55a5fc2ce89e125909d13a2c14a347ef831
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594023"
---
# <a name="pidlidsideeffects-canonical-property"></a>PidLidSideEffects 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
控制 message 对象时如何处理由客户端执行最终用户输入。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSideEffects  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x00008510  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |运行时配置  <br/> |
   
## <a name="remarks"></a>注解

必须设置为按位或零个或多个以下标志。
  
|**名称**|**值**|**说明**|
|:-----|:-----|:-----|
|seOpenToDelete  <br/> |0x0001  <br/> |Message 对象时删除需要其他处理。  <br/> |
|seNoFrame  <br/> |0x0008  <br/> |没有用户界面相关联的消息对象。  <br/> |
|seCoerceToInbox  <br/> |0x0010  <br/> |Message 对象时移动或复制到**PR_CONTAINER_CLASS** ([PidTagContainerClass](pidtagcontainerclass-canonical-property.md)) 属性值为"IPF 一个 folder 对象上需要其他处理。请注意"。  <br/> |
|seOpenTocopy  <br/> |0x0020  <br/> |Message 对象复制到另一个文件夹时需要其他处理。  <br/> |
|seOpenToMove  <br/> |0x0040  <br/> |将移动到另一个文件夹时，将 message 对象上需要其他处理。  <br/> |
|seOpenForCtxMenu  <br/> |0x0100  <br/> |Message 对象时向最终用户显示动词需要其他处理。  <br/> |
|seCannotUndoDelete  <br/> |0x0400  <br/> |无法撤消删除操作，必须设置，除非设置"seOpenToDelete"。  <br/> |
|seCannotUndoCopy  <br/> |0x0800  <br/> |无法撤消复制操作，必须设置，除非设置"seOpenTocopy"。  <br/> |
|seCannotUndoMove  <br/> |0x1000  <br/> |无法撤消移动操作，必须设置，除非设置"seOpenToMove"。  <br/> |
|seHasScript  <br/> |0x2000  <br/> |Message 对象包含最终用户脚本。  <br/> |
|seOpenToPermDelete  <br/> |0x4000  <br/> |永久删除 message 对象需要进行其他处理。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定的属性和约会、 会议请求和响应消息的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

