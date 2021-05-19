---
title: 当远程服务器在缓存模式Outlook访问Exchange存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5c6df156-4015-2d0f-26b7-07055a3f7810
description: 上次修改时间：2012 年 7 月 2 日
ms.openlocfilehash: cfc20c1a9ca4510ffec86bf16666f1fc50822321
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433862"
---
# <a name="access-a-store-on-the-remote-server-when-outlook-is-in-cached-exchange-mode"></a>当远程服务器在缓存模式Outlook访问Exchange存储
 
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含一个 C++ 代码示例，该示例演示如何在 Microsoft Office Outlook 位于缓存模式时，使用 **MAPI_NO_CACHE** 标志打开远程服务器上邮件存储中的文件夹或Exchange。 
  
缓存Exchange模式Outlook使用用户邮箱的本地副本，而 Outlook 在远程 Exchange 服务器上维护与用户邮箱的远程副本的联机连接。 默认情况下Outlook在缓存Exchange模式下运行时，登录到同一会话的任何 MAPI 解决方案也会连接到缓存的邮件存储。 访问的任何数据和对邮箱的本地副本进行的任何更改。
  
客户端或服务提供商可以在调用 **[IMsgStore：：OpenEntry](imsgstore-openentry.md)** 时，在 *ulFlags* 参数中设置 **MAPI_NO_CACHE** 的位，覆盖与本地邮件存储的连接，并打开远程存储上的邮件或文件夹。 
  
下面的代码示例演示如何使用 *ulFlags* 参数中设置的 **MAPI_NO_CACHE** 标志调用 **IMsgStore：：OpenEntry** 以打开远程邮件存储上的根文件夹。 
  
```cpp
HRESULT HrOpenRootFolder ( 
    LPMDB lpMDB, 
    LPMESSAGE* lpRootFolder) 
{ 
    ULONG ulObjType = NULL; 
    HRESULT hRes = lpMDB-&gt;OpenEntry( 
        0,// size of entry ID       
        NULL,                                   // Pointer to entry ID 
        NULL,                                   // Use default interface (IMAPIFolder) 
        MAPI_BEST_ACCESS | MAPI_NO_CACHE,       // Flags 
        &amp;ulObjType,
// Output parameter indicates the type of object returned 
        (LPUNKNOWN *) lpRootFolder));           // Pointer to put the opened folder in 
    return hRes; 
 
}
```

如果在远程服务器上使用 MDB_ONLINE 标志打开邮件存储，则不需要使用 MAPI_NO_CACHE **标志。** 
  
## <a name="see-also"></a>另请参阅

- [关于 MAPI 添加件](about-mapi-additions.md) 
- [当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

