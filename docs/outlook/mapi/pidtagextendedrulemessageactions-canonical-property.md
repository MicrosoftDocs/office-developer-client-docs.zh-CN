---
title: PidTagExtendedRuleMessageActions 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExtendedRuleMessageActions
api_type:
- HeaderDef
ms.assetid: 1cf277d4-76ec-4902-9e54-f1780cee49bf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 70f09d6db5940fcb9b980cc839988113bd3a3e2e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316336"
---
# <a name="pidtagextendedrulemessageactions-canonical-property"></a>PidTagExtendedRuleMessageActions 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关 FAI 邮件中"文件夹关联信息" (命名) 信息。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_EXTENDED_RULE_MSG_ACTIONS  <br/> |
|标识符:  <br/> |0x0E99  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Rules  <br/> |
   
## <a name="remarks"></a>备注

必须在 FAI 邮件上设置此属性。 此属性的作用与 **PR_RULE_ACTIONS** ([PidTagRuleActions](pidtagruleactions-canonical-property.md)) 相同，但包含有关规则版本以及规则操作中存储的命名属性的其他信息，以及有关此规则要执行的操作的信息。 包含在用于包含操作的操作缓冲区的任何部分的所有字符串值都必须采用 Unicode 格式。
  
有关此二进制属性的格式的信息，请参阅 [[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)
  
> 在服务器上处理传入电子邮件。
    
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

