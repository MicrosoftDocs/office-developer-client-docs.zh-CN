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
  
调用容器的 [IABContainer：:D eleteEntries](iabcontainer-deleteentries.md) 方法以删除一个或多个收件人。 **DeleteEntries** 有两个参数：表示要删除的收件人的条目标识符数组和保留标志值。 删除收件人会影响容器的内容表;除了删除收件人之外，容器还必须删除表示收件人的内容表行。 从表中删除行后，容器必须向每个注册的客户端发出表通知。 
  
### <a name="to-implement-iabcontainerdeleteentries"></a>实现 IABContainer：:D eleteEntries
  
1. 从容器中删除条目标识符表示的每个收件人。
    
2. 如果容器的内容表已打开：
    
   - 将  _fnevTableModified_ 通知与 **ulTableEvent** 成员集一TABLE_ROW_DELETED每个已删除内容表行的注册客户端。 如果提供程序使用通知实用工具，请调用 [IMAPISupport：：Notify](imapisupport-notify.md) 以发送这些通知。 
    
   - 如果提供程序支持对象通知，还应发送  _fnevObjectDeleted_ 通知。 
    

