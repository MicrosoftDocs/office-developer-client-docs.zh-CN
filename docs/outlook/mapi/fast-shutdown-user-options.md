---
title: 快速关闭用户选项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
api_type:
- COM
ms.assetid: 220aeab5-20f6-4520-96c9-8aaa0e8ea15b
description: 上次修改时间：2012 年 6 月 26 日
localization_priority: Priority
ms.openlocfilehash: 3c60862733c6b38e60650ae9daba9bba578fcd58
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341074"
---
# <a name="fast-shutdown-user-options"></a>快速关闭用户选项

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题介绍了从 Microsoft Outlook 2010 起（现包括 Microsoft Outlook 2013）用于快速关闭用户的 MAPI 客户端的三个 Windows 注册表设置。 根据 MAPI 提供程序对客户端快速关闭的支持，管理员可以使用这些注册表设置来指定首选客户端关闭行为。 反过来，管理员设置将决定 MAPI 子系统如何按照可用快速关闭支持来响应 MAPI 客户端对 [IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) 的调用。 
  
即便注册表设置可以反映管理员在用户级别对所有 MAPI 客户端快速关闭的首选项，MAPI 客户端开发人员也可以决定客户端是否支持独立快速关闭其他 MAPI 客户端以及管理员的注册表设置。 尽管如此，如需成功快速关闭，用户必须对注册表进行必要的设置，MAPI 客户端必须通过使用 [IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md) 接口启动快速关闭，并且与客户端搭配使用的 MAPI 提供程序应使用 [IMAPIProviderShutdown : IUnknown](imapiprovidershutdowniunknown.md) 接口支持客户端快速关闭。 
  
以下列表介绍了三个用户级别选项。
  
### <a name="option-1-the-mapi-subsystem-enables-fast-shutdown-unless-mapi-providers-explicitly-opt-out"></a>选项 1：MAPI 子系统支持快速关闭，除非 MAPI 提供程序显式选择退出 
    
从 Outlook 2010 起，如果 Outlook 为 MAPI 客户端，则这为默认行为；但如果是其他 MAPI 客户端，则这不一定是默认行为。 若要为 Outlook 显式指定此选项，则管理员可以选择设置以下注册表项和值。
    
注册表项：
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
值:
  
>  `"FastShutdownBehavior"=dword:00000000`
    
只要具有活动 MAPI 会话及 MAPI 客户端的所有 MAPI 提供程序均未显式选择退出快速关闭支持，则当 MAPI 客户端启动快速关闭并调用 **IMAPIClientShutdown::QueryFastShutdown** 以查询快速关闭支持，MAPI 子系统将返回 S\_OK 以响应查询。 

MAPI 提供程序通过使用 [IMAPIProviderShutdown::QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) 方法返回错误 (MAPI\_E\_NO\_SUPPORT) 来选择退出快速关闭支持。 如果一个或多个 MAPI 提供程序在 **IMAPIProviderShutdown::QueryFastShutdown** 中返回错误，则 MAPI 子系统将返回 MAPI_\E_\NO\_SUPPORT 至 **IMAPIClientShutdown::QueryFastShutdown**。 

除非 MAPI 提供程序选择退出，否则即便一个或多个提供程序未使用 **IMAPIProviderShutdown : IUnknown** 接口，MAPI 子系统也会返回 S\_OK。 
    
### <a name="option-2-the-mapi-subsystem-enables-fast-shutdown-only-if-every-mapi-provider-explicitly-opts-in"></a>选项 2：仅当每个 MAPI 提供程序显式选择加入时，MAPI 子系统才支持快速关闭 
    
管理员必须显式设置以下注册表项和值才能为客户端快速关闭指定此首选项。
    
注册表项：
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
值:
  
>  `"FastShutdownBehavior"=dword:00000001`
    
如果具有活动会话及 MAPI 客户端的所有 MAPI 提供程序支持快速关闭，则当 MAPI 客户端启动快速关闭并调用 **IMAPIClientShutdown::QueryFastShutdown** 以查询快速关闭支持时，MAPI 子系统将返回 S\_OK 以响应查询。 MAPI 提供程序通过使用 **IMAPIProviderShutdown::QueryFastShutdown** 以返回非错误代码 (S\_OK) 来演示其支持。 

如果一个或多个 MAPI 提供程序返回 MAPI\_E\_NO\_SUPPORT，或者未使用 **IMAPIProviderShutdown::QueryFastShutdown**，则 MAPI 子系统将返回错误代码至 **IMAPIClientShutdown::QueryFastShutdown**。
    
### <a name="option-3-an-administrator-disables-support-for-client-fast-shutdown"></a>选项 3：管理员禁用客户端快速关闭支持
    
管理员必须显式设置以下注册表项和值才能禁用客户端快速关闭支持。
    
注册表项：
  
>  `[HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\14.0\Outlook\Options\Shutdown]`
    
值:
  
>  `"FastShutdownBehavior"=dword:00000002`
    
无论任何 MAPI 提供程序是否支持快速关闭，当 MAPI 客户端启动快速关闭并调用 **IMAPIClientShutdown::QueryFastShutdown** 以响应快速关闭支持时，MAPI 子系统均会返回 MAPI_E_NO_SUPPORT 以响应查询。 在此注册表设置下，MAPI 子系统永远不会调用任何提供程序的 **IMAPIProviderShutdown::QueryFastShutdown** 或 [IMAPIProviderShutdown::DoFastShutdown](imapiprovidershutdown-dofastshutdown.md) 方法。 
    
## <a name="see-also"></a>另请参阅

- [MAPI 中的客户端关闭](client-shutdown-in-mapi.md)
- [快速关闭概述](fast-shutdown-overview.md)
- [快速关闭最佳做法](best-practices-for-fast-shutdown.md)

