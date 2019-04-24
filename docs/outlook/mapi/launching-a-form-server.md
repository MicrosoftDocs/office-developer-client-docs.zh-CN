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
  
当从持久存储 (即表单库) 中加载表单以显示消息时发生的一系列交互, 如下所示:
  
1. 邮件客户端获取邮件的邮件类、邮件标记和邮件状态。 此步骤是可选的;如果在步骤2中未提供这些数据片段, 则表单管理器将检索它们。
    
2. 邮件客户端使用目标邮件调用[IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md) 。 
    
3. 表单管理器从相应的表单库加载表单服务器。 如果未安装目标邮件的表单服务器, 则表单管理器也会安装该表单的可执行文件。
    
4. 表单管理器调用[IUnknown::](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)用于获取表单对象的[IMAPIForm: iunknown](imapiformiunknown.md)和[IPersistMessage: iunknown](ipersistmessageiunknown.md)接口的表单对象上的 QueryInterface。 
    
5. 表单管理器调用[IPersistMessage::](ipersistmessage-load.md)使用消息站点和查看器对象的邮件接口进行加载。 
    
6. form 对象回调到邮件客户端的[IMAPIMessageSite:: GetSiteStatus](imapimessagesite-getsitestatus.md)方法。 
    
7. 表单管理器使用来自邮件客户端的视图上下文界面调用 form 对象的[IMAPIForm:: SetViewContext](imapiform-setviewcontext.md)方法。 
    
8. form 对象回调到邮件客户端的[IMAPIViewContext:: SetAdviseSink](imapiviewcontext-setadvisesink.md)方法。 
    
9. form 对象回调到邮件客户端的[IMAPIViewContext:: GetViewStatus](imapiviewcontext-getviewstatus.md)方法。 
    
10. 邮件客户端通过查看器对象和邮件网站对象的视图上下文界面调用 form 对象的[IMAPIForm:: Advise](imapiform-advise.md)方法。 
    
11. 邮件客户端调用 form 对象的[IMAPIForm::D overb](imapiform-doverb.md)方法。 
    
12. form 对象创建其用户界面 (如有必要), 并与用户进行交互。
    
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

