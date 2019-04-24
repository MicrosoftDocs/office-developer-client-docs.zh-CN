---
title: PidTagOriginalAuthorSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorSearchKey
api_type:
- COM
ms.assetid: 4a10cf99-c5e6-4a24-b531-3aebb7800bfe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 09331e1201b6f6e45bb9e26e618ee59e67efbf8d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356257"
---
# <a name="pidtagoriginalauthorsearchkey-canonical-property"></a>PidTagOriginalAuthorSearchKey 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件第一版的作者的搜索关键字, 即邮件转发或答复前的邮件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_AUTHOR_SEARCH_KEY  <br/> |
|标识符:  <br/> |0x0056  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |服务器  <br/> |
   
## <a name="remarks"></a>注解

此属性是邮件作者的地址属性之一。 首次提交邮件时, 客户端应用程序应将此属性设置为**PR_SENDER_SEARCH_KEY**[PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)属性的值。 转发或答复邮件时, 它永远不会更改。 
  
原始作者属性允许保留本地邮件域外部的信息。 当邮件到达其他邮件域 (例如从 Internet) 时, 这些属性提供了一种确保原始信息不会丢失的方法。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

