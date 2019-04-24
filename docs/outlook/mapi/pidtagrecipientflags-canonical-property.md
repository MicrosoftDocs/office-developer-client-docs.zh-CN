---
title: PidTagRecipientFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientFlags
api_type:
- COM
ms.assetid: 9fbe537f-b5fe-48a2-803c-653c50c82efd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7b791d75c2a76ea1a504c0d8862dd20f5365b475
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356698"
---
# <a name="pidtagrecipientflags-canonical-property"></a>PidTagRecipientFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定一个用于描述收件人状态的位域。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECIPIENT_FLAGS  <br/> |
|标识符:  <br/> |0x5FFD  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |传输收件人  <br/> |
   
## <a name="remarks"></a>注解

此属性不是必需的。 以下是可以设置的单个标志。
  
|**Value**|**说明**|
|:-----|:-----|
|S (recipSendable, 0x00000001)  <br/> |收件人是**可发送**的与会者。 此标志仅在**dispidApptUnsendableRecips** ([PidLidAppointmentUnsendableRecipients](pidlidappointmentunsendablerecipients-canonical-property.md)) 属性中使用。  <br/> |
|O (recipOrganizer, 0x0000002)  <br/> |在其上设置此标志的**RecipientRow**代表会议组织者。  <br/> |
|ER (recipExceptionalResponse, 0x00000010)  <br/> |指示与会者为此**RecipientRow**所驻留的异常提供响应。 此标志仅用于组织者的会议对象的异常嵌入邮件对象的**RecipientRow** 。  <br/> |
|ED (recipExceptionalDeleted, 0x00000020)  <br/> |指示尽管**RecipientRow**存在, 但应将其视为相应的收件人不是。 此标志仅用于组织者的会议对象的异常嵌入邮件对象的**RecipientRow** 。  <br/> |
|X (reserved, 0x00000040)  <br/> |不得设置。  <br/> |
|X (reserved, 0x00000080)  <br/> |不得设置。  <br/> |
|G (recipOriginal, 0x00000100)  <br/> |指示收件人是原始与会者。 此标志仅在**dispidApptUnsendableRecips**属性中使用。  <br/> |
|X (reserved, 0x00000200)  <br/> |保留。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
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

