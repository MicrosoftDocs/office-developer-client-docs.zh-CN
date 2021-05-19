---
title: PidTagIpmWastebasketEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmWastebasketEntryId
api_type:
- HeaderDef
ms.assetid: 0f8dd043-66f0-4193-9b95-853bc3827f73
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3794386c4461c90f973e4028132cb8220dfaa19b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426350"
---
# <a name="pidtagipmwastebasketentryid-canonical-property"></a>PidTagIpmWastebasketEntryId 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含"已删除邮件"文件夹中标准 (邮件) 标识符。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_IPM_WASTEBASKET_ENTRYID  <br/> |
|标识符:  <br/> |0x35E3  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |文件夹  <br/> |
   
## <a name="remarks"></a>备注

客户端应用程序应该将已删除的邮件移动到"已删除邮件"文件夹。 如果邮件已位于此文件夹中，或者此属性不受支持，则客户端应删除该邮件。 
  
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

