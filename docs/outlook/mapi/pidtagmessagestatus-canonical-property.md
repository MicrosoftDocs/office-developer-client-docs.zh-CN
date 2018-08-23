---
title: PidTagMessageStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageStatus
api_type:
- HeaderDef
ms.assetid: e479e863-a8de-4f7e-9eae-3f721cd16e9a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 626bd945851155c20850ee7f367ec6073ad57bc1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570385"
---
# <a name="pidtagmessagestatus-canonical-property"></a>PidTagMessageStatus 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一个 32 位位掩码的标志，内容表中定义的一条消息，状态。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MSG_STATUS  <br/> |
|标识符：  <br/> |0x0E17  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>注解

在内容和一个或多个搜索结果表中可以存在一条消息和消息的每个实例都可以具有不同的状态。 此属性不应考虑上一条消息，但内容表中的列的属性。 
  
客户端应用程序可以设置此属性中的一个或多个以下标志： 
  
MSGSTATUS_ANSWERED 
  
> 已答复邮件。 
    
MSGSTATUS_DELMARKED 
  
> 邮件已标记为后续删除。 
    
MSGSTATUS_DRAFT 
  
> 邮件是草稿修订状态。 
    
MSGSTATUS_HIDDEN 
  
> 邮件是从收件人的文件夹显示要取消。 
    
MSGSTATUS_HIGHLIGHTED 
  
> 邮件是在收件人的文件夹显示突出显示。 
    
MSGSTATUS_REMOTE_DELETE 
  
> 邮件已标记为删除远程邮件存储在无须下载到本地客户端。 
    
MSGSTATUS_REMOTE_DOWNLOAD 
  
> 已从远程邮件存储下载到本地客户端标记邮件。 
    
MSGSTATUS_TAGGED 
  
> 邮件已标记的客户端定义用途。
    
由客户端定义**MSGSTATUS_DELMARKED**、 **MSGSTATUS_HIDDEN**、 **MSGSTATUS_HIGHLIGHTED**和**MSGSTATUS_TAGGED**标志。 传输和存储提供程序传递这些位不需要任何操作。 
  
客户端可以解释以任何方式适合其应用程序的这些值。 多个客户端使用此属性的一种方法是显示消息标记为删除代表图标。 
  
远程查看器客户端可以设置**MSGSTATUS_REMOTE_DELETE**或**MSGSTATUS_REMOTE_DOWNLOAD**邮件提供给它的远程传输提供程序的标头文件夹中。 客户端应用程序可以检查以确定是否应下载或在远程邮件存储区删除邮件此文件夹中的每个邮件标头。 然后使用[IMAPIFolder::SetMessageStatus](imapifolder-setmessagestatus.md)方法可设置适当的标志。 **SetMessageStatus**是任何标志设置此属性; 中的唯一方法不能使用[IMAPIProp::SetProps](imapiprop-setprops.md)方法。 若要检索此属性，客户端调用[IMAPIFolder::GetMessageStatus](imapifolder-getmessagestatus.md) ，而不是[IMAPIProp::GetProps](imapiprop-getprops.md)。
  
位 16 到 31 (通过 0x80000000 0x10000)，此属性是可供使用人际邮件 (IPM) 客户端应用程序。 所有其他位供使用通过 MAPI;上表中未定义的值应最初设置为零并随后不会改动。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 同步服务器和客户端之间的消息对象数据的句柄。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryRows](imapitable-queryrows.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

