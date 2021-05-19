---
title: 启动窗体以读取邮件
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
# <a name="launching-a-form-to-read-a-message"></a>启动窗体以读取邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端应用程序加载消息时，表单服务器实施者应该希望其表单服务器和表单对象的方法调用顺序如下：
  
1. 客户端应用程序通过调用 [MAPIOpenFormMgr](mapiopenformmgr.md) 函数打开表单管理器。 
    
2. 客户端应用程序调用 [IMAPIFormMgr：：LoadForm](imapiformmgr-loadform.md) 方法，该方法返回具有 [IMAPIForm 的对象](imapiformiunknown.md)。 如果表单管理器不用于进一步的表单激活，则现在可能会发布该表单管理器。 请注意，调用 **LoadForm** 可能需要一些时间，因为表单管理器可能必须安装表单服务器的可执行文件才能继续。 
    
3. （可选）客户端应用程序可以准备 [IMAPIViewContext](imapiviewcontextiunknown.md) 来控制可能导致表单对象在文件夹中加载上一封邮件或下一封邮件的操作。 客户端应用程序可以使用 [IMAPIForm：：SetViewContext](imapiform-setviewcontext.md) 方法更改 **LoadForm** 调用中设置的默认视图上下文。 
    
4. 客户端应用程序调用 [IPersistMessage：：Load](ipersistmessage-load.md) 方法将邮件数据加载到表单对象中。 
    
5. 客户端应用程序调用 [IMAPIForm：:D oVerb](imapiform-doverb.md) 调用打开动词，并传递可选的 [IMAPIViewContext](imapiviewcontextiunknown.md) 接口指针。 
    
## <a name="see-also"></a>另请参阅



[表单服务器交互](form-server-interactions.md)

