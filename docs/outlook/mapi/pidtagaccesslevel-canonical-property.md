---
title: PidTagAccessLevel 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAccessLevel
api_type:
- HeaderDef
ms.assetid: 8f7119c7-ffc3-47cf-aa1b-b4e56bcc5a24
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5138f5d255f6a90d2891fe2cf5ce92513463fa31
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331995"
---
# <a name="pidtagaccesslevel-canonical-property"></a>PidTagAccessLevel 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示客户端对对象的访问级别。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ACCESS_LEVEL  <br/> |
|标识符:  <br/> |0x0FF7  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |访问控制属性  <br/> |
   
## <a name="remarks"></a>备注

对于客户端，此属性是只读的。 它必须是下列值之一：
  
|**值**|**说明**|
|:-----|:-----|
|0x00000000  <br/> |只读  <br/> |
|0x00000001  <br/> |修改  <br/> |
   
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
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

