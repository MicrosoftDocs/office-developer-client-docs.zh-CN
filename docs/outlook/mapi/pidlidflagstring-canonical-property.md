---
title: PidLidFlagString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFlagString
api_type:
- COM
ms.assetid: 4cf1e08b-c869-4965-a1e4-512a0684700f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3cd88db7e93b53990cf0181af623ebca75f0c6e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357783"
---
# <a name="pidlidflagstring-canonical-property"></a>PidLidFlagString 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含标识与标志关联的一组预定义文本字符串之一的索引。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidFlagStringEnum  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x000085C0  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>备注

如果设置了此属性，客户端应该使用 (下面的表中相应的字符串值，例如，替换转换为当前用户的语言) 的字符串，并忽略 **dispidFlagRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 和 **dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md)) 中设置的值。 
  
为联系人对象建议的用户的默认值如下所示：
  
|**值**|**英语字符串**|
|:-----|:-----|
|0x00000000或不存在  <br/> | 按照与显示 **dispidFlagRequest 相关的指南。**  <br/> |
|0x0000006E  <br/> |"Follow up"  <br/> |
|0x0000006F  <br/> |"Call"  <br/> |
|0x00000070  <br/> |"安排会议"  <br/> |
|0x00000071  <br/> |"发送电子邮件"  <br/> |
|0x00000072  <br/> |"Send Letter"  <br/> |
   
为所有其他邮件对象向用户建议的默认值如下所示：
  
|**值**|**英语字符串**|
|:-----|:-----|
|0x00000000或不存在  <br/> | 按照与显示 **dispidFlagRequest 相关的指南。**  <br/> |
|0x00000001  <br/> |"Call"  <br/> |
|0x00000002  <br/> |"Do not Forward"  <br/> |
|0x00000003  <br/> |"Follow up"  <br/> |
|0x00000004  <br/> |"For your information"  <br/> |
|0x00000005  <br/> |"Forward"  <br/> |
|0x00000006  <br/> |"无需响应"  <br/> |
|0x00000007  <br/> |"Read"  <br/> |
|0x00000008  <br/> |"Reply"  <br/> |
|0x00000009  <br/> |"Reply to All"  <br/> |
|0x0000000A  <br/> |"Review"  <br/> |
   
如果适用，可以将上面指定的所有字符串翻译为用户语言。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定与标记相关的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

