---
title: 对象和 MAPI 体系结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c3bcbda5-820d-4ef5-bffd-c254eea9dff6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4f8bc2a5268d220c17a59148f8b8ba1d320d225b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279784"
---
# <a name="objects-and-the-mapi-architecture"></a>对象和 MAPI 体系结构

**适用于**：Outlook 2013 | Outlook 2016 
  
mapi 定义的所有对象都属于 mapi 体系结构中的一个或多个层。 客户端接口层包含客户端应用程序、窗体查看器或窗体服务器可以实现的所有对象。 服务提供程序接口层包含任何类型的服务提供程序可以实现的对象。 此层包括由通讯簿、邮件存储、传输提供程序和表单库实现的对象。 代表 MAPI 子系统的层位于客户端和服务提供程序接口层之间。 mapi 层包含 mapi 为要使用的客户端或服务提供程序实现的所有对象。 
  
下图显示了每个 mapi 对象适合 mapi 体系结构的位置。 这些对象使用其派生接口的名称表示。 例如, 建议接收器对象显示为[IMAPIAdviseSink: iunknown](imapiadvisesinkiunknown.md)、派生自[iunknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)的接口以及每个建议接收器对象实现。 桥接层的接口或者由多个组件使用或实现。 虽然 MAPI 层显示为单独的客户端和提供程序层, 但意味着所有通信都必须通过 MAPI, 这不是这种情况。 客户端可以直接与服务提供程序对象进行通信。 
  
**MAPI 中的对象层**
  
![MAPI 中的对象层](media/amapi_38.gif "MAPI 中的对象层")
  
## <a name="see-also"></a>另请参阅

- [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

