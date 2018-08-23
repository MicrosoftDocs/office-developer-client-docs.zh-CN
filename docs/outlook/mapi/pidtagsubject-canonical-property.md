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
ms.openlocfilehash: 9d37e4ee32cb5db623cece3061012ae4df0173a8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586940"
---
# <a name="pidtagsubject-canonical-property"></a>PidTagSubject 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含邮件的完整主题。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SUBJECT，PR_SUBJECT_A，PR_SUBJECT_W  <br/> |
|标识符：  <br/> |0x0037  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

建议对所有的消息对象都使用这些属性。 
  
这些属性将始终的完整主题文本，即前缀和规范化的主题串联。 如果没有前缀，规范化的主题应与相同主题。 消息存储或传输提供程序使用这些属性和**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 属性来计算使用规则规范化的主题所述在**PR_NORMALIZED_SUBJECT** ([下PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))。
  
Subject 属性均通常较小字符串少于 256 个字符，并且消息存储提供程序不支持这些**IStream**接口的义务。 客户端应始终尝试通过**IMAPIProp**接口访问首先，以及**IStream**仅当返回**MAPI_E_NOT_ENOUGH_MEMORY** 。 
  
对于报表，此属性包含一个 string，指示邮件发生前面的原始消息的主题。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
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

