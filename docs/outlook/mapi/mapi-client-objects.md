---
title: MAPI 客户端对象
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 11304a4c-d986-4ad9-a140-19a59825a8df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4242e466b0e784bb260d0525db0e253f1c1f37f3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568768"
---
# <a name="mapi-client-objects"></a>MAPI 客户端对象
  
**适用于**： Outlook 2013 |Outlook 2016 
  
标准邮件客户端应用程序实现只有一个对象 — 通知接收器。 建议从继承接收器[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口和使用 MAPI 服务提供商的事件通知。 某些客户端还实现进度对象，以支持显示进度对话框。 
  
更复杂的客户端支持自定义窗体实现另一个 advise 接收器对象和其他几个对象，如 message 网站对象继承[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)界面和视图上下文对象继承[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)接口。 其他 advise 接收器对象继承[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)接口。 
  
下表总结了实现标准消息客户端和支持的自定义窗体的查看的客户端的 MAPI 对象。
  
|**客户端对象**|**说明**|
|:-----|:-----|
|建议接收器  <br/> |提供消息存储、 通讯簿或会话中发生的事件的回调函数。  <br/> |
|消息网站  <br/> |处理表单对象的操作。  <br/> |
|Progress  <br/> |显示一个对话框，以显示操作的进度。  <br/> |
|查看建议接收器  <br/> |提供在窗体中发生的事件的回调函数。  <br/> |
|视图上下文  <br/> |支持命令用于打印和保存窗体和窗体之间导航。  <br/> |
   
下图显示了这些不同的客户端对象、 它们继承的接口和使用它们的 MAPI 组件之间的关系。 
  
![客户端对象和对应接口](media/amapi_65.gif "客户端对象和对应接口")
  
客户端使用更多的对象不是他们实现。 所有客户端使用的会话对象访问各种服务提供商对象和 MAPI 实现的对象。 客户端与服务提供商间接通过会话、 通讯簿中或提供 MAPI，状态对象或直接通过各种特定服务提供程序实现的对象进行交互。 若要使直接联系人通讯簿提供程序，客户端使用通讯簿容器消息用户和通讯组列表。 若要访问消息存储提供程序直接，客户端使用的消息存储对象、 文件夹、 邮件和附件。 服务提供商支持状态对象，当客户端可以使用状态对象来监控服务提供商的状态。
  
支持服务提供商和消息服务配置的客户端使用 MAPI 实现的三个对象： 消息服务管理对象、 配置文件管理对象和提供程序管理对象。 显示自定义窗体的客户端使用的窗体库提供程序或窗体服务器实现的多个窗体对象。
  
## <a name="see-also"></a>另请参阅

- [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) 
- [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)  
- [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

