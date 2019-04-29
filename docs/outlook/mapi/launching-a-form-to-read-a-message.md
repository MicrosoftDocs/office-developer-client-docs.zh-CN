---
title: 启动要读取邮件的表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 54a4b805-2ab7-4fb7-b0ea-4a33ead27451
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 439927dc78941f086c025d77c76236497d3f4a15
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425930"
---
# <a name="launching-a-form-to-read-a-message"></a>启动要读取邮件的表单

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单服务器实施者在客户端应用程序加载消息时, 应预计对其表单服务器和表单对象使用以下一系列方法调用:
  
1. 客户端应用程序使用调用[MAPIOpenFormMgr](mapiopenformmgr.md)函数打开表单管理器。 
    
2. 客户端应用程序调用[IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md)方法, 该方法返回具有[IMAPIForm](imapiformiunknown.md)的对象。 如果窗体管理器将不用于进一步的窗体激活, 现在就可以发布它。 请注意, 对**LoadForm**的调用可能需要一段时间, 因为在继续之前, 表单管理器可能必须安装表单服务器的可执行文件。 
    
3. (可选) 客户端应用程序可以准备[IMAPIViewContext](imapiviewcontextiunknown.md) , 以控制可能导致 form 对象加载该文件夹中的上一个或下一个邮件的操作。 客户端应用程序可以使用[IMAPIForm:: SetViewContext](imapiform-setviewcontext.md)方法更改在**LoadForm**调用中设置的默认视图上下文。 
    
4. 客户端应用程序调用[IPersistMessage:: load](ipersistmessage-load.md)方法将邮件数据加载到 form 对象中。 
    
5. 客户端应用程序调用[IMAPIForm::D overb](imapiform-doverb.md)调用 open 谓词, 以传递可选的[IMAPIViewContext](imapiviewcontextiunknown.md)接口指针。 
    
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

