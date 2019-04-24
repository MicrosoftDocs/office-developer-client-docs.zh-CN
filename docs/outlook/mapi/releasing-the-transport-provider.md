---
title: 释放传输提供程序
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e0f37485-55c9-40f0-bc8c-48f7297f9f50
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 41d953db8e00ff52cd09a27e2f7550f9f1879321
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328383"
---
# <a name="releasing-the-transport-provider"></a>释放传输提供程序

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当 mapi 或 mapi 后台处理程序使用传输登录对象完成时:
  
1. mapi 或 mapi 后台处理程序调用传输提供程序的[IXPLogon:: TransportLogoff](ixplogon-transportlogoff.md)方法。 
    
2. 传输提供程序通过调用[IMAPISupport:: MakeInvalid](imapisupport-makeinvalid.md)方法使 status 对象失效。 传输提供程序是否使在**TransportLogoff**调用时发送或接收的邮件对象失效, 具体取决于传递给**TransportLogoff**的标志。
    
3. 传输提供程序调用支持对象的[IUnknown:: Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法以从状态表中删除传输提供程序的行, 并从内部表中删除使用 IMAPISupport 设置的任何唯一标识符 (uid) [::SetProviderUID](imapisupport-setprovideruid.md)方法。 它会减少此提供程序对象上活动的已知登录对象的计数。 如果计数达到零, MAPI 将调用[IXPProvider:: Shutdown](ixpprovider-shutdown.md)方法, 并在 provider 对象上**释放**。 如果这是在此过程中使用此 dll 的最后一个已知提供程序对象, 则 MAPI 稍后会在 dll 上调用**FreeLibrary**函数。 已释放 MAPI 支持对象的内存, 并且支持对象**释放**方法将返回。 
    
4. **TransportLogoff**方法返回 S_OK。 
    
5. mapi 或 mapi 后台处理程序调用传输提供程序的登录对象的**版本**。 释放对象的内存。 
    
6. mapi 或 mapi 后台处理程序调用提供程序 DLL 上的**FreeLibrary** 。 
    
出于可靠性考虑, 登录和提供程序对象应该能够自行处理最终**发布**调用, 而无需先调用其**TransportLogoff**或**Shutdown**方法。 如果在这种情况下调用**Release** , 则传输提供程序应处理调用, 就好像使用零参数调用了**TransportLogoff**或**Shutdown** , 后跟**Release**。
  

