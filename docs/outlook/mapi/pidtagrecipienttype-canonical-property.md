---
title: PidTagRecipientType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientType
api_type:
- COM
ms.assetid: 67e31027-6bc2-4a40-9b00-d61baef4ab0f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9d74fdb3acb6db94078d6090f0def050fb564cd9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355256"
---
# <a name="pidtagrecipienttype-canonical-property"></a>PidTagRecipientType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含邮件收件人的收件人类型。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RECIPIENT_TYPE  <br/> |
|标识符:  <br/> |0x0C15  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 收件人  <br/> |
   
## <a name="remarks"></a>注解

此属性中包含的收件人类型包含一个必需值和一个可选标志。
  
此属性必须正好包含以下值之一:
  
MAPI_TO 
  
> 收件人是主收件人 (收件人)。 客户端是处理主收件人的必要条件。 所有其他类型都是可选的。
    
MAPI_CC 
  
> 收件人是抄送 (CC) 收件人, 除了主要收件人之外, 还接收邮件的收件人。
    
MAPI_BCC 
  
> 收件人是一个密件抄送 (BCC) 收件人。 主收件人和抄送收件人不知道密件抄送收件人是否存在。 
    
MAPI_P1 
  
> 收件人在上一次尝试中未成功接收邮件。 这是一种先前传输的重新发送。
    
此外, 还可以设置以下标志:
  
MAPI_SUBMITTED 
  
> 收件人已收到邮件, 无需再次接收邮件。 这是一种先前传输的重新发送。 此标志与**MAPI_TO**、 **MAPI_CC**和**MAPI_BCC**值一起设置。 
    
当由于 nondelivery 给一个或多个预期收件人而重新传输邮件时, 将使用 MAPI_P1 值和**MAPI_SUBMITTED**标志。 对于此重新传输, 客户端在每个不需要邮件的收件人上设置**MAPI_SUBMITTED** , 但应显示在收件人列表中。 对于之前未收到邮件的每个收件人, 客户端保留原始收件人, 其**PR_RECIPIENT_TYPE**值保持不变, 但此外, 还会提交具有 MAPI_P1 的收件人副本以替换原始值。 此副本在实际传递之前被放弃, 强制收件人加入 P1 信封并保证对该收件人进行物理重新传输。 对于 MAPI_P1 收件人, **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE。
  
当客户端显示重发表单时, 只有 MAPI_P1 收件人是可见的。 除非用户输入其他收件人, 否则邮件传递时, 收件人列表的显示与邮件首次发送时的显示方式完全一样。 
  
**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))、 **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 属性与收件人类型相关。 当客户端调用邮件的**IMAPIProp:: SaveChanges** , 并且收件人列表中至少有一个收件人时, 邮件存储提供程序将按如下所示设置这些属性: 
  
|**属性**|**说明**|
|:-----|:-----|
|PR_DISPLAY_TO  <br/> |如果有一个或多个收件人是**MAPI_TO**收件人, 则设置为 TRUE。  <br/> |
|PR_DISPLAY_CC  <br/> |如果有一个或多个收件人是**MAPI_CC**收件人, 则设置为 TRUE。  <br/> |
| PR_DISPLAY_BCC  <br/> |如果有一个或多个收件人是**MAPI_BCC**收件人, 则设置为 TRUE。  <br/> |
   
在 X. 400 中, P1 或传递信封是传递邮件所需的信息, 包括收件人的地址属性和控制传递和回复的任何选项标志。 P2 或显示信封是通常显示给除邮件文本本身之外的每个收件人的信息。 它通常包括主题、重要性、优先级、敏感度和提交时间, 以及主要和复制的收件人姓名。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagRecipientStatus 规范属性](pidtagrecipientstatus-canonical-property.md)
  
[PidTagDisplayTo 规范属性](pidtagdisplayto-canonical-property.md)
  
[PidTagDisplayBcc 规范属性](pidtagdisplaybcc-canonical-property.md)
  
[PidTagDisplayCc 规范属性](pidtagdisplaycc-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

