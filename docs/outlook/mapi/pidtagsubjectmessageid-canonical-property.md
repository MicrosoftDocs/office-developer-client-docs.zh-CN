---
title: PidTagSubjectMessageId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubjectMessageId
api_type:
- COM
ms.assetid: d4b1a087-0986-467a-aaa9-fc643f7c56fc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7bd5a030d11577c2afabb8a2253cf4f6129814cc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407100"
---
# <a name="pidtagsubjectmessageid-canonical-property"></a>PidTagSubjectMessageId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含从生成报告的邮件复制的二进制值。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SUBJECT_IPM  <br/> |
|标识符:  <br/> |0x0038  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

此属性（如 **PR_REPORT_TAG** ([PidTagReportTag](pidtagreporttag-canonical-property.md)) 属性）可用于将报表与原始邮件关联。 
  
## <a name="related-resources"></a>相关资源

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

