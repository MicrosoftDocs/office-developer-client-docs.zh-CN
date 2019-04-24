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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299447"
---
# <a name="handling-mapi-forms"></a>处理 MAPI 表单

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 表单是特定类的邮件的查看器。 允许用户使用属于各种邮件类别的邮件的客户端必须编写为处理各种 MAPI 表单。 若要处理多个窗体, 客户端将实现一个称为表单查看器的组件, 其中包含以下三个对象:
  
- 一个支持[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口的邮件网站对象。 
    
- 一个支持[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)接口的视图建议接收器。 
    
- 一个支持[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)接口的 view context 对象。 
    
这些对象中的每一个都由称为表单服务器的组件用于实现每个表单、处理其存储以及处理视图的客户端生成的通知。 一个其他组件 (即表单库提供程序) 实现表单管理器。 表单管理器管理存储表单服务器可执行文件的表单库。 此管理包括加载相应的表单服务器和处理服务器与客户端之间的初始通信。
  
下图显示了客户端与 MAPI 表单体系结构的其他部分之间的关系。
  
## <a name="mapi-form-architecture"></a>MAPI 表单体系结构
  
![MAPI 表单体系结构](media/forms01.gif "MAPI 表单体系结构")
  
如果您的客户端计划处理 MAPI 表单, 您将使用表单管理器的[IMAPIFormMgr: IUnknown](imapiformmgriunknown.md)接口执行五个基本任务: 
  
- 打开或撰写邮件时, 启动相应的 MAPI 表单服务器。
    
- 在文件夹的内容表中显示窗体服务器的图标。
    
- 发送和接收表单通知。 有关详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。
    
- 允许用户在表单库中安装或删除表单服务器。 有关详细信息, 请参阅[维护表单库](maintaining-a-form-library.md)。
    
- 允许用户将表单服务器与特定文件夹相关联。
    
若要访问表单管理器, 请在初始化期间调用一次[MAPIOpenFormMgr](mapiopenformmgr.md)函数。 
  
## <a name="in-this-section"></a>本节内容

- [实现表单查看器](implementing-a-form-viewer.md): 介绍如何通过使用视图建议接收器、消息网站和视图上下文来实现表单查看器。
    
- [实现标准窗体谓词](implementing-standard-form-verbs.md): 介绍如何在 MAPI 表单上实现用户菜单或按钮单击的谓词。
    
- [发送和接收表单通知](sending-and-receiving-form-notifications.md): 介绍如何发送和接收表单通知。
    
- [维护表单库](maintaining-a-form-library.md): 介绍如何维护包含有关表单的所有重要信息的库。
    
- 将[邮件加载到表单](loading-a-message-into-a-form.md)中: 介绍如何将邮件加载到表单中。
    
- [使用表单撰写新邮件](composing-a-new-message-by-using-a-form.md): 介绍如何使用窗体撰写邮件。
    
- [显示窗体图标](displaying-form-icons.md): 介绍了用于在窗体中显示图标的步骤。
    
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)
- [开发 MAPI 表单服务器](developing-mapi-form-servers.md)

