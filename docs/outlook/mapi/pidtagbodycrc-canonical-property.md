---
title: PidTagBodyCrc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagBodyCrc
api_type:
- HeaderDef
ms.assetid: 6efe9dc3-e988-4042-ab02-2863b5e0f294
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 416486c3b06c485a1fa6525b54c37a6e0d23f56c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415178"
---
# <a name="pidtagbodycrc-canonical-property"></a>PidTagBodyCrc 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含对邮件文本 (CRC) 循环冗余检查。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_BODY_CRC  <br/> |
|标识符:  <br/> |0x0E1C  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>备注

邮件存储可以使用生成值的任何 CRC PT_LONG值。 它必须在首次设置 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性时以及以后对其进行修改时，在 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)方法中计算此属性。
  
客户端应用程序使用 **PR_BODY_CRC** 帮助比较包含在属性或变量PR_BODY中的邮件文本字符串。  使用此属性，客户端可以快速且轻松地检测邮件文本何时发生更改。 通过使用 PR_BODY_CRC而不是从邮件存储PR_BODY它和本地版本进行比较，可以实现显著的性能提升。 
  
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

