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
ms.openlocfilehash: e56d7851b1fe28ddea1703d9ec3ffb7737abeda6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435626"
---
# <a name="pidtagreturnedmessageid-canonical-property"></a>PidTagReturnedMessageid 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果返回原始邮件并返回未读报告，则包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RETURNED_IPM  <br/> |
|标识符:  <br/> |0x0033  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>备注

X.400 传输提供程序在未读报告中设置此属性。
  
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

