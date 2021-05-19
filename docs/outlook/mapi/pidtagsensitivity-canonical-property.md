---
title: PidTagSensitivity 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSensitivity
api_type:
- COM
ms.assetid: 5b678475-f2a8-4831-ad68-11654e09c821
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eab8ce71d28a672d7069a1c16da5cd2cc2e149f7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342502"
---
# <a name="pidtagsensitivity-canonical-property"></a>PidTagSensitivity 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个值，该值指示邮件发件人对邮件的敏感度的意见。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SENSITIVITY  <br/> |
|标识符:  <br/> |0x0036  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

建议邮件对象公开此属性。
  
此属性可以正好具有下列值之一：
  
SENSITIVITY_NONE 
  
> 邮件没有特殊的敏感度。
    
SENSITIVITY_PERSONAL 
  
> 邮件是个人邮件。
    
SENSITIVITY_PRIVATE 
  
> 邮件是私有的。
    
SENSITIVITY_COMPANY_CONFIDENTIAL 
  
> 邮件被指定为公司机密。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
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

