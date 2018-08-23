---
title: 窗体状态
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dfc9fbf1-90d4-4756-92d9-032ac56a9c50
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 195a82bfcc163ee01d2d42c71e79a8f5c9c620e5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564631"
---
# <a name="form-states"></a>窗体状态

**适用于**： Outlook 2013 |Outlook 2016 
  
窗体对象可以五个不同的状态，具体取决于在其中调用了哪些方法和是否任何错误发生在执行这些方法之一。 以下主题中描述的状态：
  
- [Uninitialized 状态](uninitialized-state.md)
    
- [Normal 状态](normal-state.md)
    
- [NoScribble 状态](noscribble-state.md)
    
- [HandsOffAfterSave 状态](handsoffaftersave-state.md)
    
- [HandsOffFromNormal 状态](handsofffromnormal-state.md)
    
状态主要与窗体对象中的数据的状态。 不同的状态反映是否需要将数据保存，是否 form 对象应允许修改数据和内容指向保存窗体处于的数据的过程。 因此，窗体状态和它们之间的转换有更如何处理您的窗体服务器实现[IPersistMessage: IUnknown](ipersistmessageiunknown.md)接口比其他方法。 非常有用的 MAPI 表单接口的窗体服务器必须实现的正确实施这些状态的知识。 
  
本节中的主题介绍各种状态，以及允许导致切换到其他状态的操作。 不允许使用主题中未列出任何转换。 如果表单对象进行状态之间不允许的切换，它们将不行为消息客户端期望，并且可能会导致无法预料的客户端或窗体对象的行为方式。
  
> [!NOTE]
> 某些状态转换取决于从以前的状态信息。 窗体服务器很可能会在其表单对象，以指示该消息的属性的值是否已被更改以加快更高版本的状态更改中实现一个标志。 
  
## <a name="see-also"></a>另请参阅

- [开发 MAPI 表单服务器](developing-mapi-form-servers.md)

