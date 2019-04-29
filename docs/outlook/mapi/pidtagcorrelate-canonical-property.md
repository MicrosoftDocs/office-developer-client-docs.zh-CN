---
title: PidTagCorrelate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagCorrelate
api_type:
- HeaderDef
ms.assetid: be34993e-ffcc-47f5-b2d4-95ffa707bc5c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea217808a163c7f16bbaa3c5a959fd32c8cbe10c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405217"
---
# <a name="pidtagcorrelate-canonical-property"></a>PidTagCorrelate 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果邮件的发件人请求邮件系统的关联功能, 则该参数包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CORRELATE  <br/> |
|标识符:  <br/> |0x0E0C  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>说明

此属性用于请求与原始已发送邮件的传入报告的关联。 当传输提供程序遇到**PR_CORRELATE**设置为 TRUE 的已提交邮件时, 它会将**PR_CORRELATE_MTSID** ([PidTagCorrelateMtsid](pidtagcorrelatemtsid-canonical-property.md)) 属性设置为该邮件的邮件传输系统 (MTS) 标识符。
  
 **PR_CORRELATE**应与支持按 MTS 标识符的关联的邮件系统结合使用, 例如, X. 400。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

