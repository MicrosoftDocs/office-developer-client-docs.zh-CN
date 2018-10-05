---
title: MAPI 对象和接口概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d4ece3af-cb54-4727-8072-0c055381ec11
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fcd85bf518f4e6466bf15a09e417767bc34df78d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390987"
---
# <a name="mapi-object-and-interface-overview"></a>MAPI 对象和接口概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
C + + 对象类或 C 数据结构从一个或多个 MAPI 接口或相关的函数集继承，MAPI 对象。 下面这些集合相关函数称为于 c + + 开发人员纯虚函数。 对于纯虚函数，MAPI 提供仅函数原型，不实现。 预计的客户端应用程序、 服务提供商或 MAPI 将通过创建继承自接口，且符合的消息的 api 功能描述对象类提供此实现。 只能通过继承的类，可以实例化 MAPI 接口。
  
有许多不同的 MAPI 对象，每个对象继承最终从[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)接口继承的接口。 **IUnknown**是 OLE 组件对象模型 (COM) 基接口。 它为 MAPI 对象提供的标准机制通信和控件。 COM 规定对象实施如何处理如内存管理、 参数管理、 问题和多线程。 通过与此模型，对象实施符合指定合同由对象中包含的接口。 
  
许多 MAPI 接口继承直接从**IUnknown**，而其他人通过其他两个基本接口之一间接继承： [IMAPIProp: IUnknown](imapipropiunknown.md)属性管理和[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)文件夹和通讯簿访问。 作为独立的独立对象; 从不实现基接口始终实现这些其他对象的一部分，实现的对象派生的接口。 
  
MAPI 定义许多类型的对象，每个由一个或多个 MAPI 组件实现。 由客户端实现的对象习惯通过 MAPI、 服务提供商，以及自定义表单组件。 MAPI 和客户端，通常使用由服务提供商实现的对象。 对象实现由表单库提供程序以及其他窗体组件和客户端使用窗体服务器。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MAPI 概念](mapi-concepts.md)

