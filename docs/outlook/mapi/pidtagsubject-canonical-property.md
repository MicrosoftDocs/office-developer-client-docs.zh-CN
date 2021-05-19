---
title: PidTagSubject 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubject
api_type:
- COM
ms.assetid: aa7ba4d9-c5e0-4ce7-a34e-65f675223bc9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0cf9e9f8c10f8d27bd174b8b6f2bf19812dc269d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339254"
---
# <a name="pidtagsubject-canonical-property"></a>PidTagSubject 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件的完整主题。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SUBJECT、PR_SUBJECT_A、PR_SUBJECT_W  <br/> |
|标识符:  <br/> |0x0037  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

建议在所有邮件对象上使用这些属性。 
  
这些属性始终是完整的主题文本，即前缀和规范化主题的串联。 如果没有前缀，则规范化主题应与主题相同。 邮件存储或传输提供程序使用这些属性和 **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 属性，使用 PR_NORMALIZED_SUBJECT ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md) **)** 下所述的规则计算规范化主题。
  
主题属性通常是少于 256 个字符的小字符串，邮件存储提供程序不必支持 **其上的 IStream** 接口。 客户端应始终首先尝试通过 **IMAPIProp** 接口访问，并仅在返回 IStream  MAPI_E_NOT_ENOUGH_MEMORY **IStream。** 
  
对于报告，此属性包含原始邮件的主题前面有一个字符串，指示邮件发生了什么。
  
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
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

