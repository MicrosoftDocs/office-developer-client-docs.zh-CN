---
title: 启动表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a439e75a-92b3-4830-9dfc-e723d046be7b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 87299ce4335492a744dd4ee965b4f8b85bcedc84
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564890"
---
# <a name="launching-a-form-server"></a>启动表单服务器

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
从持久存储加载表单时发生的交互非常系列 (即，从表单库) 显示一条消息，如下所示：
  
1. 消息客户端获取消息的邮件类、 邮件标志和邮件状态。 此步骤是可选的;如果在步骤 2 中未提供这些部分数据，窗体管理器将检索它们。
    
2. 消息客户端呼叫与目标邮件[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) 。 
    
3. 窗体管理器从相应的表单库加载的窗体服务器。 如果未安装了目标邮件的窗体服务器，则窗体管理器安装窗体的可执行文件，以及。
    
4. 窗体管理器来获取的窗体对象在窗体对象上调用[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) [IMAPIForm: IUnknown](imapiformiunknown.md)和[IPersistMessage: IUnknown](ipersistmessageiunknown.md)接口。 
    
5. 窗体管理器调用[IPersistMessage::Load](ipersistmessage-load.md)邮件与网站和邮件接口从查看器对象。 
    
6. Form 对象的邮件客户端[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)方法回拨。 
    
7. 窗体管理器从消息客户端调用视图上下文接口 form 对象的[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)方法。 
    
8. Form 对象的邮件客户端[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)方法回拨。 
    
9. Form 对象的邮件客户端[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)方法回拨。 
    
10. 消息客户端调用 form 对象的[IMAPIForm::Advise](imapiform-advise.md)方法与视图上下文接口从查看器对象和消息网站对象。 
    
11. 消息客户端调用 form 对象的[IMAPIForm::DoVerb](imapiform-doverb.md)方法。 
    
12. Form 对象创建其用户界面，如有必要，以及与用户交互。
    
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

