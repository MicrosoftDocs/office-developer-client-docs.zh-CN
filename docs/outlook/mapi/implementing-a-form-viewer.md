---
title: 实现表单查看器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a567185c-bd72-4307-928c-08cac5494c1a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bbd0792b0e3e3f274797fabd7f5d5eb49cfc73fd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435815"
---
# <a name="implementing-a-form-viewer"></a>实现表单查看器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单查看器包括三个对象: 邮件网站、视图通知接收器和视图上下文。 这些对象中的每一个都允许您与表单服务器及其表单进行交互。
  
邮件站点是一个对象, 它实现[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口, 并协助表单服务器处理包含移动、保存或删除邮件、创建新邮件或启动新表单服务器等任务的任务。 表单使用消息网站获取有关有关各种服务提供商的客户端状态信息。 例如, 窗体可以使用您的邮件网站获取指向当前邮件存储、邮件或文件夹的指针。 
  
**IMAPIMessageSite**接口中有两种类型的方法: 
  
- 向表单对象提供信息的方法。
    
- 操作邮件的方法。
    
向表单对象提供信息的方法是实现简单的。 在除[IMAPIMessageSite:: GetSiteStatus](imapimessagesite-getsitestatus.md)之外的所有情况下, 您应该已经有了每种方法所需的信息。
  
操作邮件的方法应类似于通过常规用户界面触发的方法。 例如, 如果 form 对象调用您的[IMAPIMessageSite:: NewMessage](imapimessagesite-newmessage.md)方法, 则行为与用户选择使用常规用户界面撰写新的自定义邮件的行为相同。 通常会生成此行为的命令包括**撰写**、**打开**、**答复**、**答复所有收件人**和**转发**。 
  
view context 是一个实现[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)接口的对象, 它提供具有当前邮件的上下文的表单服务器, 使服务器可以轻松地切换到文件夹中的下一封或上一封邮件。 表单使用视图上下文来共享信息。 使用 view context 对象, 窗体可以执行以下操作: 
  
- 向客户端注册以获取通知。
    
- 激活文件夹中的下一封邮件或上一封邮件。
    
- 获取打印信息。
    
- 获取客户端的状态。
    
- 获取可用于保存邮件文本版本的流。
    
与[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口中的方法类似, **IMAPIViewContext**中的方法与与视图上下文相关的用户操作和客户端功能相关联。 例如, 激活下一条或上一封邮件、对文件夹内容进行排序以及筛选该文件夹的内容, 都涉及视图上下文。 
  
为用户提供的用于激活这些功能的机制并不重要, 仅重要的是这些功能的语义能够很好地映射到**IMAPIViewContext**接口中的方法。 
  
视图建议接收器是一个实现[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)接口的对象, 并处理来自影响您的查看器和帮助表单和表单查看器协同工作的表单服务器的通知。 有关详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。 
  

