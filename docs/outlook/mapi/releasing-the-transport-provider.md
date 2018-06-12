---
title: 释放传输提供程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e0f37485-55c9-40f0-bc8c-48f7297f9f50
description: 上次修改时间： 2015 年 12 月 7 日
ms.openlocfilehash: b8032b22c78ae34bce7e9ccfb0f0a14cdde07290
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778608"
---
# <a name="releasing-the-transport-provider"></a>释放传输提供程序

 
  
**适用于**： Outlook 
  
当 MAPI 或 MAPI 后台处理程序完成使用传输登录对象：
  
1. MAPI 或 MAPI 后台处理程序调用传输提供程序的[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md)方法。 
    
2. 传输提供程序使状态对象无效通过调用[IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md)方法。 传输提供程序使失效的消息对象是否正在发送或接收在**TransportLogoff**呼叫的时间取决于已传递给**TransportLogoff**的标志。
    
3. 传输提供程序调用支持对象的[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法来从状态表中删除传输提供程序的行，从内部表中删除已设置[IMAPISupport 与任何唯一标识符 (Uid)::SetProviderUID](imapisupport-setprovideruid.md)方法。 它递减已知的登录对象上此提供商对象的计数。 如果计数为零时，MAPI 提供程序对象上调用[IXPProvider::Shutdown](ixpprovider-shutdown.md)方法和**版本**。 如果这是在此过程中使用此 DLL 的最后一个已知的提供程序对象，MAPI 会在以后对 DLL 调用**句**函数。 释放内存的 MAPI 支持对象，并支持对象**释放**方法返回。 
    
4. **TransportLogoff**方法，则返回 S_OK。 
    
5. MAPI 或 MAPI 后台处理程序传输提供程序的登录对象上调用**版本**。 释放对象的内存。 
    
6. MAPI 或 MAPI 后台处理程序提供程序 DLL 调用**句**。 
    
考虑到可靠性，应能够处理自身而无需事先其**TransportLogoff**或**关闭**方法调用的最终**发行**呼叫的登录和提供程序的对象。 如果在这种情况下调用**发行版**，则传输提供程序应将呼叫，视为**TransportLogoff**或**关闭**已被调用**发行**后跟零个参数。
  

