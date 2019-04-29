---
title: IMAPIProviderShutdown IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProviderShutdown
api_type:
- COM
ms.assetid: fd86c8a5-f251-46c3-ace9-515e94e504ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 92067b5badfb2aab40f3b3735a164bc09321702c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409655"
---
# <a name="imapiprovidershutdown--iunknown"></a>IMAPIProviderShutdown : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
允许 mapi 子系统将 mapi 客户端的快速关闭通知给 mapi 提供程序, 以便 mapi 提供程序可以响应关闭操作。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|公开者:  <br/> |Provider 对象: [IXPProvider](ixpprovideriunknown.md)、 [IABProvider](iabprovideriunknown.md)或[IMSProvider](imsprovideriunknown.md) <br/> |
|实现者：  <br/> |MAPI 提供程序  <br/> |
|调用者：  <br/> |MAPI 子系统  <br/> |
|接口标识符:  <br/> |IID_IMAPIProviderShutdown  <br/> |
|指针类型:  <br/> |LPMAPIPROVIDERSHUTDOWN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) <br/> |查询 MAPI 提供程序以获取快速关闭支持。  <br/> |
|[NotifyProcessShutdown](imapiprovidershutdown-notifyprocessshutdown.md) <br/> |向 mapi 提供程序指示 mapi 客户端即将执行快速关闭, 以便提供程序可以采取措施来防止数据丢失。  <br/> |
|[DoFastShutdown](imapiprovidershutdown-dofastshutdown.md) <br/> |向 mapi 提供程序指示 mapi 客户端立即退出, 以便 mapi 提供程序将保留所做的更改以防止数据丢失。  <br/> |
   
## <a name="remarks"></a>说明

Fast shutdown 允许 MAPI 客户端在短时间内退出其进程, 因此在客户端和加载的 mapi 提供程序保存了 mapi 设置和数据之后, 也是如此。 mapi 客户端总是启动快速关闭, 并应查询 mapi 子系统, 以便从加载的 MAPI 提供程序中快速关闭支持。 管理员可以在用户级别设置 Windows 注册表, 以指定允许快速关闭所有 MAPI 客户端所必需的提供程序支持级别。 有关注册表设置的详细信息, 请参阅[Fast Shutdown User Options](fast-shutdown-user-options.md)。 但是, 为了使快速关闭在不丢失数据的情况下成功进行, MAPI 提供程序应实现**IMAPIProviderShutdown**接口。 
  
需要支持客户端快速关闭的 MAPI 提供程序应将 S_OK 返回到**IMAPIProviderShutdown:: QueryFastShutdown**方法中的 MAPI 子系统。 当 mapi 子系统随后调用**IMAPIProviderShutdown:: NotifyProcessShutdown**和**IMAPIProviderShutdown::D ofastshutdown**方法时, mapi 提供程序应执行必要的操作以保存 MAPI 设置和数据, 并准备客户端退出。 
  
如果 MAPI 提供程序不需要支持客户端快速关闭, 则仍应实现**IMAPIProviderShutdown**接口, 并让**IMAPIProviderShutdown:: QueryFastShutdown**方法返回 MAPI_E_NO_SUPPORT。 对于 outlook 作为 MAPI 客户端, 这会导致 Outlook 等待所有外部引用在退出之前发布。 
  
根据用户的 Windows 注册表设置快速关闭, 不实现**IMAPIProviderShutdown**接口不一定会阻止客户端快速关闭。 
  
有关快速关机过程的详细信息, 请参阅[fast shutdown 概述](fast-shutdown-overview.md)。 有关如何成功执行快速关机的信息, 请参阅[fast shutdown 的最佳实践](best-practices-for-fast-shutdown.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)
  
[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

