---
title: PidTagJunkAddRecipientsToSafeSendersList 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagJunkAddRecipientsToSafeSendersList
api_type:
- HeaderDef
ms.assetid: 78543caa-e6ec-4ac7-bfdd-70c56f8fd955
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3a87beaa3873b5ccb449e5b1497262bad5bf1497
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394011"
---
# <a name="pidtagjunkaddrecipientstosafesenderslist-canonical-property"></a>PidTagJunkAddRecipientsToSafeSendersList 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示要添加到安全发件人列表的邮件收件人。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_JUNK_ADD_RECIPS_TO_SSL  <br/> |
|标识符：  <br/> |0x6103  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="remarks"></a>说明

如果存在此参数，则此属性必须设置为 0 或 1。 1 表示邮件收件人是要添加到安全发件人列表。 0 值表示邮件收件人的不是要添加到安全发件人列表。
  
如果此属性的值为 1，则的电子邮件收件人的 SMTP 地址必须添加到受信任的发件人子句的垃圾邮件规则条件。 如果此属性为 0，则不不需要任何操作。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许处理的允许/阻止列表，并确定的垃圾邮件。
    
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

