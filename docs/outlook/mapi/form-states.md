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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327515"
---
# <a name="form-states"></a>表单状态

**适用于**：Outlook 2013 | Outlook 2016 
  
表单对象可以是五个不同状态之一, 具体取决于在其中调用的方法以及在执行这些方法时是否发生了错误。 以下主题介绍了这些状态:
  
- [未初始化状态](uninitialized-state.md)
    
- [正常状态](normal-state.md)
    
- [NoScribble 状态](noscribble-state.md)
    
- [HandsOffAfterSave 状态](handsoffaftersave-state.md)
    
- [HandsOffFromNormal 状态](handsofffromnormal-state.md)
    
这些状态主要与 form 对象中的数据的状态相关。 不同的状态反映了是否需要保存数据, 窗体对象是否应允许对数据进行修改, 以及保存该窗体的数据的过程点。 因此, 它们之间的表单状态和转换与您在表单服务器的 IPersistMessage 实现过程中有更多的不同之处[: IUnknown](ipersistmessageiunknown.md)接口方法。 这些状态的知识对于正确实现表单服务器必须实现的 MAPI 表单接口非常有用。 
  
本节中的主题介绍各种状态以及导致转换为其他状态的允许的操作。 不允许主题中未列出的任何转换。 如果表单对象在状态之间禁止转换, 则它们不会以邮件传递客户端预期的方式运行, 并可能导致不可预测的客户端或表单对象行为。
  
> [!NOTE]
> 某些状态转换取决于以前状态中的信息。 您的表单服务器很可能必须在其 form 对象中实现一个标志, 以指示是否已更改邮件属性的值以简化后续状态更改。 
  
## <a name="see-also"></a>另请参阅

- [开发 MAPI 表单服务器](developing-mapi-form-servers.md)

