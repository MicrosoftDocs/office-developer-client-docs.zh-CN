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
  
传输后台处理程序接口定义 MAPI 后台处理程序对传输提供程序的调用。 传输提供程序在动态链接库 (DLL) 中实现这些例程。 MAPI 后台处理程序使用的 DLL 的第一个直接入口点必须是传输提供程序初始化函数[XPProviderInit](xpproviderinit.md)。
  
MAPI 使用例程**GetProcAddress**获取服务提供程序的初始化例程的地址, 然后调用该例程。 初始化例程的名称是传输提供程序的**XPProviderInit** 。 其他类型的 MAPI 服务提供程序是不同的, 因此一个 DLL 可以包含服务提供程序类型的任意组合, 但只有一个特定类型的服务提供程序。 但是, 给定类型的一个服务提供程序可以实现其类型的多个服务。 例如, 一个传输提供程序可以实现邮件传输到多个邮件服务的功能。 
  
mapispi 头文件具有传输提供程序初始化函数的 function 原型的类型定义以及它的预定义过程名称。 通过在您的 C 和 c + + 文件中使用与**GetProcAddress**相同的名称命名的初始化例程以及在 DLL 中使用简单的导出声明来命名这些例程。DEF 文件中, 您将自动获取对初始化例程上参数的类型检查。 有关示例, 请参阅传输提供程序的示例源代码。 有关详细信息, 请参阅[传输提供程序示例](transport-provider-sample.md)。
  
如果服务提供程序的初始化调用成功, 但返回的服务提供程序接口版本号太小, mapi 无法处理, mapi 将立即调用服务提供程序对象的**Release**方法, 如同初始化调用一样失败, MAPI_E_VERSION。 通过这种方式, MAPI 和服务提供商可以共同定义他们可以处理的服务提供程序接口版本号的范围, 如果没有匹配项, 则服务提供程序加载将失败, 并返回 MAPI_E_VERSION 返回值。 
  
MAPI 后台处理程序获取服务提供程序资源访问权限的最后一步是登录到传输提供程序。 MAPI 后台处理程序调用从**XPProviderInit**返回的[IXPProvider: IUnknown](ixpprovideriunknown.md)对象的[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)方法。 此呼叫将选中凭据 (如果已使用), 并且可以允许使用对话框。
  
如果某个进程在同一传输提供程序和 MAPI 会话中打开了第二个传输会话, 则传输提供程序 DLL 不应创建第二个 provider 对象。 应使用第一个 provider 对象登录到第二个传输会话。 应将传输提供程序设计为支持单个提供程序对象中的多个传输会话。 仅当在同一进程中使用不同的 MAPI 会话时, 才应创建第二个提供程序对象。
  

