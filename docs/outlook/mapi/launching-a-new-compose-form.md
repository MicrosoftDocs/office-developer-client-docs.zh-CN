---
title: 启动新的撰写表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ffceaa03-76f2-42e0-b28d-226f1f9cc889
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 29d53ba1242014a501a01d161c19dade164f393a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270054"
---
# <a name="launching-a-new-compose-form"></a>启动新的撰写表单

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单服务器实施者在客户端应用程序打开要撰写的新邮件时, 应预计对其表单服务器和表单对象使用以下一系列方法调用:
  
1. 客户端应用程序调用[IMAPIFormMgr:: ResolveMessageClass](imapiformmgr-resolvemessageclass.md)方法, 以获取有关窗体服务器的邮件类的类信息。 
    
2. 客户端应用程序调用[IMAPIFormMgr:: CreateForm](imapiformmgr-createform.md)获取新的表单对象。 
    
3. MAPI 表单管理器会加载表单服务器 (如果它尚不在内存中), 并从表单服务器中获取[IMAPIForm](imapiformiunknown.md)接口。 
    
4. 客户端应用程序采用生成的**IMAPIForm**接口, 并调用[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法来获取对象的[IPersistMessage](ipersistmessageiunknown.md)接口。 
    
5. 客户端应用程序调用[IPersistMessage:: InitNew](ipersistmessage-initnew.md)方法将 form 对象与[IMessage](imessageimapiprop.md)、view context 和 advise sink 对象相关联。
    
6. 客户端应用程序调用[IMAPIForm::D overb](imapiform-doverb.md)方法调用 open 谓词。 
    
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

