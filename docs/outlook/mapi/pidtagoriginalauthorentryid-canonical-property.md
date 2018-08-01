---
title: PidTagOriginalAuthorEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorEntryId
api_type:
- COM
ms.assetid: 34654660-b003-42f5-9fcd-24ebaccd735d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 03244fb240231a105b0a25a0797c13b9bf7f7a80
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777912"
---
# <a name="pidtagoriginalauthorentryid-canonical-property"></a>PidTagOriginalAuthorEntryId 规范属性

  
  
**适用于**： Outlook 
  
包含一条消息，即之前正在转发或答复邮件的第一个版本的作者的项标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ORIGINAL_AUTHOR_ENTRYID  <br/> |
|标识符：  <br/> |0x004C  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>说明

此属性是一个邮件的作者的地址属性。 在首次提交邮件，客户端应用程序应将此属性设置为**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 的值。 当转发或答复邮件永远不会更改它。 
  
原始作者属性允许保留来自域外部的本地消息的信息。 邮件到达后从其他邮件的域，如从 Internet，此属性提供了一种方法，以确保该原始信息不会丢失。
  
## <a name="related-resources"></a>相关资源

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

