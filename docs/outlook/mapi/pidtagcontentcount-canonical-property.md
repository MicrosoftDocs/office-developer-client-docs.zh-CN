---
title: PidTagContentCount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentCount
api_type:
- HeaderDef
ms.assetid: 27c75031-a968-4636-98a6-4a5b7422f57c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7e9994da72bbc38a546f220e5ecf8768b80c6f1f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397014"
---
# <a name="pidtagcontentcount-canonical-property"></a>PidTagContentCount 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
计算出的消息存储库包含文件夹中的消息的数。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTENT_COUNT  <br/> |
|标识符：  <br/> |0x3602  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Folder  <br/> |
   
## <a name="remarks"></a>说明

消息存储通过计算此属性用于两个不同的但相关，目的。 MapiFolder 对象，它包含文件夹中的消息的数。 在分类 MAPI 表中的标题行中，它包含非关联的标题行所对应的类别中的消息数。
  
此属性中包含的数字不包括文件夹中的相关联的条目。 **PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md)) 包含的文件夹的未读邮件的计数。 客户端应用程序可以读取但不是能更改此属性和**PR_CONTENT_UNREAD**。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Microsoft Exchange Server 协议规范参考。
    
[[MS OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹的操作。
    
[[MS OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)
  
> 包含允许的操作的核心 table 对象。
    
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

