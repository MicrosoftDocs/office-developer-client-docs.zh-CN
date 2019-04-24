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
  
包含标志的32位位掩码, 用于定义内容表中的邮件的状态。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MSG_STATUS  <br/> |
|标识符:  <br/> |0x0E17  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常规邮件  <br/> |
   
## <a name="remarks"></a>注解

邮件可以存在于内容表和一个或多个搜索结果表中, 并且邮件的每个实例都可以具有不同的状态。 此属性不应被视为邮件的属性, 而是内容表中的列。 
  
客户端应用程序可以在此属性中设置以下一个或多个标志: 
  
MSGSTATUS_ANSWERED 
  
> 邮件已回复。 
    
MSGSTATUS_DELMARKED 
  
> 已将邮件标记为后续删除。 
    
MSGSTATUS_DRAFT 
  
> 邮件处于草稿修订版状态。 
    
MSGSTATUS_HIDDEN 
  
> 将从收件人的文件夹显示中禁止显示该邮件。 
    
MSGSTATUS_HIGHLIGHTED 
  
> 邮件将在收件人的文件夹显示中突出显示。 
    
MSGSTATUS_REMOTE_DELETE 
  
> 已将邮件标记为在远程邮件存储库中删除, 而不会将其下载到本地客户端。 
    
MSGSTATUS_REMOTE_DOWNLOAD 
  
> 已将邮件标记为从远程邮件存储下载到本地客户端。 
    
MSGSTATUS_TAGGED 
  
> 已针对客户端定义的目的对邮件进行了标记。
    
**MSGSTATUS_DELMARKED**、 **MSGSTATUS_HIDDEN**、 **MSGSTATUS_HIGHLIGHTED**和**MSGSTATUS_TAGGED**标志由客户端定义。 传输和存储提供程序无需任何操作即可传递这些 bits。 
  
客户端可以通过适合其应用程序的任何方式解释这些值。 许多客户端使用此属性的一种方式是显示标记为要删除的邮件, 其中包含代表性图标。 
  
远程查看器客户端可以对由远程传输提供程序呈现的头文件夹中的邮件设置**MSGSTATUS_REMOTE_DELETE**或**MSGSTATUS_REMOTE_DOWNLOAD** 。 客户端应用程序可以检查此文件夹中的每个邮件头, 以确定是否应在远程邮件存储中下载或删除邮件。 然后, 该示例使用[IMAPIFolder:: SetMessageStatus](imapifolder-setmessagestatus.md)方法设置适当的标志。 **SetMessageStatus**是设置此属性中的任何标志的唯一方法;无法使用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法。 若要检索此属性, 客户端应调用[IMAPIFolder:: GetMessageStatus](imapifolder-getmessagestatus.md)而不是[IMAPIProp:: GetProps](imapiprop-getprops.md)。
  
此属性的位16至 31 (0x10000 到 0x80000000) 可供人际邮件 (IPM) 客户端应用程序使用。 保留所有其他位以供 MAPI 使用;前面的表中未定义的那些项最初应设置为零, 并且不会随后更改。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理服务器和客户端之间的同步邮件对象数据。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryRows](imapitable-queryrows.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

