---
title: 从 Windows 服务调用 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: debf7ec3-e9f9-4912-b9a2-fc0953a56a01
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6465b2d24c3a38da40f2d1e6df79c2fa256b64b0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774611"
---
# <a name="calling-mapi-from-windows-services"></a>从 Windows 服务调用 MAPI

  
  
**适用于**： Outlook 
  
若要启用 MAPI 客户端应用程序作为 Windows 服务运行与 MAPI 兼容的服务提供商写入，MAPI 施加一些限制和要求。
  
MAPI 客户端具有以下限制：
  
- 他们无法允许的用户界面。
    
- 它们可以发送消息，只能通过紧密耦合的消息存储和传输提供程序。 此外，MAPI 客户端可以发送和接收邮件使用仅在 Microsoft Exchange Server 或其他基于服务器的传输提供程序。 客户端应用程序和 MAPI 后台处理程序之间的身份和安全问题，因为大多数传输提供程序不支持服务中。 
    
所有 MAPI 客户端应用程序，它们 Windows 服务，以实现是否必须都调用[MAPIInitialize](mapiinitialize.md)函数初始化 MAPI 库。 对[OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx)函数的调用也是使用 OLE 库所必需的。 [MAPIInitialize](mapiinitialize.md)和[OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx)打给[CoInitialize](http://msdn.microsoft.com/en-us/library/ms678543%28VS.85%29.aspx)函数初始化组件对象模型 (COM) 库。 在传递给[MAPIInitialize](mapiinitialize.md) [MAPIINIT_0](mapiinit_0.md)结构的**ulFlags**成员和_ulFlags_参数传递给[MAPILogonEx](mapilogonex.md)中，服务的客户端必须设置一个特殊的标志，MAPI_NT_SERVICE，若要向其特殊实现的 MAPI 的函数。 
  
MAPI 客户端的编写作为 Windows 服务并与 MAPI 客户端界面写入具有额外的要求。 必须对[MAPILogonEx](mapilogonex.md)的调用中设置 MAPI_NO_MAIL 标志。 其他类型的客户端不必设置进行登录的标志，因为它会自动设置的 MAPI。
  
若要处理初始化线程中的邮件，为服务实现 MAPI 客户端执行以下任务：
  
1. 调用[MsgWaitForMultipleObjects](http://msdn.microsoft.com/en-us/library/ms684242%28VS.85%29.aspx)函数时的主线程块。 
    
2. 调用 Windows 函数处理邮件时[MsgWaitForMultipleObjects](http://msdn.microsoft.com/en-us/library/ms684242%28VS.85%29.aspx)返回_nCount_参数的值的总和的[GetMessage](http://msdn.microsoft.com/en-us/library/ms644936%28VS.85%29.aspx)、 [TranslateMessage](http://msdn.microsoft.com/en-us/library/ms644955%28VS.85%29.aspx)和[DispatchMessage](http://msdn.microsoft.com/en-us/library/ms644934%28VS.85%29.aspx)序列和**WAIT_OBJECT_0**，表示一条消息队列中的值。
    
## <a name="see-also"></a>另请参阅



[MAPIInitialize](mapiinitialize.md)
  
[MAPIINIT_0](mapiinit_0.md)
  
[MAPILogonEx](mapilogonex.md)


[操作环境问题](operating-environment-issues.md)

