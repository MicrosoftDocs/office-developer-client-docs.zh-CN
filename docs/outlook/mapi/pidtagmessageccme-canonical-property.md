---
title: PidTagMessageCcMe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageCcMe
api_type:
- HeaderDef
ms.assetid: 7310a0f2-a109-40a4-99bf-e963d754a067
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7605739dd6d0f0205a1a4f09eb8c45d235c0c179
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329734"
---
# <a name="pidtagmessageccme-canonical-property"></a>PidTagMessageCcMe 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果专门将此邮件用户命名为"抄送 (抄送) 此邮件的收件人，并且此邮件用户不是通讯组列表的一部分，则包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MESSAGE_CC_ME  <br/> |
|标识符:  <br/> |0x0058  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

此属性提供了一种方便地确定用户名是否显式显示在抄件收件人列表中，而无需检查列表中的所有条目。 
  
此属性还有助于在收到邮件时自动处理收到的邮件。 在传输提供程序的选项中，如果邮件传递用户未直接在收件人表中列出，则此属性包含 FALSE 或不设置。 
  
通讯组列表扩展或盲副本指定导致的邮件传递不会导致设置此属性。 收件人必须明确命名。 
  
未发送的邮件通常不设置此属性、PR_MESSAGE_RECIP_ME ( [PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md)) 或 **PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md)) 。 如果用户在邮件中显示用户可以访问公共邮件存储、其他用户专用存储、磁盘上的文件或其他接收的邮件内嵌入的邮件，则通常包含传输提供程序上次传递邮件时设置的值。 
  
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

