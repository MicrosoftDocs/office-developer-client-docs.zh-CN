---
title: 初始化传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 977c18ce-ece5-4ad1-ac97-5a680846ab83
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3b369e20101bbaba5e246b2ef9f6ab3ed1771ef6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563553"
---
# <a name="initializing-the-transport-provider"></a>初始化传输提供程序

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
传输-后台处理程序接口定义 MAPI 后台处理程序向传输提供程序的呼叫。 传输提供程序动态链接库 (DLL) 中实现这些例程。 使用 MAPI 后台处理程序的 DLL 的第一个直接入口点必须传输提供程序初始化函数[XPProviderInit](xpproviderinit.md)。
  
MAPI 使用例程**GetProcAddress**来获取服务提供商的初始化例程的地址，然后调用该例程。 初始化例程的名称是**XPProviderInit**传输提供程序。 使一个 DLL 可以包含服务提供程序类型，但只有一个服务提供程序特定类型的任意组合，它是不同的其他类型的 MAPI 服务提供商。 但是，给定类型的一个服务提供商可以实现与其类型的多项服务。 例如，一个传输提供程序可以实现多个消息服务的邮件传输功能。 
  
Mapispi.h 头文件具有的传输提供程序初始化函数，该函数原型的类型定义和它的预定义的过程名称。 通过使用由**GetProcAddress**并通过使用简单的相同名称命名您的 C 和 c + + 文件中的初始化例程导出 DLL 中的声明。DEF 文件，您将自动获取类型检查的初始化例程的参数。 请参阅示例的示例传输提供程序源代码。 有关详细信息，请参阅[传输提供程序示例](transport-provider-sample.md)。
  
如果服务提供商的初始化调用成功，但返回的服务提供商接口版本号 MAPI 处理的太小，MAPI 立即调用服务提供商对象的**发布**方法和直接如同初始化呼叫具有 MAPI_E_VERSION 失败。 这种方式 MAPI 服务提供商共同定义和号码范围的服务提供程序界面版本能够处理，并使用 MAPI_E_VERSION 失败如果 nothing 匹配，则服务提供商加载返回值。 
  
获取服务提供程序资源的访问权限 MAPI 后台处理程序的最后一步是登录到传输提供程序。 MAPI 后台处理程序调用的[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)方法[IXPProvider: IUnknown](ixpprovideriunknown.md) **XPProviderInit**从返回的对象。 这是的调用其中检查凭据，如果使用，并且可以允许对话框。
  
如果一个进程打开的上同一传输提供程序的第二个传输会话和 MAPI 会话，请传输提供程序 DLL 不应创建第二个提供程序对象。 第一个提供商对象用于登录到第二个传输会话。 应该对传输提供程序进行编程，以支持多个传输会话在单个提供程序对象。 如果在同一个进程使用不同的 MAPI 会话，则只应创建第二个提供程序对象。
  

