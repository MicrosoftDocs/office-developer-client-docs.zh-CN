---
title: PidTagIpmSentMailEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmSentMailEntryId
api_type:
- HeaderDef
ms.assetid: f6877435-6b26-4060-924f-a65591ad9538
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fd29afc93bc952bb619dfac752fae232bf7991cf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437320"
---
# <a name="pidtagipmsentmailentryid-canonical-property"></a>PidTagIpmSentMailEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 IPM 和"已发送 (文件夹中) 邮件的条目标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IPM_SENTMAIL_ENTRYID  <br/> |
|标识符:  <br/> |0x35E4  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |文件夹  <br/> |
   
## <a name="remarks"></a>备注

发送后，通常将邮件放入"已发送项目"文件夹中。 客户端可以使用此属性对提交的邮件PR_SENTMAIL_ENTRYID ( [PidTagSentMailEntryId) PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)属性。 
  
## <a name="related-resources"></a>相关资源

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

