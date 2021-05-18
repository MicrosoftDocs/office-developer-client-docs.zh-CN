---
title: 启动表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a439e75a-92b3-4830-9dfc-e723d046be7b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: dec8706ba00356660ec82c25e0213ef3e638691d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270047"
---
# <a name="launching-a-form-server"></a>启动表单服务器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从持久性存储库加载表单时发生的一系列 (，即从表单库) 显示消息的交互如下所示：
  
1. 邮件客户端获取邮件的邮件类、邮件标志和邮件状态。 此步骤是可选的;如果步骤 2 中未提供这些部分数据，则表单管理器将检索它们。
    
2. 消息客户端使用目标消息[调用 IMAPIFormMgr：：LoadForm。](imapiformmgr-loadform.md) 
    
3. 表单管理器从相应的表单库加载表单服务器。 如果未安装目标邮件的表单服务器，则表单管理器也安装表单的可执行文件。
    
4. 表单管理器对表单对象调用 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) 以获取表单对象的 [IMAPIForm ： IUnknown](imapiformiunknown.md) 和 [IPersistMessage ： IUnknown](ipersistmessageiunknown.md) 接口。 
    
5. 表单管理器使用查看器对象的消息网站和消息界面调用[IPersistMessage：：Load。](ipersistmessage-load.md) 
    
6. 表单对象将调用回消息客户端的 [IMAPIMessageSite：：GetSiteStatus](imapimessagesite-getsitestatus.md) 方法。 
    
7. 表单管理器使用消息客户端中的视图上下文接口调用表单对象的 [IMAPIForm：：SetViewContext](imapiform-setviewcontext.md) 方法。 
    
8. 表单对象将调用回消息客户端的 [IMAPIViewContext：：SetAdviseSink](imapiviewcontext-setadvisesink.md) 方法。 
    
9. 表单对象将调用回消息客户端的 [IMAPIViewContext：：GetViewStatus](imapiviewcontext-getviewstatus.md) 方法。 
    
10. 消息客户端使用查看器对象和消息网站对象的视图上下文接口调用表单对象的 [IMAPIForm：：Advise](imapiform-advise.md) 方法。 
    
11. 消息客户端调用表单对象的 [IMAPIForm：:D oVerb](imapiform-doverb.md) 方法。 
    
12. 窗体对象将创建其用户界面（如有必要）并与用户交互。
    
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

