---
title: PidTagOriginalSubject 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSubject
api_type:
- COM
ms.assetid: 8668ba4f-3236-4a87-a5aa-9cf7eea3d87b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cf81a5b4c10cb7bff5f03a1b25d11bbaa8ff277
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777971"
---
# <a name="pidtagoriginalsubject-canonical-property"></a>PidTagOriginalSubject 规范属性

  
  
**适用于**： Outlook 
  
包含用于报告有关邮件原始邮件的主题。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_SUBJECT，PR_ORIGINAL_SUBJECT_A，PR_ORIGINAL_SUBJECT_W  <br/> |
|标识符：  <br/> |0x0049  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

这些属性最初设置为相同的值的**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性。
  
Subject 属性均通常较小字符串少于 256 个字符，并且消息存储提供程序不支持这些对象链接和嵌入 (OLE) **IStream**接口的义务。 客户端应始终尝试通过**IMAPIProp**接口访问首先，以及**IStream**仅当返回**MAPI_E_NOT_ENOUGH_MEMORY** 。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 同步服务器和客户端之间的消息对象数据的句柄。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和电子邮件消息对象在允许的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

