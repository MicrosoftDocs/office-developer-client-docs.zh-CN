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
   
## <a name="remarks"></a>备注

此属性中包含的收件人类型由一个必需值和一个可选标志组成。
  
此属性必须仅包含下列值之一：
  
MAPI_TO 
  
> 收件人是收件人 () 收件人。 客户端需要处理主收件人。 所有其他类型都是可选的。
    
MAPI_CC 
  
> 收件人是抄送 (抄) 抄送收件人，即除了主要收件人之外接收邮件的收件人。
    
MAPI_BCC 
  
> 收件人是 BCC 收件人 (的) 副本。 主要收件人和抄送收件人不知道是否存在 BCC 收件人。 
    
MAPI_P1 
  
> 收件人在上一次尝试中未成功收到邮件。 这是之前传输的重新发送。
    
此外，还可以设置以下标志：
  
MAPI_SUBMITTED 
  
> 收件人已收到邮件，无需再次接收邮件。 这是之前传输的重新发送。 此标志与值 MAPI_TO、MAPI_CC和 **MAPI_BCC****一起** 设置。 
    
由于MAPI_P1一个或多个目标收件人而重新传递邮件时，使用 MAPI_P1 值和 MAPI_SUBMITTED 标志。 对于此重新传输，客户端MAPI_SUBMITTED设置每个不需要再次发送邮件但应显示在收件人列表中的收件人的邮件。 对于之前未收到邮件的每一个收件人，客户端会保留原始收件人的 **PR_RECIPIENT_TYPE** 值不变，但另外提交收件人的副本，MAPI_P1以更改原始值。 在实际传递之前放弃此副本会强制收件人进入 P1 信封，并保证实际重新传输给该收件人。 对于 **PR_RESPONSIBILITY (** [PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE，MAPI_P1 FALSE。
  
当客户端显示重新发送窗体时，只有MAPI_P1收件人可见。 除非用户输入其他收件人，否则在邮件传递时，收件人列表的显示方式与首次发送邮件时完全相同。 
  
[PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) PR_DISPLAY_TO (、PR_DISPLAY_CC ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和 **PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 属性与收件人类型相关。   当客户端调用邮件 **的 IMAPIProp：：SaveChanges** 且收件人列表中至少有一个收件人时，邮件存储提供程序将按如下方式设置这些属性： 
  
|**属性**|**说明**|
|:-----|:-----|
|PR_DISPLAY_TO  <br/> |如果一个或多个收件人是收件人，则设置为 TRUE **MAPI_TO** 收件人。  <br/> |
|PR_DISPLAY_CC  <br/> |如果一个或多个收件人是收件人，则设置为 TRUE **MAPI_CC收件人** 。  <br/> |
| PR_DISPLAY_BCC  <br/> |如果一个或多个收件人是收件人，则设置为 TRUE **MAPI_BCC收件人** 。  <br/> |
   
在 X.400 中，P1 或传递信封是传递邮件时需要的信息，包括收件人的地址属性以及控制传递和答复的任何选项标志。 P2 或显示信封是通常向除邮件文本本身外的其他每个收件人显示的信息。 通常包括主题、重要性、优先级、敏感度和提交时间，以及主要和复制的收件人姓名。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定电子邮件对象允许的属性和操作。
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagRecipientStatus 规范属性](pidtagrecipientstatus-canonical-property.md)
  
[PidTagDisplayTo 规范属性](pidtagdisplayto-canonical-property.md)
  
[PidTagDisplayBcc 规范属性](pidtagdisplaybcc-canonical-property.md)
  
[PidTagDisplayCc 规范属性](pidtagdisplaycc-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

