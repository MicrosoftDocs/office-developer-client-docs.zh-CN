---
title: 删除通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 107ebcd7-b612-4139-b676-c3851f15bc74
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1d5ae33b08c85c9ee93764d762c2ec251fddd265
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425258"
---
# <a name="removing-address-book-entries"></a>删除通讯簿条目
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将调用容器的[IABContainer::D eleteentries](iabcontainer-deleteentries.md)方法以删除一个或多个收件人。 **DeleteEntries**有两个参数: 条目标识符的数组, 这些标识符代表要删除的收件人和保留的标志值。 删除收件人会影响容器的内容表;除了删除收件人, 容器必须删除代表收件人的内容表格行。 当从表中删除行时, 您的容器必须向每个已注册的客户端发出表通知。 
  
### <a name="to-implement-iabcontainerdeleteentries"></a>实现 IABContainer::D eleteentries
  
1. 从容器中删除条目标识符代表的每个收件人。
    
2. 如果容器的内容表处于打开状态:
    
   - 向每个已删除内容表行的已注册客户端发送_fnevTableModified_通知, 并将**ulTableEvent**成员设置为 TABLE_ROW_DELETED。 如果提供程序使用通知实用程序, 请调用[IMAPISupport:: Notify](imapisupport-notify.md)发送这些通知。 
    
   - 如果您的提供程序支持对象通知, 则还要发送_fnevObjectDeleted_通知。 
    

