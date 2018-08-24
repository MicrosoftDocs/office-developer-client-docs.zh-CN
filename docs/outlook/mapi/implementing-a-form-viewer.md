---
title: 实现表单查看器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a567185c-bd72-4307-928c-08cac5494c1a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ad0da261b3059ca83f2d547c25a508ec9337aa72
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584742"
---
# <a name="implementing-a-form-viewer"></a>实现表单查看器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单查看器包括三个对象： 消息网站视图告知接收器和了视图上下文。 每个对象，可以与窗体服务器和其表单进行交互。
  
消息网站是实现的对象[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口，并可帮助您与任务，如移动、 保存或删除邮件、 创建新的邮件，或启动新表单服务器表单服务器。 消息网站使用窗体来获取有关您的客户端与各种服务提供商的状态信息。 例如，窗体可用于您的消息网站获得到您当前的消息存储、 一条消息或文件夹的指针。 
  
有两种类型的**IMAPIMessageSite**接口中的方法： 
  
- 向表单对象提供的信息的方法。
    
- 操作的邮件的方法。
    
向表单对象提供的信息的方法是实现简单。 除[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)所有情况下，您应该已经可用所需的每种方法的信息。
  
操作的邮件的方法应就像它们具有通过常规用户界面触发。 例如，如果窗体对象调用[IMAPIMessageSite::NewMessage](imapimessagesite-newmessage.md)方法的行为就好像用户已选择撰写使用常规用户界面的新自定义消息。 这通常生成此行为的命令的**撰写**、**打开**、**答复**、**给所有收件人的答复**和**转发**。 
  
了视图上下文是实现的对象[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)接口，并为当前消息，使服务器能够轻松地切换到文件夹中的下一个或上一个邮件窗体服务器提供与上下文。 窗体使用了视图上下文的共享信息。 与视图上下文对象，窗体可以： 
  
- 注册您的客户端的通知。
    
- 激活下一个或上一个邮件文件夹中。
    
- 获取打印的信息。
    
- 获取客户端的状态。
    
- 获取一个流，可用于保存一条消息的文本版本。
    
类似于中的方法[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口， **IMAPIViewContext**中的方法将与用户操作和与视图上下文相关的客户端功能相关联。 例如，了视图上下文涉及与激活下一个或上一条消息、 排序的文件夹，内容和筛选文件夹中的内容。 
  
它并不重要的用户提供哪种机制要激活这些功能，请务必仅这些功能的语义映射到**IMAPIViewContext**接口中的方法。 
  
查看建议接收器是实现的对象[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)从影响您查看器和帮助表单和表单查看器协同工作的窗体服务器的接口和处理通知。 有关详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。 
  

