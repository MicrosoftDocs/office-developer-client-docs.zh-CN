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
ms.openlocfilehash: f30a5848e07de03e61d3a63188aa7b608504ff24
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573731"
---
# <a name="pidtagsensitivity-canonical-property"></a>PidTagSensitivity 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个值，指示邮件发件人的邮件的敏感度的平均意见。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SENSITIVITY  <br/> |
|标识符：  <br/> |0x0036  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

建议消息对象公开此属性。
  
此属性可以具有完全下列值之一：
  
SENSITIVITY_NONE 
  
> 邮件有任何特殊的敏感度。
    
SENSITIVITY_PERSONAL 
  
> 消息为个人。
    
SENSITIVITY_PRIVATE 
  
> 邮件是专用的。
    
SENSITIVITY_COMPANY_CONFIDENTIAL 
  
> 邮件被指定公司机密。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
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

