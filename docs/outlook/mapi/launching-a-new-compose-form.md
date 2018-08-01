---
title: 启动新的撰写表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ffceaa03-76f2-42e0-b28d-226f1f9cc889
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8d1b94c70e4de6310d2e84cf002c4e3199fced2b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776154"
---
# <a name="launching-a-new-compose-form"></a>启动新的撰写表单

  
  
**适用于**： Outlook 
  
窗体服务器实施应产生预期方法调用与其窗体服务器的以下序列和表单对象时客户端应用程序打开一个新邮件以撰写：
  
1. 客户端应用程序调用[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法来获取有关窗体服务器的邮件类的类信息。 
    
2. 客户端应用程序调用[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)以获取新的窗体对象。 
    
3. MAPI 窗体管理器加载窗体服务器中，如果它不是内存，并从窗体服务器获取[IMAPIForm](imapiformiunknown.md)接口。 
    
4. 客户端应用程序所需的结果**IMAPIForm**接口，并调用[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法获取对象的[IPersistMessage](ipersistmessageiunknown.md)接口。 
    
5. 客户端应用程序调用[IPersistMessage::InitNew](ipersistmessage-initnew.md)方法[IMessage](imessageimapiprop.md)，视图上下文相关联的 form 对象并告知接收器对象。
    
6. 客户端应用程序调用[IMAPIForm::DoVerb](imapiform-doverb.md)方法来调用打开谓词。 
    
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

