---
title: PidTagAccess 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAccess
api_type:
- HeaderDef
ms.assetid: 8c8a882e-62c1-4c57-8c63-ee5849f656b0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b453a7b0cfa04dd94da01089573427a931fb4d4f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316511"
---
# <a name="pidtagaccess-canonical-property"></a>PidTagAccess 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含标志的位掩码, 这些标志指示可用于对象的客户端的操作。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ACCESS  <br/> |
|标识符:  <br/> |0x0FF4  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |访问控制属性  <br/> |
   
## <a name="remarks"></a>注解

对于客户端, 此属性为只读。 它必须是下表中的一个或多个值的按位 "**或**"。 
  
|**Name**|**Value**|**说明**|
|:-----|:-----|:-----|
|MAPI_ACCESS_MODIFY  <br/> |0x00000001  <br/> |写入  <br/> |
|MAPI_ACCESS_READ  <br/> |0x00000002  <br/> |读取  <br/> |
|MAPI_ACCESS_DELETE  <br/> |0x00000004  <br/> |删除  <br/> |
|MAPI_ACCESS_CREATE_HIERARCHY  <br/> |0x00000008  <br/> |在文件夹层次结构中创建子文件夹  <br/> |
|MAPI_ACCESS_CREATE_CONTENTS  <br/> |0x00000010  <br/> |创建内容邮件  <br/> |
|MAPI_ACCESS_CREATE_ASSOCIATED  <br/> |0x00000020  <br/> |创建关联的内容邮件  <br/> |
   
MAPI_ACCESS_DELETE、MAPI_ACCESS_MODIFY 和 MAPI_ACCESS_READ 标志位于 folder 和 message 对象以及内容表和关联的内容表中的**PR_ACCESS**列中。 MAPI_ACCESS_CREATE_ASSOCIATED、MAPI_ACCESS_CREATE_CONTENTS 和 MAPI_ACCESS_CREATE_HIERARCHY 标志仅在 folder 对象上找到。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
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

