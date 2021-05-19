---
title: MAPI 窗体通知
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
# <a name="mapi-forms-notifications"></a>MAPI 窗体通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册和处理来自表单对象的通知的过程与其他 MAPI 对象不同。 建议接收表单通知的接收器实现 **IMAPIViewAdviseSink** 或 **IMAPIFormAdviseSink** 接口，而不是 **IMAPIAdviseSink**。 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md) 和 [IMAPIFormAdviseSink ： IUnknown](imapiformadvisesinkiunknown.md) 分别具有多种方法，每个方法对应于相应建议源能够生成的每个可能事件。 例如 **，IMAPIFormAdviseSink** 有两种方法 [：IMAPIFormAdviseSink：：OnChange](imapiformadvisesink-onchange.md) 处理表单查看器状态更改 [，IMAPIFormAdviseSink：：OnActivateNext](imapiformadvisesink-onactivatenext.md) 显示包含正确表单的新消息。 
  
表单的事件处理策略类似于在 OLE 中实现的事件处理策略。 客户端不会像注册大多数 MAPI 对象一样注册特定事件类型。 假设注册通知后，他们就可以接收由特定建议源生成的任何类型的事件。 由于 **必须编写 IMAPIAdviseSink：：OnNotify** 才能处理所有注册的事件，因此对于注册许多不同事件的客户端，实现该事件可能很复杂。 由于表单中的方法建议接收对象面向单个事件，因此实现这些方法更简单。 
  

