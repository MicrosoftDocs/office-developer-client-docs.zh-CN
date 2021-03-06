---
title: PidTagRemoteValidateOk 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRemoteValidateOk
api_type:
- COM
ms.assetid: e336d2ec-57cb-4d08-bd6e-330ef7d9939e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8b5c9e5bb2aa915d4b76d9998baaf504e7929b78
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424222"
---
# <a name="pidtagremotevalidateok-canonical-property"></a>PidTagRemoteValidateOk 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果允许远程查看器调用 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法，则此属性包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_REMOTE_VALIDATE_OK  <br/> |
|标识符:  <br/> |0x3E0D  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>备注

此属性显示在状态表中，并提供对传输性能的一些控制。 它可视为将远程查看器引导到空闲的另一种方法。 当设置为 TRUE 时，远程查看器可以视需要经常调用 **IMAPIStatus：：ValidateState。** FALSE 值指示远程查看器不能再进行更多调用。 
  
传输提供程序通常通过将值设置为 FALSE 来动态设置此属性，以在传输提供程序具有足够的处理量时禁用其他呼叫。 传输提供程序完成后，它会将值设置成 TRUE，以允许客户端应用程序进行进一步 **IMAPIStatus：：ValidateState** 调用。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

