---
title: PidTagRtfSyncBodyTag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfSyncBodyTag
api_type:
- COM
ms.assetid: 2dab5018-4214-4162-93bc-e5565f3ac24c
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bad754d21652d3f5278a6dad3ec06f4a0b533036
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778270"
---
# <a name="pidtagrtfsyncbodytag-canonical-property"></a>PidTagRtfSyncBodyTag 规范属性

  
  
**适用于**： Outlook 
  
包含出现在消息文本的开头的有效字符。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_RTF_SYNC_BODY_TAG，PR_RTF_SYNC_BODY_TAG_A，PR_RTF_SYNC_BODY_TAG_W  <br/> |
|标识符:  <br/> |0x1008  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |MAPI 邮件  <br/> |
   
## <a name="remarks"></a>备注

[RTFSync](rtfsync.md)函数使用的文本标记指示消息文本的开头。 修改文本时，标记用于查找以前的文本的开头。 
  
这些属性是富文本格式辅助属性。 他们使用**RTFSync**函数并不能直接使用客户端应用程序。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 进行编码和解码为有效的流表示形式的消息和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

