---
title: PidTagAlternateRecipient 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAlternateRecipient
api_type:
- HeaderDef
ms.assetid: df787b60-2f53-42ac-89b5-1b52c906f472
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c3ebb520de8929185a8b67b585976b4d768727b4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22562951"
---
# <a name="pidtagalternaterecipient-canonical-property"></a>PidTagAlternateRecipient 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含由原始收件人指定的备用收件人的项标识符的列表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ALTERNATE_RECIPIENT  <br/> |
|标识符：  <br/> |0x3A01  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>注解

此属性用于自动转发邮件。 它包含的备用收件人[FLATENTRYLIST](flatentrylist.md)结构。 如果不允许自动转接，或者如果已不指定任何备用收件人，则生成原件报表。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理顺序和客户端和服务器之间的数据传输的流。
    
[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。
    
[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> 进行编码和解码为有效的流表示形式的消息和附件对象。
    
### <a name="header-files"></a>头文件

Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[FLATENTRYLIST](flatentrylist.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

