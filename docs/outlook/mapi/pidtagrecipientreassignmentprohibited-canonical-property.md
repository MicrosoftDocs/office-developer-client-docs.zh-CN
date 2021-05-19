---
title: PidTagRecipientReassignmentProhibited 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 8636774b-1fff-4b29-bc12-4d0bd63fcba2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2dac2cb1d40fadbe0cad67b144891b0ece54aae9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341109"
---
# <a name="pidtagrecipientreassignmentprohibited-canonical-property"></a>PidTagRecipientReassignmentProhibited 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定在转发邮件时是否禁止为电子邮件添加其他收件人。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECIPIENT_REASSIGNMENT_PROHIBITED  <br/> |
|标识符:  <br/> |0x002B  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

此属性根据电子邮件的默认值PR_SENSITIVITY ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) 值。  如果 **PR_SENSITIVITY** 设置为"0x00000000" (普通) 或"0x00000003" (机密) ，则必须将此属性设置为"0x00"，或不存在允许向电子邮件添加其他或不同收件人的含义。 如果电子邮件对象的 **PR_SENSITIVITY** 设置为"0x00000001" (个人) 或"0x00000002" (专用) ，则必须将此属性设置为"0x01"以防止通过转发添加此电子邮件的其他或不同收件人。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许对电子邮件执行的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

