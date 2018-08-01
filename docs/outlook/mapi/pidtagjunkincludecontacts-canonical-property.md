---
title: PidTagJunkIncludeContacts 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagJunkIncludeContacts
api_type:
- HeaderDef
ms.assetid: 25368f6c-4fba-4381-840c-ca122bd31b5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4dde93bbec2594804ab18a3ee4eb3e116a57e528
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777783"
---
# <a name="pidtagjunkincludecontacts-canonical-property"></a>PidTagJunkIncludeContacts 规范属性

  
  
**适用于**： Outlook 
  
指示是否在联系人文件夹中的联系人的电子邮件地址被视为特殊相对于垃圾邮件筛选器。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_JUNK_INCLUDE_CONTACTS  <br/> |
|标识符：  <br/> |0x6100  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="remarks"></a>说明

如果设置为"0x00000001"，这些电子邮件地址必须填充垃圾电子邮件规则限制的"受信任的"联系人电子邮件地址部分以便从这些地址的邮件将被视为"非垃圾邮件"。 如果设置为"0x00000000"，从联系人文件夹的电子邮件地址必须添加到垃圾邮件规则，并且该规则的一部分必须为 NULL。
  
如果此属性的值为"0x00000001"并添加了的联系人如果具有未在垃圾邮件规则的受信任的联系人部分中包含的电子邮件地址，则这些电子邮件地址必须添加到限制。 如果此属性为"0x00000000"，则不不需要任何操作。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
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

