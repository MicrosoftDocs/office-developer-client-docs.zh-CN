---
title: PidTagMessageRecipientMe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageRecipientMe
api_type:
- HeaderDef
ms.assetid: 90333258-8913-4f98-aefb-4cc2ab34abcf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 78423e874becdfc232b0dd964b32ae0c4530d19e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325618"
---
# <a name="pidtagmessagerecipientme-canonical-property"></a>PidTagMessageRecipientMe 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果专门将此邮件用户命名为主要 (To) 、抄送 (CC) 或密件抄送 (密件抄送 (密件抄送) 收件人，并且此邮件用户不是通讯组列表的一部分，则包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_RECIP_ME  <br/> |
|标识符:  <br/> |0x0059  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性提供了一种方便地确定用户名是否显式显示在收件人列表中，而无需检查列表中的所有条目。 值表示属性 **PR_MESSAGE_CC_ME** ([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md)) 和 **PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md)) 的逻辑 **OR** 操作，以及不会显示在属性) 中的 BCC 信息 (。 
  
此属性有助于在收到邮件时自动处理收到的邮件。 在传输提供程序的选项中，如果邮件传递用户未直接在收件人表中列出，则此属性包含 FALSE 或不包含此属性。 
  
通讯组列表展开导致的邮件传递不会导致设置此属性。 收件人必须明确命名。 
  
未发送的邮件通常不设置此属性、PR_MESSAGE_CC_ME **或****PR_MESSAGE_TO_ME**。 如果用户在邮件中显示用户可以访问公共邮件存储、其他用户专用存储、磁盘上的文件或其他接收的邮件内嵌入的邮件，则通常包含传输提供程序上次传递邮件时设置的值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许对电子邮件对象执行的属性和操作。
    
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

