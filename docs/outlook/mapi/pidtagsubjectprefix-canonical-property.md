---
title: PidTagSubjectPrefix 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubjectPrefix
api_type:
- COM
ms.assetid: 07fcb881-d873-45bf-b048-30f41d0d8d85
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8257c3c3583072d16e96e6ea9bba4632fc78f9ef
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339226"
---
# <a name="pidtagsubjectprefix-canonical-property"></a>PidTagSubjectPrefix 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含主题前缀, 通常指示对邮件的某些操作, 例如, 用于转发的 "FW:"。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SUBJECT_PREFIX、PR_SUBJECT_PREFIX_A、PR_SUBJECT_PREFIX_W  <br/> |
|标识符:  <br/> |0x003D  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

对于所有邮件对象, 建议使用这些属性。 
  
主题前缀由一个或多个字母数字字符组成, 后跟一个冒号和一个空格 (作为前缀的一部分)。 冒号前不能包含任何非字母数字字符。 不能使用空字符串或未设置该属性来表示前缀。 
  
如果显式设置了这些属性, 则字符串可为任意长度并使用任何字母数字字符, 但它必须与**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性的开头的子字符串相匹配。 如果这些属性不是由发件人设置的, 并且必须进行计算, 则它们的内容更受限制。 用于计算前缀的规则是, **PR_SUBJECT**必须以一个、两个或三个字母开头 (仅限字母), 后跟一个冒号和一个空格。 如果在**PR_SUBJECT**的开头找到此类子字符串, 则该子串将成为这些属性的字符串 (也停留在**PR_SUBJECT**的开头)。 否则, 这些属性将保持未设置。 
  
应将这些属性和**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 作为[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)实现的一部分进行计算。 客户端不应提示[IMAPIProp:: GetProps](imapiprop-getprops.md)获取其值, 直到它们已被**IMAPIProp:: SaveChanges**调用提交。 
  
subject 属性通常是少于256个字符的较小字符串, 而邮件存储区提供程序并不是对其支持 OLE **IStream**接口的义务。 客户端应始终先尝试通过**IMAPIProp**接口访问, 并且只有在返回**MAPI_E_NOT_ENOUGH_MEMORY**时才会转到**IStream** 。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
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

