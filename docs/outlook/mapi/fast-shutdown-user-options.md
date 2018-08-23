---
title: 快速关闭用户选项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 220aeab5-20f6-4520-96c9-8aaa0e8ea15b
description: 上次修改时间： 2012 年 6 月 26 日
ms.openlocfilehash: bd541ed09bc661f3697408d3f475928b9ef0bcc1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585190"
---
# <a name="fast-shutdown-user-options"></a>快速关闭用户选项

**适用于**： Outlook 2013 |Outlook 2016 
  
本主题介绍的三个 Windows 注册表设置的可用，Microsoft Outlook 2010 中启动和现在包括 Microsoft Outlook 2013 的用户的 MAPI 客户端的快速关闭。 管理员可以使用这些注册表设置来指定根据 MAPI 提供程序支持的客户端快速关闭的首选的客户端关闭行为。 反过来，管理员的设置确定如何 MAPI 子系统响应[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方面提供快速关闭支持 MAPI 客户端的呼叫。 
  
即使注册表设置的所有 MAPI 客户端反映在用户级别的快速关闭的管理员的首选项，MAPI 客户端开发人员可以决定是否在客户端支持快速关闭独立于其他 MAPI 客户端和管理员的注册表设置。 不过的快速关闭执行成功，用户必须拥有所需的注册表设置，MAPI 客户端必须使用启动快速关闭[IMAPIClientShutdown: IUnknown](imapiclientshutdowniunknown.md)接口，并使用的 MAPI 提供程序客户端应实现[IMAPIProviderShutdown: IUnknown](imapiprovidershutdowniunknown.md)接口以支持客户端快速关闭。 
  
以下列表介绍的三个用户级别选项。
  
### <a name="option-1-the-mapi-subsystem-enables-fast-shutdown-unless-mapi-providers-explicitly-opt-out"></a>选项 1: MAPI 子系统启用快速关闭，除非明确退出 MAPI 提供程序 
    
启动 Outlook 2010 中，这是默认行为 Outlook MAPI 客户端，则时它不一定是其他 MAPI 客户端的默认行为。 若要显式指定 Outlook 此选项，管理员可以选择设置以下注册表项和值。
    
注册表项：
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
值：
  
>  `"FastShutdownBehavior"=dword:00000000`
    
在 MAPI 客户端发起快速关闭，并调用**IMAPIClientShutdown::QueryFastShutdown**查询快速关闭支持，MAPI 子系统响应查询通过返回 S\_会长达具有活动的 MAPI 没有 MAPI 提供程序单击确定与 MAPI 客户端会话已明确选择出快速关闭支持。 

MAPI 提供程序将超出快速关闭通过实现[IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md)方法返回的错误 (MAPI\_E\_无\_支持)。 如果一个或多个 MAPI 提供程序中**IMAPIProviderShutdown::QueryFastShutdown**返回错误，MAPI 子系统返回 MAPI_\E_\NO\_ **IMAPIClientShutdown::QueryFastShutdown**支持。 

除非将 MAPI 提供程序，MAPI 子系统返回 S\_单击确定，即使未实现一个或多个提供程序**IMAPIProviderShutdown: IUnknown**接口。 
    
### <a name="option-2-the-mapi-subsystem-enables-fast-shutdown-only-if-every-mapi-provider-explicitly-opts-in"></a>选项 2: MAPI 子系统启用快速关闭才中明确将每个 MAPI 提供程序 
    
管理员必须明确设置以下注册表项和值，以指定的客户端快速关闭此首选项。
    
注册表项：
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
值：
  
>  `"FastShutdownBehavior"=dword:00000001`
    
在 MAPI 客户端发起快速关闭，并调用**IMAPIClientShutdown::QueryFastShutdown**查询快速关闭支持，MAPI 子系统响应查询通过返回 S\_单击确定如果所有 MAPI 提供程序都具有与活动会话MAPI 客户端支持快速关闭。 MAPI 提供程序说明其支持通过实现**IMAPIProviderShutdown::QueryFastShutdown**返回非错误代码 (S\_确定)。 

如果一个或多个此类 MAPI 提供程序返回 MAPI\_E\_无\_支持或不实现**IMAPIProviderShutdown::QueryFastShutdown**，MAPI 子系统到**IMAPIClientShutdown::QueryFastShutdown**返回错误代码.
    
### <a name="option-3-an-administrator-disables-support-for-client-fast-shutdown"></a>选项 3： 管理员禁用支持的客户端快速关闭
    
管理员必须明确设置以下注册表项和值，以禁用支持的客户端快速关闭。
    
注册表项：
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
值：
  
>  `"FastShutdownBehavior"=dword:00000002`
    
在 MAPI 客户端发起快速关闭，并调用**IMAPIClientShutdown::QueryFastShutdown**查询快速关闭支持，MAPI 子系统响应查询通过无论是否返回 MAPI_E_NO_SUPPORT，任何 MAPI 提供程序支持快速关闭。 在此注册表设置下, MAPI 子系统永远不会调用的任何提供程序的**IMAPIProviderShutdown::QueryFastShutdown**或[IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md)方法。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 中的客户端关闭](client-shutdown-in-mapi.md)
- [快速关闭概述](fast-shutdown-overview.md)
- [快速关闭的最佳实践](best-practices-for-fast-shutdown.md)

