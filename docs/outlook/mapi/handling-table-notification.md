---
title: 处理表通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: edc9bc71-4885-4783-b465-0bafa20eff73
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 95ef351e4fe906608319a3e25de8f20a44e23d9d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775070"
---
# <a name="handling-table-notification"></a>处理表通知

**适用于**： Outlook 
  
作为的替代方式直接注册 advise source 对象，如文件夹或消息的用户，客户端可以在内容通知注册或层次结构表。 跟踪更改通讯簿条目、 文件夹和邮件内容或层次结构表可以更简单、 更加比通过单个对象。 

例如，您可以在文件夹层次结构表，寻找到它的子文件夹发生更改时呼叫[IMAPITable::Advise](imapitable-advise.md) 。 如果您支持查看的远程邮件，使用状态表，以查看由传输提供程序的活动和 MAPI 后台处理程序注册。 
  
但是，它并不总是首选而不是对象通知使用表通知。 监控的文件夹中的消息数的变化时的示例可能需要您的客户端注册对象通知的文件夹，而不是在该文件夹所实现的表格。
  

