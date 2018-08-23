---
title: 处理 MAPI 窗体
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c1589d49-2ebe-48ce-85c7-b70fb7c1bb67
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c6cdb07e1cbe68d90c6dcd9d5418f700ea5abc3d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589649"
---
# <a name="handling-mapi-forms"></a>处理 MAPI 窗体

**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 表单是查看器的特定类一条消息。 允许其用户使用属于邮件类的各种邮件的客户端必须编写处理各种 MAPI 形式。 若要处理多个窗体，客户端实现称为表单查看器，其中包含下面的三个对象的组件：
  
- 消息网站对象，它支持[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口。 
    
- 查看建议接收器，支持[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)接口。 
    
- 一个视图上下文对象，它支持[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)接口。 
    
每个对象使用一个称为实现处理其存储和处理视图的客户端生成的通知，每个窗体的窗体服务器组件。 一个其他组件，表单库提供程序，可实现窗体管理器。 窗体管理器管理表单库，其中存储窗体服务器可执行文件。 此管理包括加载的相应窗体服务器并处理服务器和客户端之间的初始通信。
  
下图显示的客户端和 MAPI 表单体系结构的其他部件之间的关系。
  
## <a name="mapi-form-architecture"></a>MAPI 表单体系结构
  
![MAPI 表单体系结构](media/forms01.gif "MAPI 表单体系结构")
  
如果您的客户端计划处理 MAPI 表单，您将使用的窗体管理器[IMAPIFormMgr: IUnknown](imapiformmgriunknown.md)接口执行基本的五个任务： 
  
- 打开或组成一条消息时，请启动相应的 MAPI 表单服务器。
    
- 文件夹的内容表中显示窗体服务器图标。
    
- 发送和接收窗体通知。 有关详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。
    
- 允许用户安装或删除表单库表单服务器。 有关详细信息，请参阅[维护表单库](maintaining-a-form-library.md)。
    
- 允许用户与特定的文件夹关联表单服务器。
    
若要访问窗体管理器，请一次在初始化过程中调用[MAPIOpenFormMgr](mapiopenformmgr.md)函数。 
  
## <a name="in-this-section"></a>本节内容

- [实现表单查看器](implementing-a-form-viewer.md)： 介绍如何通过使用视图来实现表单查看器告知接收器、 消息网站和了视图上下文。
    
- [实现标准窗体谓词](implementing-standard-form-verbs.md)： 介绍如何在 MAPI 窗体上实现用户菜单或按钮单击的动作。
    
- [发送和接收窗体通知](sending-and-receiving-form-notifications.md)： 介绍如何发送和接收窗体通知。
    
- [维护表单库](maintaining-a-form-library.md)： 介绍如何维护库包含有关表单的所有重要信息。
    
- [加载邮件到窗体](loading-a-message-into-a-form.md)： 介绍如何将一条消息加载到窗体。
    
- [撰写新邮件使用窗体](composing-a-new-message-by-using-a-form.md)： 介绍如何撰写邮件使用窗体。
    
- [显示窗体图标](displaying-form-icons.md)： 介绍用于显示与表单图标的步骤。
    
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)
- [开发 MAPI 表单服务器](developing-mapi-form-servers.md)

