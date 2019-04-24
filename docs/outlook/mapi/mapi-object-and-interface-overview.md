---
title: MAPI 对象和接口概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d4ece3af-cb54-4727-8072-0c055381ec11
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fcd85bf518f4e6466bf15a09e417767bc34df78d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345785"
---
# <a name="mapi-object-and-interface-overview"></a>MAPI 对象和接口概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 对象是从一个或多个 MAPI 接口或相关函数集合继承的 c + + 对象类或 C 数据结构。 这些相关函数集合是 c + + 开发人员已知的纯虚函数。 对于纯虚函数, MAPI 仅提供函数原型, 而不提供实现。 预计客户端应用程序、服务提供程序或 MAPI 将通过以下方式提供此实现: 创建一个继承自接口的对象类, 并符合消息传递 API 的函数说明。 只能通过继承的类来实例化 MAPI 接口。
  
有许多不同的 MAPI 对象, 从最终继承自[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)接口的接口继承的每个对象。 **IUnknown**是 OLE 组件对象模型 (COM) 基接口。 它为 MAPI 对象提供了用于通信和控制的标准机制。 COM 决定了对象实施者如何处理内存管理、参数管理和多线程等问题。 通过符合此模型, 对象实施者遵循对象中包含的接口指定的协定。 
  
许多 MAPI 接口直接从**IUnknown**继承, 而另一些则是通过两个其他基本接口之一间接继承: [IMAPIProp:](imapipropiunknown.md) property management 和 IMAPIContainer 的 IUnknown: [IMAPIProp](imapicontainerimapiprop.md) for folder and通讯簿访问。 基接口永远不会作为单独的独立对象实现;它们始终作为其他对象 (实现派生接口的对象) 的一部分实现。 
  
MAPI 定义了许多类型的对象, 每个对象都由一个或多个 MAPI 组件实现。 由 MAPI、服务提供商和自定义表单组件使用由客户端实现的对象。 由服务提供程序实现的对象通常由 MAPI 和客户端使用。 由窗体库提供程序和窗体服务器实现的对象由其他表单组件和客户端使用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MAPI 概念](mapi-concepts.md)

