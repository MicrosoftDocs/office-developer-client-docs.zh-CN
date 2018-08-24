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
ms.openlocfilehash: 063e41bf9fe306b3862e302abb4495ca56e3087b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575453"
---
# <a name="pidtagcorrelate-canonical-property"></a>PidTagCorrelate 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 TRUE，如果发件人的邮件请求邮件系统的相关功能。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CORRELATE  <br/> |
|标识符：  <br/> |0x0E0C  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>注解

此属性用于请求的传入报告的原始发送邮件的相关性。 当传输提供程序遇到已提交的邮件**PR_CORRELATE**设置为 TRUE 时，它将**PR_CORRELATE_MTSID** ([PidTagCorrelateMtsid](pidtagcorrelatemtsid-canonical-property.md)) 属性设置为该邮件的邮件传输系统 (MTS) 标识符。
  
 通过 MTS 标识符，如 X.400，应使用消息支持相关的系统使用**PR_CORRELATE** 。 
  
## <a name="related-resources"></a>相关资源

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

