---
title: 删除通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 107ebcd7-b612-4139-b676-c3851f15bc74
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1fb7224e110bbee6844cf2820782aac8be213ba3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778602"
---
# <a name="removing-address-book-entries"></a>删除通讯簿条目
  
**适用于**： Outlook 
  
调用容器的[IABContainer::DeleteEntries](iabcontainer-deleteentries.md)方法，以删除一个或多个收件人。 **DeleteEntries**有两个参数： 一个表示要删除的收件人的项标识符和保留的标志值的数组。 删除收件人会影响您的容器; 将目录除了删除收件人，您的容器必须删除代表收件人的内容表行。 时行已从表中，您的容器必须为每个已注册的客户端发出表通知。 
  
### <a name="to-implement-iabcontainerdeleteentries"></a>若要实现 IABContainer::DeleteEntries
  
1. 删除由您的容器中的项标识符的每个收件人。
    
2. 如果您的容器内容表处于打开状态：
    
   - 与将设置为 TABLE_ROW_DELETED 以注册的每个已删除的内容的表格行的客户端的**ulTableEvent**成员发送_fnevTableModified_通知。 如果您的提供商使用通知实用工具，调用[IMAPISupport::Notify](imapisupport-notify.md)发送这些通知。 
    
   - 如果您的提供商支持对象通知，还可以发送_fnevObjectDeleted_通知。 
    

