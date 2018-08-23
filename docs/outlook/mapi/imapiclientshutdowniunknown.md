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
ms.openlocfilehash: 9fb372e504eaeb55861b09c4151956fb102c08f6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577147"
---
# <a name="imapiclientshutdown--iunknown"></a>IMAPIClientShutdown : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
允许执行快速关闭的客户端进程的 MAPI 客户端。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |[IMAPISession](imapisessioniunknown.md)对象  <br/> |
|通过实现：  <br/> |MAPI 子系统  <br/> |
|调用：  <br/> |MAPI 客户端  <br/> |
|接口标识符：  <br/> |IID_IMAPIClientShutdown  <br/> |
|指针类型：  <br/> |LPMAPICLIENTSHUTDOWN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[QueryFastShutdown](imapiclientshutdown-queryfastshutdown.md) <br/> |查询的 MAPI 子系统的快速关闭支持提供的加载 MAPI 提供程序。  <br/> |
|[NotifyProcessShutdown](imapiclientshutdown-notifyprocessshutdown.md) <br/> |表示的 MAPI 客户端的目的，继续执行关闭。  <br/> |
|[DoFastShutdown](imapiclientshutdown-dofastshutdown.md) <br/> |指示的 MAPI 客户端的目的立即退出该客户端进程。  <br/> |
   
## <a name="remarks"></a>注解

快速关闭的用途是允许 MAPI 客户端和与 MAPI 客户端有活动 MAPI 会话保存 MAPI 设置和数据任何加载的 MAPI 提供程序。 这样 MAPI 客户端断开所有外部引用并退出不会导致丢失数据。 需要执行快速关闭 MAPI 客户端必须使用**IMAPIClientShutdown**接口。 MAPI 客户端可以通过在任何[IMAPISession](imapisessioniunknown.md)对象上调用 IUnknown::QueryInterface 方法获取指向此接口的指针。 
  
MAPI 客户端总是初始化快速关闭通过调用**IMAPIClientShutdown::QueryFastShutdown**方法。 MAPI 子系统响应通过验证加载的 MAPI 提供程序是否支持客户端的快速关闭的 MAPI 客户端的查询。 管理员可以使用 Windows 注册表设置来帮助确定所需的 MAPI 客户端可以继续进行快速关闭提供程序支持的级别。 有关详细信息，请参阅[Fast 关闭用户选项](fast-shutdown-user-options.md)。
  
若要继续进行快速关闭，客户端调用**IMAPIClientShutdown::NotifyProcessShutdown**方法，以指示到 MAPI 子系统想要关闭。 然后，客户端调用**IMAPIClientShutdown::DoFastShutdown**方法来指示客户端进程正在立即退出。 
  
有关快速关闭的详细信息，请参阅[快速关闭 Overview](fast-shutdown-overview.md)。 有关如何成功执行快速关闭的信息，请参阅[快速关闭的最佳实践](best-practices-for-fast-shutdown.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)
  
[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

