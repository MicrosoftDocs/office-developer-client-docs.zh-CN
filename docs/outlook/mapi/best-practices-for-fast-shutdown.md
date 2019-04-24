---
title: 快速关闭的最佳实践
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ae8a9214-e53f-4c57-8dbe-aa7cc6903aa8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8c7225427b80d89c6dd8adfa85f7d91885850365
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318142"
---
# <a name="best-practices-for-fast-shutdown"></a>快速关闭的最佳实践

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题为管理员、mapi 客户端和 mapi 提供程序推荐了使用 Windows 注册表设置和 fast shutdown 接口的最佳做法, 以最大限度地减少客户端关闭期间的数据丢失。
  
- 为了使 mapi 客户端成功执行快速关机, 以便提供程序进程不会丢失数据, MAPI 客户端应首先调用[IMAPIClientShutdown:: QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md)方法。 然后, 客户端应继续[IMAPIClientShutdown:: NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md)和[IMAPIClientShutdown:](imapiclientshutdown-dofastshutdown.md)基于 MAPI 子系统支持快速关机的 ofastshutdown 方法, 如返回值**为IMAPIClientShutdown:: QueryFastShutdown**。 作为 MAPI 客户端, Microsoft Outlook 不会调用**IMAPIClientShutdown:: NotifyProcessShutdown**或**IMAPIClientShutdown::D ofastshutdown**如果**IMAPIClientShutdown:: QueryFastShutdown**返回错误。 如果管理员已在 Windows 注册表中禁用 fast shutdown, MAPI 子系统将返回 MAPI_E_NO_SUPPORT to **IMAPIClientShutdown:: QueryFastShutdown**。 在这种情况下, mapi 子系统不会通知 mapi 提供程序即时客户端进程退出。 因此, 如果 MAPI 客户端忽略此错误, 则会继续快速关闭并断开所有外部引用, 所有加载的 MAPI 提供程序都将丢失数据。 
    
- MAPI 提供程序应实现[IMAPIProviderShutdown: IUnknown](imapiprovidershutdowniunknown.md)接口, 以执行及时和必要的步骤, 以避免由于客户端在客户端退出前断开外部引用而导致数据丢失。 提供程序应将数据保存到其主数据存储区中不必要的所有其他项。 例如, 传输提供程序应推迟检查新邮件的不必要的后台操作, 通讯簿提供程序应延迟从其服务器下载最近更改, 并且存储提供程序应延迟维护任务, 例如压缩或编制索引。 
    
- 希望 MAPI 客户端在关闭时立即退出的用户应使用默认注册表设置, 除非提供程序弹出, 否则启用快速关机。
    
- MAPI 客户端调用**IMAPIClientShutdown::D ofastshutdown**后, 它不应对 MAPI 进行任何其他调用, 包括[MAPIUninitialize](mapiuninitialize.md)函数。 客户端不应将 MAPI 用于其他客户端进程的生存期。 
    
- MAPI 客户端决不应直接调用提供程序的**IMAPIProviderShutdown**接口。 MAPI 客户端应始终使用[IMAPIClientShutdown: IUnknown](imapiclientshutdowniunknown.md)接口。 
    
- 如果 MAPI 提供程序需要确保在加载过程中不使用 fast shutdown, 它应实现**IMAPIProviderShutdown**接口, 并返回 MAPI_E_NO_SUPPORT for the **IMAPIProviderShutdown:: QueryFastShutdown**方法。 但是, 对于 Outlook 这样的 MAPI 客户端, 这将导致客户端放弃快速关机并花费更长的时间来关闭。 
    
## <a name="see-also"></a>另请参阅



[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)
  
[快速关闭概述](fast-shutdown-overview.md)
  
[快速关闭用户选项](fast-shutdown-user-options.md)

