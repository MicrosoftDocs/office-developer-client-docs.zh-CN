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
  
MAPI 对象是从一个或多个 MAPI 接口或相关函数集合继承的 C++ 对象类或 C 数据结构。 C++ 开发人员知道这些相关函数集合是纯虚拟函数。 对于纯虚拟函数，MAPI 仅提供函数原型，而不是实现。 客户端应用程序、服务提供商或 MAPI 预期会通过创建继承自接口且符合消息 API 的函数说明的对象类来提供此实现。 MAPI 接口只能通过继承的类实例化。
  
存在许多不同的 MAPI 对象，每个对象都继承自最终继承自 [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) 接口的接口。 **IUnknown** 是 OLE 组件对象模型 (COM) 接口。 它为 MAPI 对象提供了用于通信和控制的标准机制。 COM 规定对象实施者如何处理内存管理、参数管理和多线程等问题。 通过遵循此模型，对象实现者将遵守对象中包含的接口所指定的协定。 
  
许多 MAPI 接口直接继承自 **IUnknown**，而其他接口通过其他两个基接口之一间接继承 [：IMAPIProp：用于属性管理的 IUnknown](imapipropiunknown.md) 和 [IMAPIContainer：用于](imapicontainerimapiprop.md) 文件夹和通讯簿访问的 IMAPIProp。 基接口从不作为独立的独立对象实现;它们始终作为其他对象的一部分实现，即实现派生接口的对象。 
  
MAPI 定义许多类型的对象，每种类型的对象都由一个或多个 MAPI 组件实现。 由客户端实现的对象由 MAPI、服务提供商和自定义表单组件使用。 服务提供商实现的对象通常由 MAPI 和客户端使用。 由表单库提供程序和表单服务器实现的对象由其他表单组件和客户端使用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MAPI 概念](mapi-concepts.md)

