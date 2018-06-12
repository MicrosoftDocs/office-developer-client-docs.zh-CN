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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a679d04f7697abbe0172105febf87082c0cd9946
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775573"
---
# <a name="imapiprovidershutdown--iunknown"></a>IMAPIProviderShutdown: IUnknown

  
  
**适用于**： Outlook 
  
允许 MAPI 子系统通知的 MAPI 客户端，快速关闭 MAPI 提供程序，以便 MAPI 提供程序可以响应关闭。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |提供商对象： [IXPProvider](ixpprovideriunknown.md)、 [IABProvider](iabprovideriunknown.md)或[IMSProvider](imsprovideriunknown.md) <br/> |
|通过实现：  <br/> |MAPI 提供程序  <br/> |
|调用：  <br/> |MAPI 子系统  <br/> |
|接口标识符：  <br/> |IID_IMAPIProviderShutdown  <br/> |
|指针类型：  <br/> |LPMAPIPROVIDERSHUTDOWN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[QueryFastShutdown](imapiprovidershutdown-queryfastshutdown.md) <br/> |查询快速关闭 MAPI 提供程序支持。  <br/> |
|[NotifyProcessShutdown](imapiprovidershutdown-notifyprocessshutdown.md) <br/> |表示的 MAPI 提供程序，MAPI 客户端将要执行快速关闭，以便提供程序可以执行操作，以防止数据丢失。  <br/> |
|[DoFastShutdown](imapiprovidershutdown-dofastshutdown.md) <br/> |指示到 MAPI 提供程序 MAPI 客户端立即退出以便 MAPI 提供程序将保留更改以防止数据丢失。  <br/> |
   
## <a name="remarks"></a>备注

快速关闭允许 MAPI 客户端退出短时间内的其进程，希望客户端后，并加载 MAPI 提供程序已保存 MAPI 设置和数据。 MAPI 客户端始终发起快速关闭，并应查询的 MAPI 子系统的快速关闭加载 MAPI 提供程序的支持。 管理员可以设置在用户级别指定的所需允许快速关闭所有 MAPI 客户端提供程序支持级别的 Windows 注册表。 有关注册表设置的详细信息，请参阅[Fast 关闭用户选项](fast-shutdown-user-options.md)。 但是，对于快速关闭成功发生丢失数据，MAPI 提供程序应实现**IMAPIProviderShutdown**接口。 
  
需要支持客户端快速关闭 MAPI 提供程序应到 MAPI 子系统在**IMAPIProviderShutdown::QueryFastShutdown**方法返回 S_OK。 MAPI 提供程序的 MAPI 子系统随后呼叫的**IMAPIProviderShutdown::NotifyProcessShutdown**和**IMAPIProviderShutdown::DoFastShutdown**方法时, 应采取必要的操作以保存 MAPI 设置和数据和准备客户端的退出。 
  
MAPI 提供程序不需要支持客户端快速关闭仍应实现**IMAPIProviderShutdown**接口，并让 MAPI_E_NO_SUPPORT **IMAPIProviderShutdown::QueryFastShutdown**方法。 对于作为 MAPI 客户端的 Outlook，这会导致 Outlook 等待它退出之前，必须释放的所有外部引用。 
  
根据用户的 Windows 注册表设置的快速关闭不实现**IMAPIProviderShutdown**接口不一定是阻止客户端快速关闭。 
  
有关的快速关闭进程的详细信息，请参阅[快速关闭概述](fast-shutdown-overview.md)。 有关如何成功执行快速关闭的信息，请参阅[快速关闭的最佳实践](best-practices-for-fast-shutdown.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)
  
[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

