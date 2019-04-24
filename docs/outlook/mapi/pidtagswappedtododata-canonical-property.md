---
title: PidTagSwappedToDoData 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSwappedToDoData
api_type:
- COM
ms.assetid: d2a82fc8-de5d-4819-906e-b8314fd06ea0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ecfa1e89688ae525a28e221424fb4a8194fc217
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359134"
---
# <a name="pidtagswappedtododata-canonical-property"></a>PidTagSwappedToDoData 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
维护不影响邮件对象的标记状态的第二组属性值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SWAPPED_TODO_DATA  <br/> |
|标识符:  <br/> |0x0E2D  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |MAPI 非传输  <br/> |
   
## <a name="remarks"></a>注解

充当辅助标志存储位置如果支持发件人标志或发件人标志, 则此结构将提供一个位置, 以在其中存储与发件人标志中支持的信息标记协议相关的所有属性, 以及所有与发件人提醒中支持的提醒设置协议相关的属性, 而不会将发件人标志或发件人提醒信息暴露给邮件的收件人。
  
同样, 此结构还提供一个位置, 以存储与收件人中支持的提醒设置协议相关的收件人标志和属性中所支持的信息标记协议相关的所有属性。有关以前发送的邮件的提醒。
  
有关此属性的详细信息, 请参阅[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> 指定与标记相关的属性和操作。
    
[[毫秒-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> 指定用于电子邮件和其他对象提醒的属性和交互模型。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

