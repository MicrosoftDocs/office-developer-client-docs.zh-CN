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
  
允许 MAPI 子系统通知 MAPI 提供程序快速关闭 MAPI 客户端，以便 MAPI 提供程序可以响应关闭。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |提供程序对象[：IXPProvider、IABProvider](ixpprovideriunknown.md)或[IMSProvider](imsprovideriunknown.md) [](iabprovideriunknown.md) <br/> |
|实现者：  <br/> |MAPI 提供程序  <br/> |
|调用者：  <br/> |MAPI 子系统  <br/> |
|接口标识符：  <br/> |IID_IMAPIProviderShutdown  <br/> |
|指针类型：  <br/> |LPMAPIPROVIDERSHUTDOWN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) <br/> |向 MAPI 提供程序查询快速关闭支持。  <br/> |
|[NotifyProcessShutdown](imapiprovidershutdown-notifyprocessshutdown.md) <br/> |向 MAPI 提供程序指示 MAPI 客户端将快速关闭，以便提供程序可以采取措施防止数据丢失。  <br/> |
|[DoFastShutdown](imapiprovidershutdown-dofastshutdown.md) <br/> |向 MAPI 提供程序指示 MAPI 客户端正在立即退出，以便 MAPI 提供程序将保留更改以防止数据丢失。  <br/> |
   
## <a name="remarks"></a>备注

快速关闭允许 MAPI 客户端在短时间内退出其进程，希望在客户端和加载的 MAPI 提供程序保存 MAPI 设置和数据之后。 MAPI 客户端始终启动快速关闭，并且应查询 MAPI 子系统，以从已加载的 MAPI 提供程序获得快速关闭支持。 管理员可以在用户级别Windows注册表，以指定允许快速关闭所有 MAPI 客户端所需的提供程序支持级别。 有关注册表设置的详细信息，请参阅快速 [关闭用户选项](fast-shutdown-user-options.md)。 但是，若要在未丢失数据的情况下成功成功关闭，MAPI 提供程序应实现 **IMAPIProviderShutdown** 接口。 
  
需要支持客户端快速关闭的 MAPI 提供程序应S_OK **IMAPIProviderShutdown：：QueryFastShutdown** 方法中的 MAPI 子系统。 当 MAPI 子系统随后调用 **IMAPIProviderShutdown：：NotifyProcessShutdown** 和 **IMAPIProviderShutdown：:D oFastShutdown** 方法时，MAPI 提供程序应执行必要的操作来保存 MAPI 设置和数据，并准备客户端退出。 
  
无需支持客户端快速关闭的 MAPI 提供程序仍应实现 **IMAPIProviderShutdown** 接口，并且让 **IMAPIProviderShutdown：：QueryFastShutdown** 方法返回 MAPI_E_NO_SUPPORT。 对于Outlook MAPI 客户端，这将导致Outlook等待所有外部引用在退出之前释放。 
  
根据用户的快速关闭Windows设置，不实现 **IMAPIProviderShutdown** 接口不一定阻止客户端快速关闭。 
  
有关快速关闭过程详细信息，请参阅 [快速关闭概述](fast-shutdown-overview.md)。 若要了解如何成功执行快速关闭，请参阅[Best Practices for Fast Shutdown。](best-practices-for-fast-shutdown.md)
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)
  
[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

