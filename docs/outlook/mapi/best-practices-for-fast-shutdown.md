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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426966"
---
# <a name="best-practices-for-fast-shutdown"></a>快速关闭的最佳实践

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题建议管理员、MAPI 客户端和 MAPI 提供程序使用 Windows 注册表设置和快速关闭接口以在客户端关闭期间最大程度地减少数据丢失的最佳实践。
  
- 若要使 MAPI 客户端成功执行快速关闭，以便提供程序进程不会丢失数据，MAPI 客户端应首先调用 [IMAPIClientShutdown：：QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) 方法。 然后，客户端应基于 MAPI 子系统对快速关闭的支持继续执行 [IMAPIClientShutdown：：NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) 和 [IMAPIClientShutdown：:D oFastShutdown](imapiclientshutdown-dofastshutdown.md) 方法，如 **IMAPIClientShutdown：：QueryFastShutdown** 的返回值所指示。 作为 MAPI 客户端，如果 **IMAPIClientShutdown：：QueryFastShutdown 返回错误，Microsoft Outlook 不会调用 IMAPIClientShutdown：：NotifyProcessShutdown** 或 **IMAPIClientShutdown：:D oFastShutdown。**  如果管理员在注册表中禁用了快速关闭Windows，MAPI 子系统将MAPI_E_NO_SUPPORT **IMAPIClientShutdown：：QueryFastShutdown**。 在这种情况下，MAPI 子系统不会通知 MAPI 提供程序立即退出客户端进程。 因此，如果 MAPI 客户端忽略此错误返回代码，继续执行快速关闭操作并断开所有外部引用，则所有加载的 MAPI 提供程序都将丢失数据。 
    
- MAPI 提供程序应实现 [IMAPIProviderShutdown ： IUnknown](imapiprovidershutdowniunknown.md) 接口，以执行及时的必要步骤，以避免由于客户端在客户端退出之前断开外部引用而丢失数据。 提供程序应推迟将数据保存至其主数据存储不重要的一切其他操作。 例如，传输提供程序应推迟检查新邮件的不必要的后台操作，通讯簿提供程序应推迟从服务器下载最近更改，存储提供程序应推迟维护任务，如压缩或索引。 
    
- 希望 MAPI 客户端在关闭后立即退出的用户应该使用默认注册表设置，此设置可启用快速关闭，除非提供程序选择退出。
    
- 一旦 MAPI 客户端调用 **IMAPIClientShutdown：:D oFastShutdown，** 它不应对 MAPI（包括 [MAPIUninitialize](mapiuninitialize.md) 函数）进行任何其他调用。 客户端不应在客户端进程的生存期的其余部分使用 MAPI。 
    
- MAPI 客户端永远不应直接调用提供程序的 **IMAPIProviderShutdown** 接口。 MAPI 客户端应始终使用 [IMAPIClientShutdown ： IUnknown](imapiclientshutdowniunknown.md) 接口。 
    
- 如果 MAPI 提供程序需要确保在加载时不会使用快速关闭，它应实现 **IMAPIProviderShutdown** 接口，并针对 **IMAPIProviderShutdown：：QueryFastShutdown** 方法返回 MAPI_E_NO_SUPPORT。 但是，对于 MAPI Outlook，这会使客户端放弃快速关闭，并需要较长时间来关闭。 
    
## <a name="see-also"></a>另请参阅



[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)
  
[快速关闭概述](fast-shutdown-overview.md)
  
[快速关闭用户选项](fast-shutdown-user-options.md)

