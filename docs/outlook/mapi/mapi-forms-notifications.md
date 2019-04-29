---
title: MAPI 表单通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 97ff2733-a2b1-4da0-b628-00850fc7925b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e9c10f78af6dff2e0d0c59d0bfe59be07dccd4b2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418608"
---
# <a name="mapi-forms-notifications"></a>MAPI 表单通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在表单对象中注册和处理通知与其他 MAPI 对象的过程不同。 窗体通知的通知接收器实现**IMAPIViewAdviseSink**或**IMAPIFormAdviseSink**接口, 而不是**IMAPIAdviseSink**。 [IMAPIViewAdviseSink: iunknown](imapiviewadvisesinkiunknown.md)和[IMAPIFormAdviseSink: iunknown](imapiformadvisesinkiunknown.md)都有多个方法, 每个方法对应于相应的建议源能够生成的每个可能的事件一个。 例如, **IMAPIFormAdviseSink**有两种方法: [IMAPIFormAdviseSink:: OnChange](imapiformadvisesink-onchange.md)以处理对表单查看器状态的更改, 并[IMAPIFormAdviseSink:: OnActivateNext](imapiformadvisesink-onactivatenext.md)以使用正确的格式显示新邮件。 
  
窗体的事件处理策略类似于在 OLE 中实现的事件处理策略。 客户端不会对对大多数 MAPI 对象的特定事件类型进行注册。 假定注册通知使其能够接收可由特定通知源生成的任何类型的事件。 由于必须写入**IMAPIAdviseSink:: OnNotify**以处理所有已注册的事件, 因此实现它对于注册许多不同事件的客户端来说可能非常复杂。 由于 "建议接收器对象" 中的方法面向单个事件, 因此实现这些方法更简单。 
  

