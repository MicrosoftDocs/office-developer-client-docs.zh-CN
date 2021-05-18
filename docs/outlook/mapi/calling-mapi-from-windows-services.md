---
title: 从 Windows 服务调用 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: debf7ec3-e9f9-4912-b9a2-fc0953a56a01
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a606b8bf82ce4c06c8e55f6e4df94220bc67501d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318101"
---
# <a name="calling-mapi-from-windows-services"></a>从 Windows 服务调用 MAPI

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为了使作为服务编写的 MAPI 客户端应用程序Windows兼容 MAPI 的服务提供商进行操作，MAPI 施加了一些限制和要求。
  
MAPI 客户端具有以下限制：
  
- 它们不允许用户界面。
    
- 他们只能通过紧密耦合的邮件存储和传输提供程序发送邮件。 此外，MAPI 客户端只能使用服务器或其他基于服务器的传输Microsoft Exchange Server发送和接收邮件。 由于客户端应用程序和 MAPI 后台处理程序之间的标识和安全问题，大多数传输提供程序在服务中不受支持。 
    
所有 MAPI 客户端应用程序（无论它们是作为Windows实现）都必须调用[MAPIInitialize](mapiinitialize.md)函数以初始化 MAPI 库。 调用 [OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx) 函数也是使用 OLE 库所必需的。 [MAPIInitialize](mapiinitialize.md)和[OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx)调用[CoInitialize](https://msdn.microsoft.com/library/ms678543%28VS.85%29.aspx)函数以初始化组件对象模型 (COM) 库。 作为服务的客户端必须在传递到 [MAPIInitialize](mapiinitialize.md)的 MAPIINIT_0 结构的 **ulFlags** 成员和传递给 [MAPILogonEx](mapilogonex.md)函数的 _ulFlags_ 参数中设置特殊标志 [MAPI_NT_SERVICE，](mapiinit_0.md)以通知 MAPI 其特殊实现。 
  
以 mapI 客户端Windows MAPI 客户端接口编写的 MAPI 客户端具有其他要求。 他们必须在调用 [MAPILogonEx MAPI_NO_MAIL设置 mapILogonEx 标记](mapilogonex.md)。 其他类型的客户端不需要设置用于登录的标志，因为它由 MAPI 自动设置。
  
若要处理初始化线程中的消息，作为服务实现的 MAPI 客户端将执行以下操作：
  
1. 当 [主线程阻止时，调用 MsgWaitForMultipleObjects](https://msdn.microsoft.com/library/ms684242%28VS.85%29.aspx) 函数。 
    
2. 当 [MsgWaitForMultipleObjects](https://msdn.microsoft.com/library/ms684242%28VS.85%29.aspx)返回 _nCount_ 参数和 **WAIT_OBJECT_0** 值的总和时，调用 Windows 函数的 [GetMessage、TranslateMessage](https://msdn.microsoft.com/library/ms644936%28VS.85%29.aspx)和 [DispatchMessage](https://msdn.microsoft.com/library/ms644934%28VS.85%29.aspx)序列来处理邮件，这表示邮件在队列中。 [](https://msdn.microsoft.com/library/ms644955%28VS.85%29.aspx)
    
## <a name="see-also"></a>另请参阅



[MAPIInitialize](mapiinitialize.md)
  
[MAPIINIT_0](mapiinit_0.md)
  
[MAPILogonEx](mapilogonex.md)


[操作环境问题](operating-environment-issues.md)

