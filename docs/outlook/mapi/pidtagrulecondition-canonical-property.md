---
title: PidTagRuleCondition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRuleCondition
api_type:
- COM
ms.assetid: 8a11e846-c62f-4c06-876f-94623d50cc3b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 81dbd097523f4cb5016a3e846f63cfbe1c643de2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575859"
---
# <a name="pidtagrulecondition-canonical-property"></a>PidTagRuleCondition 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使用评估规则时的条件。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RULE_CONDITION  <br/> |
|标识符：  <br/> |0x6679  <br/> |
|数据类型：  <br/> |PT_SRESTRICTION  <br/> |
|区域：  <br/> |服务器端规则  <br/> |
   
## <a name="remarks"></a>注解

条件表示为**限制**，并且**PropertyValue**缓冲区包含打包为[[MS OXCDATA]](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)中指定的**限制**结构。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ImportProcs.cpp  <br/> |PropCopyMore HrCopyRestriction  <br/> |这些函数演示如何将复制到另一个属性对于分析**PT_SRESTRICTION**属性。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXORULE]](http://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)
  
> 处理传入的电子邮件服务器上。
    
[[MS OXCDATA]](http://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)
  
> 定义所使用的基本的数据结构中远程操作。
    
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

