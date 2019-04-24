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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350923"
---
# <a name="pidtagbodycrc-canonical-property"></a>PidTagBodyCrc 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在邮件文本中包含循环冗余检查 (CRC) 值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_BODY_CRC  <br/> |
|标识符:  <br/> |0x0E1C  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>注解

邮件存储区可以使用任何可生成 PT_LONG 值的 CRC 算法。 如果首次设置了**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性, 并在随后对其进行了修改, 则它必须将此属性作为[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法的一部分进行计算。
  
客户端应用程序使用**PR_BODY_CRC**来协助比较**PR_BODY**属性或其变体中包含的邮件文本字符串。 使用此属性, 客户端可以快速且轻松地检测邮件文本的更改时间。 通过使用**PR_BODY_CRC** (而不是从邮件存储区获取**PR_BODY** , 并将其与本地版本进行比较) 可以显著提高性能。 
  
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

