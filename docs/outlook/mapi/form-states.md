---
title: 表单状态
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dfc9fbf1-90d4-4756-92d9-032ac56a9c50
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 61d20ff7010151a82c53cafc69270e6925796a5c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429164"
---
# <a name="form-states"></a>表单状态

**适用于**：Outlook 2013 | Outlook 2016 
  
Form 对象可能位于五个不同的状态之一，具体取决于已调用的方法以及执行这些方法时是否发生了任何错误。 这些状态在下列主题中进行了介绍：
  
- [未初始化状态](uninitialized-state.md)
    
- [正常状态](normal-state.md)
    
- [NoScribble 状态](noscribble-state.md)
    
- [HandsOffAfterSave 状态](handsoffaftersave-state.md)
    
- [HandsOffFromNormal 状态](handsofffromnormal-state.md)
    
状态主要与表单对象中数据的状态相关。 不同的状态反映了是否需要保存数据、表单对象是否应该允许修改数据，以及保存表单数据的过程中位于什么点。 因此，与任何其他方法不同，表单状态和转换与表单服务器的 [IPersistMessage ： IUnknown](ipersistmessageiunknown.md) 接口方法的实现相关。 了解这些状态对于正确实现表单服务器必须实施的 MAPI 表单接口非常有用。 
  
本节中的主题介绍各种状态，以及导致过渡到其他状态允许的操作。 不允许在主题中未列出的任何转换。 如果表单对象不允许在状态之间进行转换，则它们的行为方式不会与邮件客户端预期的方式一样，并且可能导致不可预知的客户端或表单对象行为。
  
> [!NOTE]
> 某些状态转换取决于以前状态的信息。 您的表单服务器很可能必须在其表单对象中实现一个标志，以指示是否已更改邮件属性的值，以便以后更改状态。 
  
## <a name="see-also"></a>另请参阅

- [开发 MAPI 表单服务器](developing-mapi-form-servers.md)

