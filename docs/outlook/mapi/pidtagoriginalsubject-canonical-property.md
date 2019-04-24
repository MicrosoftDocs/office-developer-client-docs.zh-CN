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
ms.openlocfilehash: de957c33165cc96eec82bf95c8f292c5b323676a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331141"
---
# <a name="pidtagoriginalsubject-canonical-property"></a>PidTagOriginalSubject 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含原始邮件的主题, 以供在有关邮件的报告中使用。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_SUBJECT、PR_ORIGINAL_SUBJECT_A、PR_ORIGINAL_SUBJECT_W  <br/> |
|标识符:  <br/> |0x0049  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

这些属性最初设置为与**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性相同的值。
  
subject 属性通常是少于256个字符的较小字符串, 而邮件存储区提供程序并不是支持其上的对象链接和嵌入 (OLE) **IStream**接口的义务。 客户端应始终先尝试通过**IMAPIProp**接口访问, 并且只有在返回**MAPI_E_NOT_ENOUGH_MEMORY**时才会转到**IStream** 。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理服务器和客户端之间的同步邮件对象数据。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定在电子邮件对象上允许的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

