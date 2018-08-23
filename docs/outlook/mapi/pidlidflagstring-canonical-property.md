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
ms.openlocfilehash: b29fdbb82635ca7706be15ee9f674262d2204ad5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576181"
---
# <a name="pidlidflagstring-canonical-property"></a>PidLidFlagString 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含标识之一的一组预定义的文本字符串标志相关联的索引。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidFlagStringEnum  <br/> |
|属性进行设置：  <br/> |PSETID_Common  <br/> |
|长 ID （盖）：  <br/> |0x000085C0  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |Task  <br/> |
   
## <a name="remarks"></a>注解

如果设置此属性，客户端应下表中 （例如，若要替换的字符串转换为当前用户的语言），使用相应的字符串值，并应忽略**dispidFlagRequest** ([中设置的值PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 和**dispidValidFlagStringProof** ([PidLidValidFlagStringProof](pidlidvalidflagstringproof-canonical-property.md))。 
  
建议为用户联系人对象的默认值如下所示：
  
|**值**|**英语字符串**|
|:-----|:-----|
|0x00000000 或不存在  <br/> | 按照与显示**dispidFlagRequest**相关的指南。  <br/> |
|0x0000006E  <br/> |"跟踪"  <br/> |
|0x0000006F  <br/> |"呼叫"  <br/> |
|0x00000070  <br/> |"安排会议"  <br/> |
|0x00000071  <br/> |"发送电子邮件"  <br/> |
|0x00000072  <br/> |"发送字母"  <br/> |
   
建议对所有其他消息对象的用户的默认值如下所示：
  
|**值**|**英语字符串**|
|:-----|:-----|
|0x00000000 或不存在  <br/> | 按照与显示**dispidFlagRequest**相关的指南。  <br/> |
|0x00000001  <br/> |"呼叫"  <br/> |
|0x00000002  <br/> |"不要转发"  <br/> |
|0x00000003  <br/> |"跟踪"  <br/> |
|0x00000004  <br/> |"为您的信息"  <br/> |
|0x00000005  <br/> |"转接"  <br/> |
|0x00000006  <br/> |"不需要响应"  <br/> |
|0x00000007  <br/> |"Read"  <br/> |
|0x00000008  <br/> |"答复"  <br/> |
|0x00000009  <br/> |"全部答复"  <br/> |
|0x0000000A  <br/> |"审阅"  <br/> |
   
上面指定的所有字符串可以都转换到用户的语言，如果适用。
  
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



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

