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
ms.openlocfilehash: 55da942e59c619dd384bef58349aa3a00d4a6d8c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571470"
---
# <a name="pidtagbodycrc-canonical-property"></a>PidTagBodyCrc 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含消息文本在一个循环冗余检查 (CRC) 值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_BODY_CRC  <br/> |
|标识符：  <br/> |0x0E1C  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>注解

消息存储库可以使用任何 CRC 算法生成 PT_LONG 值。 它必须时**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性已设置第一次，只要随后已修改计算此属性作为[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法的一部分。
  
客户端应用程序使用**PR_BODY_CRC**帮助比较**PR_BODY**属性或其变量中包含的消息文本字符串。 使用此属性，客户端可以快速、 方便地检测何时更改消息文本。 它可以使用而不是从消息存储中获取**PR_BODY**并将其与本地版本进行比较**PR_BODY_CRC**实现显著提高性能。 
  
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

