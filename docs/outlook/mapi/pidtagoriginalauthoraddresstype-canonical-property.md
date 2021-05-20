---
title: PidTagOriginalAuthorAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorAddressType
api_type:
- COM
ms.assetid: 7cdedb1a-e441-469b-be50-2f18203eb30d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 596e416624fb6f2bf1fdaef64c2179feb7787815
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431412"
---
# <a name="pidtagoriginalauthoraddresstype-canonical-property"></a>PidTagOriginalAuthorAddressType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件第一个版本的作者的地址类型，即转发或答复前的邮件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_AUTHOR_ADDRTYPE、PR_ORIGINAL_AUTHOR_ADDRTYPE_A、PR_ORIGINAL_AUTHOR_ADDRTYPE_W  <br/> |
|标识符:  <br/> |0x0079  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |服务器  <br/> |
   
## <a name="remarks"></a>备注

这些属性是邮件作者的地址属性示例。 首次提交邮件时，客户端应用程序应将此属性设置为 **PR_SENDER_ADDRTYPE** ([PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)) 属性的值。 转发或答复邮件时从不更改。
  
原始作者属性允许保留来自本地邮件域外部的信息。 当邮件从另一个邮件域（如 Internet）到达时，这些属性提供了一种确保原始信息不会丢失的方法。
  
## <a name="related-resources"></a>相关资源

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

