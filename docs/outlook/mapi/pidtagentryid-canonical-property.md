---
title: PidTagEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagEntryId
api_type:
- HeaderDef
ms.assetid: ca02e873-c2d2-4d58-8df8-c05fbcdc8fba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: feb34cdbf8ba917936c3272bcaaf6eff040ddc3a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387788"
---
# <a name="pidtagentryid-canonical-property"></a>PidTagEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含用于打开和编辑特定的 MAPI 对象的属性的 MAPI 条目标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ENTRYID  <br/> |
|标识符：  <br/> |0x0FFF  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |ID 属性  <br/> |
   
## <a name="remarks"></a>说明

此属性标识**OpenEntry**若要实例化对象，并提供对其所有属性通过**IMAPIProp**相应派生界面访问。 
  
此属性是所有邮件用户的基址属性之一。 
  
此属性可以包含长期或短期标识符。 短期标识符是更轻松和快速构造，但不能在其范围和持续时间，通常为当前会话和工作站超出。 它们是通常用于临时性质，如表格行或对话框中各项，对象，然后放弃。 长期标识符用于更全面且长期性质的对象。 
  
此属性始终是可通过以下方法[IMAPIProp::SaveChanges](imapiprop-savechanges.md)第一次调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法。 某些服务提供商可以使其可实例化后立即。 提供程序必须始终返回从**GetProps**长期的项标识符。 因此，将转换为长期的短期标识符，只需打开的对象并获取其 this 通过**GetProps**属性。 
  
下表总结了此属性，之间重要差异**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))。 
  
|**特征**|**PR_ENTRYID**|**PR_RECORD_KEY**|**PR_SEARCH_KEY**|
|:-----|:-----|:-----|:-----|
|Attachment 对象上所需  <br/> |否  <br/> |是  <br/> |否  <br/> |
|需要对文件夹对象  <br/> |是  <br/> |是  <br/> |否  <br/> |
|消息存储对象上所需  <br/> |是  <br/> |是  <br/> |否  <br/> |
|状态对象上所需  <br/> |是  <br/> |否  <br/> |否  <br/> |
|创建客户端  <br/> |否  <br/> |否  <br/> |是  <br/> |
|调用**SaveChanges**前可用 <br/> |取决于提供程序实现  <br/> |取决于提供程序实现  <br/> |用于消息，是。 其他人，取决于提供程序实现。  <br/> |
|复制操作中发生的更改  <br/> |是  <br/> |是  <br/> |否  <br/> |
|可更改后副本的客户端  <br/> |否  <br/> |否  <br/> |是  <br/> |
|唯一  <br/> |整个 world  <br/> |提供程序实例  <br/> |整个 world  <br/> |
|二进制 （与 memcmp) 相当  <br/> |无需使用[IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md) <br/> |是  <br/> |是  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
[[MS OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为消息对象。
    
[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理顺序和客户端和服务器之间的数据传输的流。
    
[[MS OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)
  
> 处理检索存储在服务器的文件夹的权限列表。
    
[[MS OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。
    
[[MS OXWAVLS]](https://msdn.microsoft.com/library/69a276d8-5fc3-40ba-acd0-31cf42e6af58%28Office.15%29.aspx)
  
> 指定架构和用于请求用户和资源的可用性信息的方法。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagStoreEntryId 规范属性](pidtagstoreentryid-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

