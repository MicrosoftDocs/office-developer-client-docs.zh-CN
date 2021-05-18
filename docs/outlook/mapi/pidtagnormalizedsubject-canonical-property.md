---
title: PidTagNormalizedSubject 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNormalizedSubject
api_type:
- HeaderDef
ms.assetid: 2000e6e8-d908-4814-8093-28f8011250c8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 54a0f438dacc8a1c7838eb538ec05c5c263f1b0a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329272"
---
# <a name="pidtagnormalizedsubject-canonical-property"></a>PidTagNormalizedSubject 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含已删除任何前缀的邮件主题。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_NORMALIZED_SUBJECT、PR_NORMALIZED_SUBJECT_A、PR_NORMALIZED_SUBJECT_W  <br/> |
|标识符:  <br/> |0x0E1D  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>备注

这些属性由 PR_SUBJECT ([PidTagSubject](pidtagsubject-canonical-property.md) **)** 和 **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 属性的邮件存储或传输提供程序计算。
  
- 如果 **PR_SUBJECT_PREFIX** 存在，并且是 **PR_SUBJECT****的初始子** 字符串，PR_NORMALIZED_SUBJECT 和关联的属性将设置为 PR_SUBJECT，并删除前缀。  
    
- 如果 **PR_SUBJECT_PREFIX** 存在，但它不是 **PR_SUBJECT** 的初始子字符串，则使用下列规则从 **PR_SUBJECT** 中删除和重新计算 **PR_SUBJECT_PREFIX：** 如果 PR_SUBJECT 中包含的字符串以一到三个非数字字符开头，后跟冒号和空格，则包含冒号和空白的字符串将成为前缀。  数字、空白和标点符号无效前缀字符。 
    
- 如果 **PR_SUBJECT_PREFIX** 不存在，则使用上一 **PR_SUBJECT概述的规则** 从以下位置计算。 然后，将此属性设置为前缀 **PR_SUBJECT** 的内容。 
    
 **注意** 当 **PR_SUBJECT_PREFIX** 为空字符串 **时，PR_SUBJECT** 和此属性相同。 
  
最后，此属性应该是前缀 **PR_SUBJECT部分。** 如果没有前缀，此属性将变为与 PR_SUBJECT **相同**。
  
 **PR_SUBJECT_PREFIX** 和此属性应作为 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 实现一部分进行计算。 在 **IMAPIProp：：SaveChanges 调用提交 IMAPIProp：：SaveChanges** 方法之前，客户端应用程序不应提示 [IMAPIProp：：GetProps](imapiprop-getprops.md)方法提供其值。 
  
主题属性通常是少于 256 个字符的小字符串，邮件存储提供程序不必支持对象链接和嵌入 (OLE) **IStream** 接口。 客户端应始终首先尝试通过 **IMAPIProp** 接口访问，并且仅在返回 IStream 时MAPI_E_NOT_ENOUGH_MEMORY **IStream。** 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表允许的属性和操作。
    
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

