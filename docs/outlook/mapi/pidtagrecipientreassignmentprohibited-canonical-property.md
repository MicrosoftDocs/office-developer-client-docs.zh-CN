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
ms.openlocfilehash: 0176485ca9b84260176e3be8ec9c8f42cf755cba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778160"
---
# <a name="pidtagrecipientreassignmentprohibited-canonical-property"></a>PidTagRecipientReassignmentProhibited 规范属性

  
  
**适用于**： Outlook 
  
指定是否添加其他收件人转发的邮件时, 禁止的电子邮件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECIPIENT_REASSIGNMENT_PROHIBITED  <br/> |
|标识符：  <br/> |0x002B  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>说明

基于电子邮件的**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) 值设置此属性。 如果**PR_SENSITIVITY**设置为"0x00000000"（正常） 或"0x00000003"（机密），则此属性必须设置为"0x00"或不存在这意味着该添加允许附加的或不同的收件人添加到电子邮件。 如果对象的**PR_SENSITIVITY**设置为"0x00000001"（个人） 或"0x00000002:uc"（专用） 电子邮件，必须将此属性设置"0x01"以防添加其他或不同之处的转接通过此电子邮件的收件人。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件中允许的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

