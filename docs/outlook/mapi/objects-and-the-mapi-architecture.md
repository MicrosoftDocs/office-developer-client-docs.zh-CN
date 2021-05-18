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
  
MAPI 定义的所有对象都属于 MAPI 体系结构中的一个或多个层。 客户端接口层包含客户端应用程序、表单查看器或表单服务器可以实现的所有对象。 服务提供程序接口层包含任何类型的服务提供商可以实现的对象。 此层包括通讯簿、邮件存储、传输提供程序和表单库实现的对象。 表示 MAPI 子系统的层位于客户端和服务提供商接口层之间。 MAPI 层包含 MAPI 实现供客户端或服务提供商使用的所有对象。 
  
下图显示了每个 MAPI 对象适合 MAPI 体系结构的位置。 这些对象用其派生接口的名称表示。 例如，通知接收对象显示为 [IMAPIAdviseSink ： IUnknown，](imapiadvisesinkiunknown.md)它是从 [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) 派生的接口，并且每个通知接收器对象都实现。 桥层的接口由多个组件使用或实现。 尽管 MAPI 层似乎将客户端层和提供程序层分开，但这意味着所有通信都必须通过 MAPI 进行，但情况并非如此。 客户端可以直接与服务提供商对象通信，也可以与服务提供商对象直接通信。 
  
**MAPI 中的对象层**
  
MAPI![中的 MAPI](media/amapi_38.gif "对象层中的对象层")
  
## <a name="see-also"></a>另请参阅

- [IMAPIAdviseSink : IUnknown](imapiadvisesinkiunknown.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

