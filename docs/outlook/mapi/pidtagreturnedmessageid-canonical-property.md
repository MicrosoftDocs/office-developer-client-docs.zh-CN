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
ms.openlocfilehash: 38d357fa87a8781173be118fdd2cd26f57e814df
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583622"
---
# <a name="pidtagreturnedmessageid-canonical-property"></a>PidTagReturnedMessageid 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
如果使用 nonread 报告返回原始邮件，则，包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RETURNED_IPM  <br/> |
|标识符：  <br/> |0x0033  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>注解

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

