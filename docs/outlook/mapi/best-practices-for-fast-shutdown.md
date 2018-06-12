---
title: 快速关闭的最佳实践
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ae8a9214-e53f-4c57-8dbe-aa7cc6903aa8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0d9e7caf43bcee654aa92652e94bc8c2ebba18e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774621"
---
# <a name="best-practices-for-fast-shutdown"></a>快速关闭的最佳实践

  
  
**适用于**： Outlook 
  
本主题建议为管理员、 MAPI 客户端和 MAPI 提供程序使用 Windows 注册表设置和快速关闭接口客户端关闭期间减少数据丢失的最佳做法。
  
- MAPI 客户端执行快速关闭成功，以便提供程序进程不会导致数据丢失的 MAPI 客户端应首先调用[IMAPIClientShutdown::QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法。 客户端应然后继续进行基于 MAPI 子系统的支持的快速关闭[IMAPIClientShutdown::NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)和[IMAPIClientShutdown::DoFastShutdown](imapiclientshutdown-dofastshutdown.md)方法由**的返回值IMAPIClientShutdown::QueryFastShutdown**。 作为 MAPI 客户端，Microsoft Outlook 不会调用**IMAPIClientShutdown::NotifyProcessShutdown**或**IMAPIClientShutdown::DoFastShutdown**如果**IMAPIClientShutdown::QueryFastShutdown**将返回错误。 如果管理员已禁用 Windows 注册表中的快速关闭，MAPI 子系统应返回**IMAPIClientShutdown::QueryFastShutdown**MAPI_E_NO_SUPPORT。 在这种情况下，MAPI 子系统不会通知 MAPI 提供程序即时客户过程的退出。 因此，如果 MAPI 客户端将忽略此错误返回代码，继续执行快速关闭，并且断开所有外部引用，所有加载的 MAPI 提供程序将会丢失数据。 
    
- MAPI 提供程序应实现[IMAPIProviderShutdown: IUnknown](imapiprovidershutdowniunknown.md)接口执行及时和所需的步骤，以避免由于客户端断开外部引用客户端退出之前的数据丢失。 提供程序应推迟的其他内容是将数据保存到其主数据存储区不重要。 例如，传输提供程序应推迟检查新邮件，通讯簿提供程序应从其服务器上，下载最新更改推迟的不必要的后台操作和存储提供程序应如推迟维护任务在压缩或索引。 
    
- 要退出只要它们关闭它们的 MAPI 客户端的用户应使用默认注册表设置，使快速关闭，除非将提供程序。
    
- 一旦 MAPI 客户端呼叫**IMAPIClientShutdown::DoFastShutdown**，它不应为 MAPI，包括[MAPIUninitialize](mapiuninitialize.md)函数的任何其他呼叫。 客户端不应使用 MAPI 客户端进程的生存期的其余部分。 
    
- MAPI 客户端应永远不会直接调用提供商的**IMAPIProviderShutdown**接口。 MAPI 客户端应始终使用[IMAPIClientShutdown: IUnknown](imapiclientshutdowniunknown.md)接口。 
    
- 如果 MAPI 提供程序需要以确保它加载时未使用的快速关闭，应实现**IMAPIProviderShutdown**接口并返回 MAPI_E_NO_SUPPORT **IMAPIProviderShutdown::QueryFastShutdown**方法。 但是，如 Outlook 的 MAPI 客户端，这将导致客户端放弃快速关闭并需要很长时间关闭。 
    
## <a name="see-also"></a>另请参阅



[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)
  
[快速关闭概述 （英文)](fast-shutdown-overview.md)
  
[快速关闭用户选项](fast-shutdown-user-options.md)

