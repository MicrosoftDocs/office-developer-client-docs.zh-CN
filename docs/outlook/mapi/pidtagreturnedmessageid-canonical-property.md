---
title: PidTagReturnedMessageid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 1f0f13e2-7554-41fc-a7a9-a90c34181c96
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8624821d264500a440b5988ffa30a5c31dc8a91f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778238"
---
# <a name="pidtagreturnedmessageid-canonical-property"></a>PidTagReturnedMessageid 规范属性

  
  
**适用于**： Outlook 
  
如果使用 nonread 报告返回原始邮件，则，包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RETURNED_IPM  <br/> |
|标识符：  <br/> |0x0033  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>说明

X.400 传输提供程序的未读报告中设置此属性。
  
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

