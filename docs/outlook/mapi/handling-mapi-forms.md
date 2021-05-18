---
title: 处理 MAPI 表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c1589d49-2ebe-48ce-85c7-b70fb7c1bb67
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 91347f0c34b8d7b76e4e456397a1faa061f3b2c6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423053"
---
# <a name="handling-mapi-forms"></a>处理 MAPI 表单

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 窗体是特定类消息的查看器。 必须编写允许用户处理属于各种邮件类的邮件的客户端，以处理各种 MAPI 窗体。 为了处理多个表单，客户端实现一个称为表单查看器的组件，其中包含以下三个对象：
  
- 支持 [IMAPIMessageSite ： IUnknown](imapimessagesiteiunknown.md) 接口的消息站点对象。 
    
- 视图建议接收器，支持 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md) 接口。 
    
- 支持 [IMAPIViewContext ： IUnknown](imapiviewcontextiunknown.md) 接口的视图上下文对象。 
    
每个对象都由一个称为表单服务器的组件使用，该组件实现每个表单，处理其存储和由处理视图的客户端生成的通知。 另一个组件是表单库提供程序，它实现表单管理器。 表单管理器管理表单库，该库存储表单服务器可执行文件。 此管理包括加载相应的表单服务器和处理服务器和客户端之间的初始通信。
  
下图显示了客户端与 MAPI 表单体系结构的其他部分之间的关系。
  
## <a name="mapi-form-architecture"></a>MAPI 表单体系结构
  
![MAPI 表单体系结构](media/forms01.gif "MAPI 表单体系结构")
  
如果客户端计划处理 MAPI 表单，您将使用表单管理器的 [IMAPIFormMgr ： IUnknown](imapiformmgriunknown.md) 接口执行五个基本任务： 
  
- 打开或撰写邮件时启动相应的 MAPI 表单服务器。
    
- 在文件夹的内容表中显示表单服务器的图标。
    
- 发送和接收表单通知。 有关详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。
    
- 允许用户从表单库安装或删除表单服务器。 有关详细信息，请参阅 [维护表单库](maintaining-a-form-library.md)。
    
- 允许用户将表单服务器与特定文件夹关联。
    
若要访问表单管理器，在初始化期间调用 [MAPIOpenFormMgr](mapiopenformmgr.md) 函数一次。 
  
## <a name="in-this-section"></a>本节内容

- [实现表单查看器](implementing-a-form-viewer.md)：介绍如何通过使用视图建议接收器、消息网站和视图上下文来实现表单查看器。
    
- [Implementing Standard Form Verbs](implementing-standard-form-verbs.md)： Describes how to implement the verbs for user menu or button clicks on MAPI forms.
    
- [发送和接收表单通知](sending-and-receiving-form-notifications.md)：介绍如何发送和接收表单通知。
    
- [Maintaining a Form Library](maintaining-a-form-library.md)： Describes how to maintain a library that holds all the important information about a form.
    
- [Loading a Message Into a Form](loading-a-message-into-a-form.md)： Describes how to load a message into a form.
    
- [使用窗体撰写新邮件](composing-a-new-message-by-using-a-form.md)：介绍如何使用窗体撰写邮件。
    
- [显示表单图标](displaying-form-icons.md)：介绍显示窗体图标的步骤。
    
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)
- [开发 MAPI 表单服务器](developing-mapi-form-servers.md)

