---
title: IMAPIClientShutdown IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIClientShutdown
api_type:
- COM
ms.assetid: b6a5096f-ad27-48b3-b569-f33efc20fa72
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 279d6109e8c29de204c4fb58da51de84b4fbe183
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435332"
---
# <a name="imapiclientshutdown--iunknown"></a>IMAPIClientShutdown : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使 MAPI 客户端能够快速关闭客户端进程。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|公开者:  <br/> |[IMAPISession](imapisessioniunknown.md)对象  <br/> |
|实现者：  <br/> |MAPI 子系统  <br/> |
|调用者：  <br/> |MAPI 客户端  <br/> |
|接口标识符:  <br/> |IID_IMAPIClientShutdown  <br/> |
|指针类型:  <br/> |LPMAPICLIENTSHUTDOWN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) <br/> |查询 mapi 子系统以获取加载的 mapi 提供程序提供的快速关闭支持。  <br/> |
|[NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) <br/> |指示 MAPI 客户端的意向继续关闭。  <br/> |
|[DoFastShutdown](imapiclientshutdown-dofastshutdown.md) <br/> |指示 MAPI 客户端在立即退出客户端进程的意图。  <br/> |
   
## <a name="remarks"></a>说明

快速关闭的目的是允许 mapi 客户端和任何已加载的 mapi 提供程序与 mapi 客户端具有活动的 mapi 会话, 以保存 mapi 设置和数据。 这使 MAPI 客户端可以断开所有外部引用并退出, 而不会导致任何数据丢失。 需要执行快速关机的 MAPI 客户端必须使用**IMAPIClientShutdown**接口。 MAPI 客户端可以通过在任何[IMAPISession](imapisessioniunknown.md)对象上调用 IUnknown:: QueryInterface 方法来获取指向此接口的指针。 
  
MAPI 客户端总是通过调用**IMAPIClientShutdown:: QueryFastShutdown**方法启动快速关机。 mapi 子系统通过验证加载的 mapi 提供程序是否支持客户端快速关闭来响应 mapi 客户端的查询。 管理员可以使用 Windows 注册表设置来帮助确定 MAPI 客户端进行快速关机所需的提供程序支持级别。 有关详细信息, 请参阅[Fast Shutdown User Options](fast-shutdown-user-options.md)。
  
若要继续快速关闭, 客户端会调用**IMAPIClientShutdown:: NotifyProcessShutdown**方法, 以指示 MAPI 子系统关闭的意图。 然后, 客户端调用**IMAPIClientShutdown::D ofastshutdown**方法, 以指示客户端进程立即退出。 
  
有关快速关闭的详细信息, 请参阅[fast shutdown 概述](fast-shutdown-overview.md)。 有关如何成功执行快速关机的信息, 请参阅[fast shutdown 的最佳实践](best-practices-for-fast-shutdown.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)
  
[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

