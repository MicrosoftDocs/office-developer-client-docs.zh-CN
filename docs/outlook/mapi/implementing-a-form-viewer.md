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
  
表单查看器包括三个对象：消息网站、视图建议接收器和视图上下文。 其中每个对象都允许您与表单服务器及其表单进行交互。
  
消息网站是一个实现 [IMAPIMessageSite ： IUnknown](imapimessagesiteiunknown.md) 接口的对象，可帮助表单服务器执行移动、保存或删除消息、创建新消息或启动新表单服务器等任务。 邮件网站由表单用于获取有关各种服务提供商的客户端状态的信息。 例如，窗体可以使用邮件网站获取指向当前邮件存储、邮件或文件夹的指针。 
  
**IMAPIMessageSite** 接口有两种类型的方法： 
  
- 向表单对象提供信息的方法。
    
- 操作邮件的方法。
    
向表单对象提供信息的方法很容易实现。 在除 [IMAPIMessageSite：：GetSiteStatus](imapimessagesite-getsitestatus.md)之外的所有情况下，都应已提供每个方法所需的信息。
  
操作消息的方法应像通过常规用户界面触发一样操作。 例如，如果表单对象调用 [IMAPIMessageSite：：NewMessage](imapimessagesite-newmessage.md) 方法，则其行为就像用户已选择使用常规用户界面撰写新的自定义邮件一样。 通常生成此行为的命令有Compose、Open、Reply、Reply **to All Recipients** 和 **Forward**。   
  
视图上下文是一个实现 [IMAPIViewContext ： IUnknown](imapiviewcontextiunknown.md) 接口的对象，可为表单服务器提供当前消息的上下文，从而使服务器可以轻松地切换到文件夹中的下一封邮件或上一封邮件。 表单使用视图上下文来共享信息。 对于视图上下文对象，表单可以： 
  
- 在客户端中注册以接收通知。
    
- 激活文件夹中的下一封邮件或上一封邮件。
    
- 获取打印信息。
    
- 获取客户端的状态。
    
- 获取可用于保存邮件的文本版本的流。
    
与 [IMAPIMessageSite ： IUnknown](imapimessagesiteiunknown.md) 接口中的方法类似 **，IMAPIViewContext** 中的方法与与视图上下文相关的用户操作和客户端功能关联。 例如，视图上下文涉及激活下一封邮件或上一封邮件、对文件夹内容进行排序以及筛选文件夹的内容。 
  
为用户提供哪些机制来激活这些功能并非很重要，这些功能的语义必须很好地映射到 **IMAPIViewContext** 接口中的方法。 
  
视图通知接收器是一个对象，它实现 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md) 接口，并处理来自影响查看器的表单服务器的通知，并帮助表单和表单查看器协同工作。 有关详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。 
  

