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
  
标准邮件客户端应用程序仅实现一个对象 — 一个建议接收器。 建议接收器继承自 [IMAPIAdviseSink ： IUnknown](imapiadvisesinkiunknown.md) 接口，供 MAPI 和服务提供商用于事件通知。 某些客户端还实现进度对象以支持进度对话框的显示。 
  
支持自定义表单的更复杂的客户端实现另一个通知接收器对象和一些其他对象，例如从 [IMAPIMessageSite ： IUnknown](imapimessagesiteiunknown.md) 接口继承的消息网站对象和从 [IMAPIViewContext ： IUnknown](imapiviewcontextiunknown.md) 接口继承的视图上下文对象。 其他建议接收器对象继承自 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md) 接口。 
  
下表总结了标准邮件客户端和支持查看自定义表单的客户端实现的 MAPI 对象。
  
|**Client 对象**|**说明**|
|:-----|:-----|
|建议接收  <br/> |为在邮件存储、通讯簿或会话中发生的事件提供回调函数。  <br/> |
|邮件网站  <br/> |处理表单对象的操作。  <br/> |
|Progress  <br/> |显示一个对话框以显示操作的进度。  <br/> |
|查看建议接收器  <br/> |为窗体中发生的事件提供回调函数。  <br/> |
|视图上下文  <br/> |支持打印和保存窗体以及表单之间的导航命令。  <br/> |
   
下图显示了这些不同的客户端对象、这些对象从其继承的接口以及使用这些对象的 MAPI 组件之间的关系。 
  
![客户端对象和相应的接口](media/amapi_65.gif "客户端对象和相应的接口")
  
客户端使用的对象多于其实现的对象。 所有客户端都使用会话对象来访问 MAPI 实现的各种服务提供程序对象和对象。 客户端通过会话、通讯簿或 MAPI 提供的状态对象间接地与服务提供商进行交互，或者直接通过特定服务提供商实现的各种对象进行交互。 为了直接与通讯簿提供商联系，客户端使用通讯簿容器、邮件用户和通讯组列表。 若要直接访问邮件存储提供程序，客户端可使用邮件存储对象、文件夹、邮件和附件。 当服务提供商支持状态对象时，客户端可以使用 status 对象监视服务提供商的状态。
  
支持服务提供程序和邮件服务配置的客户端使用 MAPI 实现三个对象：邮件服务管理对象、配置文件管理对象和提供程序管理对象。 显示自定义表单的客户端使用表单库提供程序或表单服务器实现的几个表单对象。
  
## <a name="see-also"></a>另请参阅

- [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) 
- [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)  
- [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

