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
ms.openlocfilehash: 7e61e98d1db1ab3acb958da353d8d22870937632
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328712"
---
# <a name="pidtagjunkincludecontacts-canonical-property"></a>PidTagJunkIncludeContacts 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示是否对"联系人"文件夹中的联系人的电子邮件地址进行特殊处理，以考虑垃圾邮件筛选器。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_JUNK_INCLUDE_CONTACTS  <br/> |
|标识符:  <br/> |0x6100  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="remarks"></a>备注

如果设置为"0x00000001"，这些电子邮件地址必须填充垃圾邮件规则限制的"受信任的"联系人电子邮件地址部分，这样来自这些地址的邮件将被视为"非垃圾邮件"。 如果设置为"0x00000000"，则不得将"联系人"文件夹中的电子邮件地址添加到垃圾邮件规则中，并且该规则部分必须为 NULL。
  
如果此属性存在值"0x00000001"，并且添加的联系人的电子邮件地址尚未包含在垃圾邮件规则的受信任的联系人部分中，则必须将那些电子邮件地址添加到限制中。 如果此属性为"0x00000000"，则无需任何操作。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许/阻止列表的处理和垃圾邮件的确定。
    
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

