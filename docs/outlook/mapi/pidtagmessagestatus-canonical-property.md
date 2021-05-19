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
ms.openlocfilehash: dacd759d978394a5f4ed028915ed1c717bf6efe5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355718"
---
# <a name="pidtagmessagestatus-canonical-property"></a>PidTagMessageStatus 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含定义内容表中邮件状态的 32 位位掩码标志。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MSG_STATUS  <br/> |
|标识符:  <br/> |0x0E17  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

邮件可以存在于内容表和一个或多个搜索结果表中，并且邮件的每个实例可以具有不同的状态。 不应将此属性视为邮件上的属性，而应视为内容表中的列。 
  
客户端应用程序可以在此属性中设置以下一个或多个标志： 
  
MSGSTATUS_ANSWERED 
  
> 邮件已答复。 
    
MSGSTATUS_DELMARKED 
  
> 邮件已标记为后续删除。 
    
MSGSTATUS_DRAFT 
  
> 邮件位于草稿修订状态。 
    
MSGSTATUS_HIDDEN 
  
> 邮件从收件人的文件夹显示中取消显示。 
    
MSGSTATUS_HIGHLIGHTED 
  
> 邮件将在收件人的文件夹显示中突出显示。 
    
MSGSTATUS_REMOTE_DELETE 
  
> 邮件已在远程邮件存储中标记为删除，无需下载到本地客户端。 
    
MSGSTATUS_REMOTE_DOWNLOAD 
  
> 邮件已标记为从远程邮件存储下载到本地客户端。 
    
MSGSTATUS_TAGGED 
  
> 邮件已标记为客户端定义。
    
客户端MSGSTATUS_DELMARKED、MSGSTATUS_HIDDEN、MSGSTATUS_HIGHLIGHTED和 **MSGSTATUS_TAGGED** 标志。 传输和存储提供程序无需任何操作即可传递这些位。 
  
客户端可以通过适合其应用程序的任何方式解释这些值。 许多客户端使用此属性的一种方式是使用具有代表性图标显示标记为删除的邮件。 
  
远程查看器客户端 **可以在MSGSTATUS_REMOTE_DELETE MSGSTATUS_REMOTE_DOWNLOAD** 向它显示的邮件头文件夹中的邮件设置或设置邮件。 客户端应用程序可以检查此文件夹中的每个邮件头，以确定应在远程邮件存储中下载还是删除邮件。 然后，它使用 [IMAPIFolder：：SetMessageStatus](imapifolder-setmessagestatus.md) 方法设置相应的标志。 **SetMessageStatus** 是设置此属性中任何标志的唯一方法; [不能使用 IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。 若要检索此属性，客户端调用 [IMAPIFolder：：GetMessageStatus，](imapifolder-getmessagestatus.md) 而不是 [IMAPIProp：：GetProps](imapiprop-getprops.md)。
  
此属性的 16 (0x10000 31 位0x80000000) IPM 客户端应用程序中的 (消息) 使用。 保留所有其他位以供 MAPI 使用;上表中未定义的那些项应最初设置为零，以后不应更改。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理在服务器和客户端之间同步邮件对象数据。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryRows](imapitable-queryrows.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

