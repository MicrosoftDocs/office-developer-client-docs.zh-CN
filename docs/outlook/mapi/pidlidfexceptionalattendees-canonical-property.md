---
title: PidLidFExceptionalAttendees 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFExceptionalAttendees
api_type:
- COM
ms.assetid: f1f489a3-e83a-4e96-bf9a-d98bc17d29f5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 544b5b5ac945eeedf787af0e311491da1f9d0217
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327473"
---
# <a name="pidlidfexceptionalattendees-canonical-property"></a>PidLidFExceptionalAttendees 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示此属性是否为具有一个或多个例外的定期 calendar 对象, 并且至少有一个异常嵌入邮件至少有一个 RecipientRow。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidFExceptionalAttendees  <br/> |
|属性集:  <br/> |PSETID_Appointment  <br/> |
|长 ID (盖子):  <br/> |0x0000822B  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |会议  <br/> |
   
## <a name="remarks"></a>注解

值为 FALSE, 或缺少此属性时, 指示 calendar 对象不包含任何异常, 或者任何异常嵌入的邮件都没有 RecipientRows。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

