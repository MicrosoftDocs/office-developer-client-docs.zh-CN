---
title: 启动要读取邮件的表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 54a4b805-2ab7-4fb7-b0ea-4a33ead27451
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 675de7eeda534d8761887cdcb6d5c94a209ca18b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776141"
---
# <a name="launching-a-form-to-read-a-message"></a>启动要读取邮件的表单

  
  
**适用于**： Outlook 
  
客户端应用程序加载一条消息时，窗体服务器实施应产生预期方法调用其窗体服务器和窗体对象的以下序列：
  
1. 客户端应用程序调用[MAPIOpenFormMgr](mapiopenformmgr.md)函数打开的窗体管理器。 
    
2. 客户端应用程序调用[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)方法，它返回[IMAPIForm](imapiformiunknown.md)对象。 窗体管理器可能会立即发布，如果它将不用于进一步表单激活。 请注意**LoadForm**调用可能需要一些时间，因为窗体管理器可能必须安装该窗体服务器的可执行文件，然后再继续。 
    
3. （可选） 客户端应用程序可以准备[IMAPIViewContext](imapiviewcontextiunknown.md)控制操作可能会导致加载文件夹中的上一个或下一步邮件的 form 对象。 客户端应用程序可以使用[IMAPIForm::SetViewContext](imapiform-setviewcontext.md)方法以更改已设置的默认视图上下文**LoadForm**呼叫中。 
    
4. 客户端应用程序调用[IPersistMessage::Load](ipersistmessage-load.md)方法来将消息数据加载到 form 对象。 
    
5. 客户端应用程序调用[IMAPIForm::DoVerb](imapiform-doverb.md)调用传递可选[IMAPIViewContext](imapiviewcontextiunknown.md)接口指针打开动词。 
    
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

