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
  
包含通常指示对邮件执行某些操作的主题前缀，例如"FW："用于转发。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SUBJECT_PREFIX、PR_SUBJECT_PREFIX_A、PR_SUBJECT_PREFIX_W  <br/> |
|标识符:  <br/> |0x003D  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

建议在所有邮件对象上使用这些属性。 
  
主题前缀由一个或多个字母数字字符组成，后跟冒号和空格 (作为前缀前缀) 。 冒号之前不得包含任何非字母数字字符。 没有前缀可以表示为空字符串或此属性未设置。 
  
如果显式设置这些属性，则字符串的长度可以是任意长度并使用任何字母数字字符，但它必须与 **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性开头的子字符串匹配。 如果发件人未设置这些属性并且必须计算这些属性，则其内容将受到限制。 计算前缀的规则是PR_SUBJECT必须以一、 (字母开头，) 后跟冒号和空格。  如果在 PR_SUBJECT 开头找到这样的子字符串，则它将成为这些属性的字符串 (并且仍保留在PR_SUBJECT) 。  否则，这些属性将保持未设置状态。 
  
这些属性 **和** PR_NORMALIZED_SUBJECT ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 应作为 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 实现一部分进行计算。 在 **IMAPIProp：：SaveChanges 调用提交 IMAPIProp：：SaveChanges** 之前，客户端不应提示 [IMAPIProp：：GetProps](imapiprop-getprops.md)提供其值。 
  
主题属性通常是少于 256 个字符的小字符串，并且邮件存储提供程序不必支持其上的 OLE **IStream** 接口。 客户端应始终首先尝试通过 **IMAPIProp** 接口访问，并仅在返回 IStream **MAPI_E_NOT_ENOUGH_MEMORY使用****IStream。** 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许对电子邮件对象执行的属性和操作。
    
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

