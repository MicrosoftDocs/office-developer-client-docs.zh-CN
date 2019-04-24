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
  
若要启用作为 Windows 服务编写的 mapi 客户端应用程序以使用符合 MAPI 的服务提供程序运行, mapi 有多种限制和要求。
  
MAPI 客户端具有以下限制:
  
- 无法允许用户界面。
    
- 他们只能通过紧密耦合的邮件存储和传输提供程序发送邮件。 此外, MAPI 客户端可以仅使用 Microsoft Exchange Server 或其他基于服务器的传输提供程序发送和接收邮件。 由于客户端应用程序和 MAPI 后台处理程序之间的标识和安全问题, 在服务中不支持大多数传输提供程序。 
    
所有 MAPI 客户端应用程序 (无论是作为 Windows 服务实现的) 都必须调用[MAPIInitialize](mapiinitialize.md)函数来初始化 mapi 库。 若要使用 OLE 库, 还需要调用[OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx)函数。 [MAPIInitialize](mapiinitialize.md)和[OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx)调用[CoInitialize](https://msdn.microsoft.com/library/ms678543%28VS.85%29.aspx)函数以初始化组件对象模型 (COM) 库。 作为服务的客户端必须在[MAPIINIT_0](mapiinit_0.md)结构的**ulFlags**成员中设置一个特殊标志 MAPI_NT_SERVICE, 该标志将传递给[MAPIInitialize](mapiinitialize.md) , 并在传递到[ulFlags](mapilogonex.md)的_MAPILogonEx_参数中进行设置。用于通知 MAPI 其特殊实现的函数。 
  
作为 Windows 服务编写并使用 mapi 客户端接口写入的 mapi 客户端具有其他要求。 必须在对[MAPILogonEx](mapilogonex.md)的调用中设置 MAPI_NO_MAIL 标志。 其他类型的客户端无需设置用于登录的标志, 因为它是由 MAPI 自动设置的。
  
若要在初始化线程中处理邮件, 作为服务实现的 MAPI 客户端将执行以下操作:
  
1. 在主线程阻塞时调用[MsgWaitForMultipleObjects](https://msdn.microsoft.com/library/ms684242%28VS.85%29.aspx)函数。 
    
2. 调用 Windows 函数的[GetMessage](https://msdn.microsoft.com/library/ms644936%28VS.85%29.aspx)、 [TranslateMessage](https://msdn.microsoft.com/library/ms644955%28VS.85%29.aspx)和[DispatchMessage](https://msdn.microsoft.com/library/ms644934%28VS.85%29.aspx)序列, 以处理当[MsgWaitForMultipleObjects](https://msdn.microsoft.com/library/ms684242%28VS.85%29.aspx)返回_nCount_参数值的总和和**WAIT_OBJECT_0**的值, 该值指示邮件在队列中。
    
## <a name="see-also"></a>另请参阅



[MAPIInitialize](mapiinitialize.md)
  
[MAPIINIT_0](mapiinit_0.md)
  
[MAPILogonEx](mapilogonex.md)


[操作环境问题](operating-environment-issues.md)

