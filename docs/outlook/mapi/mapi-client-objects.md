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
ms.openlocfilehash: 6e78c80d861a5a56584bfb03bfdf2895efde8730
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412406"
---
# <a name="mapi-client-objects"></a>MAPI 客户端对象
  
**适用于**：Outlook 2013 | Outlook 2016 
  
标准邮件客户端应用程序仅实现一个对象 (即通知接收器)。 通知接收器继承自[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口, 由 MAPI 和服务提供商用于事件通知。 某些客户端也会实施进度对象, 以支持显示进度对话框。 
  
支持自定义窗体的更复杂的客户端可实现另一个通知接收器对象和一些其他对象, 例如从[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口继承的邮件网站对象, 以及从继承自的视图上下文对象[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)接口。 附加的建议接收器对象继承自[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)接口。 
  
下表汇总了由标准邮件客户端和支持查看自定义窗体的客户端所实现的 MAPI 对象。
  
|**客户端对象**|**说明**|
|:-----|:-----|
|通知接收器  <br/> |提供用于在邮件存储区、通讯簿或会话中发生的事件的回调函数。  <br/> |
|消息网站  <br/> |处理对 form 对象的操作。  <br/> |
|Progress  <br/> |显示用于显示操作进度的对话框。  <br/> |
|查看建议接收器  <br/> |为表单中发生的事件提供回调函数。  <br/> |
|查看上下文  <br/> |支持用于打印和保存窗体以及在窗体之间导航的命令。  <br/> |
   
下图显示了这些不同客户端对象之间的关系、它们继承的接口以及使用这些对象的 MAPI 组件。 
  
![客户端对象和相应的接口](media/amapi_65.gif "客户端对象和相应的接口")
  
客户端使用的对象数多于它们实现的对象数。 所有客户端都使用 session 对象访问 MAPI 实现的各种服务提供程序对象和对象。 客户端可以通过会话、通讯簿或 MAPI 提供的 status 对象间接与服务提供程序交互, 也可以直接通过特定服务提供程序实现的各种对象进行交互。 若要与通讯簿提供商建立直接联系, 客户可以使用通讯簿容器、邮件用户和通讯组列表。 若要直接访问邮件存储区提供程序, 客户端需要使用邮件存储对象、文件夹、邮件和附件。 当服务提供商支持状态对象时, 客户端可以使用 status 对象监视服务提供程序的状态。
  
支持服务提供程序和邮件服务配置的客户端使用 MAPI 实现的三个对象: 邮件服务管理对象、配置文件管理对象和提供程序管理对象。 显示自定义窗体的客户端使用表单库提供程序或表单服务器实现的多个表单对象。
  
## <a name="see-also"></a>另请参阅

- [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) 
- [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)  
- [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

