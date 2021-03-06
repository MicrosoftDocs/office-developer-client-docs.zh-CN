---
title: PidTagContentUnreadCount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContentUnreadCount
api_type:
- HeaderDef
ms.assetid: 4fe207e9-a77f-46b9-b51d-d989847a9d02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9572a053182aaa59020a6816736b8a4b92e778b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331869"
---
# <a name="pidtagcontentunreadcount-canonical-property"></a>PidTagContentUnreadCount 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含文件夹中未读邮件的数量，由邮件存储计算。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTENT_UNREAD  <br/> |
|标识符:  <br/> |0x3603  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |文件夹  <br/> |
   
## <a name="remarks"></a>备注

邮件存储计算的此属性用于两个不同的（虽然相关）用途。 在 MAPI 文件夹对象上，它包含文件夹中的邮件数。 在分类的 MAPI 表的标题行中，它包含与该标题行对应的类别中未读非关联邮件的数量。
  
此属性包含文件夹内容表中未在 PR_MESSAGE_FLAGS ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)属性中设置MSGFLAG_READ 标志) 数量。 PidTagContent) Count PR_CONTENT_COUNT ([PidTagContentCount](pidtagcontentcount-canonical-property.md)属性包含文件夹的总邮件计数。  PR_CONTENT_COUNT **和** 此属性对于客户端是只读的。 
  
一些客户端应用程序根据此属性的值以不同方式显示类别的标题行。 例如，客户端可以以粗体显示包含未读邮件的类别。 此属性不能作为类别使用，并且尝试这样做会导致从 [IMAPITable：：SortTable](imapitable-sorttable.md) MAPI_E_INVALID_PARAMETER返回值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Microsoft Exchange Server的引用。
    
[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹操作。
    
[[MS-OXCTABL]](https://msdn.microsoft.com/library/d33612dc-36a8-4623-8a26-c156cf8aae4b%28Office.15%29.aspx)
  
> 包括核心表对象的允许操作。
    
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

