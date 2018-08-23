---
title: PidTagAcknowledgementMode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAcknowledgementMode
api_type:
- HeaderDef
ms.assetid: 23329ca3-89f9-4e5a-9c8a-6262f2a2d26f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28b42e6abee5d918dbcca69c13642f3ebcc859e1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581935"
---
# <a name="pidtagacknowledgementmode-canonical-property"></a>PidTagAcknowledgementMode 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含消息确认的模式的标识符。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ACKNOWLEDGEMENT_MODE  <br/> |
|标识符：  <br/> |0x0001  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Exchange  <br/> |
   
## <a name="remarks"></a>注解

此属性可以具有完全下列值之一：
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |手动确认。  <br/> |
|1  <br/> |自动确认。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

