---
title: PidTagDisplayType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayType
api_type:
- HeaderDef
ms.assetid: ee2bc6ca-3769-4b56-a77d-81418d28f768
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 3fd5a8d92621dcefce66fb42e843f78755fa84df
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777576"
---
# <a name="pidtagdisplaytype-canonical-property"></a>PidTagDisplayType 规范属性

  
  
**适用于**： Outlook 
  
包含用于将图标与特定的表格行关联的值。 
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_DISPLAY_TYPE  <br/> |
|标识符:  <br/> |0x3900  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 通讯簿  <br/> |
   
## <a name="remarks"></a>备注

此属性包含长整型，从而便于在其类型基于的表项的特殊处理。 显示的图标或其他 display 元素的显示类型相关联的通常包含此特殊处理。 
  
文件夹内容表中不使用此属性。 客户端应用程序应使用消息的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性和相应的[IMAPIFormInfo](imapiforminfoimapiprop.md)接口要获取的**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 和**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 的邮件的属性。 
  
此属性可以具有完全下列值之一：
  
DT_AGENT 
  
> 自动的代理，如天报价单或天气图表的显示。
    
DT_DISTLIST 
  
> 通讯组列表。
    
DT_FOLDER 
  
> 显示默认文件夹图标紧邻文件夹。
    
DT_FOLDER_LINK 
  
> 显示默认文件夹链接图标紧邻文件夹，而不是默认文件夹图标。
    
DT_FOLDER_SPECIAL 
  
> 显示特定于应用程序的差异，如一个特殊类型的公用文件夹的文件夹的图标。
    
DT_FORUM 
  
> 论坛，如布告栏服务或公共或共享文件夹。
    
DT_GLOBAL 
  
> 全局通讯簿。
    
DT_LOCAL 
  
> 与小型工作组共享本地通讯簿。
    
DT_MAILUSER 
  
> 典型的消息用户。
    
DT_MODIFIABLE 
  
> 可修改;在用户界面中，应为可修改表示容器。
    
DT_NOT_SPECIFIC 
  
> 不匹配的任何其他设置。
    
DT_ORGANIZATION 
  
> 定义一大组，如帮助台、 accounting 或血驱动器协调特殊别名。
    
DT_PRIVATE_DISTLIST 
  
> 专用的个人管理通讯组列表。
    
DT_REMOTE_MAILUSER 
  
> 已知要从外部或远程邮件系统的收件人。
    
DT_WAN 
  
> 广域网网络通讯簿。
    
通讯簿内容表使用 DT_AGENT、 DT_DISTLIST、 DT_FORUM、 DT_MAILUSER、 DT_ORGANIZATION、 DT_PRIVATE_DISTLIST 和 DT_REMOTE_MAILUSER 值。 通讯簿层次结构表和一次性表使用 DT_GLOBAL、 DT_LOCAL、 DT_MODIFIABLE、 DT_NOT_SPECIFIC 和 DT_WAN 值。 文件夹层次结构表使用 DT_FOLDER、 DT_FOLDER_LINK 和 DT_FOLDER_SPECIAL 值。 
  
如果未设置此属性，客户端应采用默认类型适用于表、 通常 DT_FOLDER、 DT_LOCAL 或 DT_MAILUSER。 
  
 **注释**MAPI 的保留未进行归档的所有值。 客户端应用程序无需定义的任何新值，必须在准备好处理一个未记录的值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的地址簿模板。
    
[[MS OXLDAP]](http://msdn.microsoft.com/library/727c090a-f05c-4eed-94aa-565724cfc550%28Office.15%29.aspx)
  
> 启用目录访问。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

