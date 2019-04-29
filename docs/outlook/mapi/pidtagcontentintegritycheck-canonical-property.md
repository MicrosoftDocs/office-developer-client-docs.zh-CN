---
title: PidTagContentIntegrityCheck 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentIntegrityCheck
api_type:
- HeaderDef
ms.assetid: c7f10b8a-6b20-44cf-bde6-8d2b711c1c14
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 30ed8053c9c3d77f4831da37ddd2456ad0564a5a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415724"
---
# <a name="pidtagcontentintegritycheck-canonical-property"></a>PidTagContentIntegrityCheck 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 ASN. 1 内容完整性检查值, 允许邮件发件人将邮件内容泄露给未授权的收件人。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTENT_INTEGRITY_CHECK  <br/> |
|标识符:  <br/> |0x0C00  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>说明

此属性提供对邮件内容的不可否认性的提供。 与**PR_MESSAGE_TOKEN** ([PidTagMessageToken](pidtagmessagetoken-canonical-property.md)) 结合使用, 可确保邮件的内容在其目标处不变。
  
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

