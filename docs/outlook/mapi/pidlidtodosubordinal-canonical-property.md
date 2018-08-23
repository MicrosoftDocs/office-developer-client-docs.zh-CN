---
title: PidLidToDoSubOrdinal 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidToDoSubOrdinal
api_type:
- COM
ms.assetid: e3bc15ef-155e-49fd-88e5-64713df9b939
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 98dfdab24d2c4170609d9db1c3104a3f17436736
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578064"
---
# <a name="pidlidtodosubordinal-canonical-property"></a>PidLidToDoSubOrdinal 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
**DispidToDoOrdinalDate** ([PidLidToDoOrdinalDate](pidlidtodoordinaldate-canonical-property.md)) 属性排序对象和领结结果时，作为领结分词系统。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidToDoSubOrdinal  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x000085A1  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>注解

如果使用，必须按字典序按此属性。 字符串的组件字符必须包含仅数字 0 到 9。 此属性应最初设置为"5555555"。 此属性的长度不得超过 254 个字符 （不包括 NULL 终止符）。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和相关的 Exchange Server 协议规范的引用。
    
[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定的属性和与标记的操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[PidLidToDoOrdinalDate 规范属性](pidlidtodoordinaldate-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

