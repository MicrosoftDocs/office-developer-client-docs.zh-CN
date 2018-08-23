---
title: 对象和 MAPI 体系结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c3bcbda5-820d-4ef5-bffd-c254eea9dff6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 29a61ff8f7894c5582d31895bacd74e1ebcaa49c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583874"
---
# <a name="objects-and-the-mapi-architecture"></a>对象和 MAPI 体系结构

**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 体系结构中的一个或多个图层属于的所有 MAPI 定义对象。 客户端接口层包含客户端应用程序、 窗体查看器或窗体服务器可以实现的所有对象。 服务提供程序接口层包含任何类型的服务提供商可以实现的对象。 该层包括实现通过通讯簿、 消息存储、 传输提供程序和表单库的对象。 代表 MAPI 子系统层位于客户端与服务提供程序界面层之间。 MAPI 层包含的所有客户端或服务提供商使用 MAPI 实现的对象。 
  
下图显示了每个 MAPI 对象到 MAPI 体系结构适合的位置。 对象表示与及其派生接口的名称。 例如，advise 接收器对象显示为[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)，从[iunknown 导出](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)派生并在每个 advise 接收器对象实现的接口。 桥接图层的接口是或使用由多个组件实现。 尽管 MAPI 层显示到单独的客户端和提供程序层，这意味着所有通信必须都流过 MAPI，但这不是这种情况。 客户端可以和执行通信直接向服务提供商对象。 
  
**MAPI 中的对象层**
  
![MAPI 中的对象层](media/amapi_38.gif "MAPI 中的对象层")
  
## <a name="see-also"></a>另请参阅

- [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

