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
ms.openlocfilehash: b5bc464bc5a251579d262f5926193b7f7a731728
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563659"
---
# <a name="pidtagnormalizedsubject-canonical-property"></a>PidTagNormalizedSubject 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含与删除任何前缀的邮件主题。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_NORMALIZED_SUBJECT，PR_NORMALIZED_SUBJECT_A，PR_NORMALIZED_SUBJECT_W  <br/> |
|标识符：  <br/> |0x0E1D  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |电子邮件  <br/> |
   
## <a name="remarks"></a>注解

这些属性由消息存储计算，或按以下方式传输提供程序从**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 和**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 属性。
  
- 如果**PR_SUBJECT_PREFIX**存在并且**PR_SUBJECT**初始子， **PR_NORMALIZED_SUBJECT**和关联的属性设置为的**PR_SUBJECT**内容移除了前缀。 
    
- 如果**PR_SUBJECT_PREFIX**是存在此参数，但它并不**PR_SUBJECT**初始子， **PR_SUBJECT_PREFIX**删除和重新计算从**PR_SUBJECT**使用以下规则： 如果**PR_SUBJECT**中包含的字符串开头一到三个非数字字符后跟一个冒号和一个空格，则与冒号和空白一起字符串成为前缀。 数字、 空格和标点的字符不是有效的前缀字符。 
    
- 如果**PR_SUBJECT_PREFIX**不存在，它是从**PR_SUBJECT**使用上一步中所述的规则进行计算。 此属性然后设置为的**PR_SUBJECT**内容移除了前缀。 
    
 **注释**当**PR_SUBJECT_PREFIX**就为空字符串时， **PR_SUBJECT**和此属性是相同。 
  
最后，此属性应为**PR_SUBJECT**关注前缀的一部分。 如果没有前缀，此属性将成为**PR_SUBJECT**相同。
  
 **PR_SUBJECT_PREFIX**和此属性应计算作为[IMAPIProp::SaveChanges](imapiprop-savechanges.md)实现的一部分。 客户端应用程序应不提示其值的[IMAPIProp::GetProps](imapiprop-getprops.md)方法之前已经提交由**IMAPIProp::SaveChanges**呼叫。 
  
Subject 属性均通常较小字符串少于 256 个字符，并且消息存储提供程序不支持这些对象链接和嵌入 (OLE) **IStream**接口的义务。 客户端应始终尝试通过**IMAPIProp**接口访问首先，以及**IStream**仅当返回 MAPI_E_NOT_ENOUGH_MEMORY。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的联系人和个人通讯组列表。
    
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

