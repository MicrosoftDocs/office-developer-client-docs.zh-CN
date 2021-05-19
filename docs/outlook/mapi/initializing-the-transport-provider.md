---
title: 初始化传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 977c18ce-ece5-4ad1-ac97-5a680846ab83
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 474a8085ca8b82d11efd68c9fd4d8719fe239207
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416599"
---
# <a name="initializing-the-transport-provider"></a>初始化传输提供程序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
transport-spooler 接口定义 MAPI 后台处理程序对传输提供程序的调用。 传输提供程序在动态链接库中实现这些例程 (DLL) 。 MAPI 后台处理程序使用的 DLL 的第一个直接入口点必须是传输提供程序初始化函数 [XPProviderInit](xpproviderinit.md)。
  
MAPI 使用 **例程 GetProcAddress** 获取服务提供商的初始化例程的地址，然后调用该例程。 对于传输提供程序，初始化例程的名称为 **XPProviderInit。** 对于其他类型的 MAPI 服务提供程序，这有所不同，因此一个 DLL 可以包含任何服务提供程序类型组合，但只能包含一个特定类型的服务提供程序。 但是，给定类型的一个服务提供商可以实现其类型的多个服务。 例如，一个传输提供程序可以将邮件传输功能实现到多个邮件服务。 
  
mapispi.h 头文件具有传输提供程序初始化函数的函数原型的类型定义，以及它的预定义过程名称。 通过使用 **GetProcAddress** 使用的相同名称在 C 和 C++ 文件中命名初始化例程，在 DLL.DEF 文件中使用简单的导出声明，可自动获取初始化例程上参数的类型检查。 有关示例，请参阅示例传输提供程序源代码。 有关详细信息，请参阅传输 [提供程序示例](transport-provider-sample.md)。
  
如果服务提供商的初始化调用成功，但返回的服务提供商接口版本号太小，MAPI 无法处理，MAPI 将立即调用服务提供商对象的 **Release** 方法，然后继续，就像初始化调用在 MAPI_E_VERSION 中失败一样。 这样，MAPI 和服务提供商可以一起定义他们可以处理的服务提供商接口版本号的范围，如果没有任何匹配项，则服务提供程序加载将失败，MAPI_E_VERSION值。 
  
MAPI 后台处理程序获取对服务提供商资源的访问权限的最后一步是登录到传输提供程序。 MAPI 后台处理程序调用从 **XPProviderInit** 返回的 [IXPProvider ： IUnknown](ixpprovideriunknown.md)对象的 IXPProvider：：TransportLogon 方法。 [](ixpprovider-transportlogon.md) 这是检查凭据（如果使用）并允许对话框的调用。
  
如果进程在同一传输提供程序和 MAPI 会话上打开第二个传输会话，则传输提供程序 DLL 不应创建第二个提供程序对象。 第一个提供程序对象应该用于登录到第二个传输会话。 传输提供程序应进行编程以支持单个提供程序对象中的多个传输会话。 只有当同一进程中使用不同的 MAPI 会话时，才应创建第二个提供程序对象。
  

