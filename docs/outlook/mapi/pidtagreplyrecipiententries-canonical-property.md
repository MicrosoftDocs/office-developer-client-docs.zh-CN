---
title: PidTagReplyRecipientEntries 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReplyRecipientEntries
api_type:
- COM
ms.assetid: a903fd22-a3f2-464f-99b0-c087e211b124
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 000132f052abb666ae844ec7d21b59c85ab43613
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355053"
---
# <a name="pidtagreplyrecipiententries-canonical-property"></a>PidTagReplyRecipientEntries 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于获取回复的收件人的条目标识符大小数组。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REPLY_RECIPIENT_ENTRIES  <br/> |
|标识符:  <br/> |0x004F  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

此属性包含 [FLATENTRYLIST](flatentrylist.md) 结构，而不是多值属性。 
  
当此属性不存在时，答复将仅发送给[PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md) PR_SENDER_ENTRYID (标识) 用户。  定义此PR_REPLY_RECIPIENT_NAMES ( [PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) 属性时，答复将发送给这两个属性标识的所有收件人。 传输提供程序使用这些属性覆盖常见的回复逻辑。
  
如果设置了此属性或 **PR_REPLY_RECIPIENT_NAMES** 属性，则还必须设置另一个属性。 这些属性必须包含相同数量的收件人，并且必须按相同的顺序包含它们。 如果未能遵守这些要求，可能会导致不可预知的结果。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许对电子邮件执行的属性和操作。
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
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

