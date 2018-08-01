---
title: MAPI 表单通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 97ff2733-a2b1-4da0-b628-00850fc7925b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7064aee2ccd35b6b372bc6f911c7508113c26162
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776249"
---
# <a name="mapi-forms-notifications"></a>MAPI 表单通知

  
  
**适用于**： Outlook 
  
注册有关和处理来自窗体对象通知其他 MAPI 对象不同于进程。 **IMAPIViewAdviseSink**或**IMAPIFormAdviseSink**接口而不是**IMAPIAdviseSink**也建议的窗体通知实现接收器。 [IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)和[IMAPIFormAdviseSink: IUnknown](imapiformadvisesinkiunknown.md)每个具有多个方法，一个用于每个可能的事件的相应告知源是能够生成。 例如， **IMAPIFormAdviseSink**具有两个方法： [IMAPIFormAdviseSink::OnChange](imapiformadvisesink-onchange.md)处理对表单查看器的状态和[IMAPIFormAdviseSink::OnActivateNext](imapiformadvisesink-onactivatenext.md)显示新消息与正确的表单的更改。 
  
类似于处理 OLE 中实现的策略的事件的事件处理表单的策略。 客户端不注册为特定事件类型的大多数 MAPI 对象一样。 假设是事件的，将通知注册使他们能够接收任何类型的特定 advise 源可以生成。 由于**IMAPIAdviseSink::OnNotify**必须编写以便处理所有已注册的事件，实现它可以复杂的客户端的多个不同事件注册。 因为窗体中的方法告知接收器对象目标单个事件，实现这些方法是简单。 
  

