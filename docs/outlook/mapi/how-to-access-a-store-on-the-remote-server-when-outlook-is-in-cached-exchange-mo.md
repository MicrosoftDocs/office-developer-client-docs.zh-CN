---
title: 当 Outlook 处于缓存 Exchange 模式下时, 访问远程服务器上的存储区
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5c6df156-4015-2d0f-26b7-07055a3f7810
description: '上次修改时间: 2012 年7月2日'
ms.openlocfilehash: cfc20c1a9ca4510ffec86bf16666f1fc50822321
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433862"
---
# <a name="access-a-store-on-the-remote-server-when-outlook-is-in-cached-exchange-mode"></a>当 Outlook 处于缓存 Exchange 模式下时, 访问远程服务器上的存储区
 
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含 c + + 中的代码示例, 演示如何使用**MAPI_NO_CACHE**标志在 Microsoft Office Outlook 处于缓存 Exchange 模式下时, 在远程服务器上的邮件存储区中打开文件夹或邮件。 
  
缓存 Exchange 模式允许 outlook 在 outlook 维护与远程 Exchange 服务器上的用户邮箱远程副本的联机连接时使用该用户邮箱的本地副本。 当 Outlook 在缓存 Exchange 模式下运行时, 默认情况下, 登录到同一会话的任何 MAPI 解决方案也将连接到缓存的邮件存储区。 访问的任何数据和所做的任何更改都将针对邮箱的本地副本进行。
  
在调用**[IMsgStore:: OpenEntry](imsgstore-openentry.md)** 时, 客户端或服务提供程序可以通过在*ulFlags*参数中设置**MAPI_NO_CACHE**的位来覆盖本地邮件存储的连接并在远程存储中打开邮件或文件夹。 
  
下面的代码示例演示如何使用*ulFlags*参数中设置的**MAPI_NO_CACHE**标志调用**IMsgStore:: OpenEntry** , 以打开远程邮件存储区上的根文件夹。 
  
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

如果使用远程服务器上的**MDB_ONLINE**标志打开邮件存储区, 则无需使用**MAPI_NO_CACHE**标志。 
  
## <a name="see-also"></a>另请参阅

- [关于 MAPI 添加件](about-mapi-additions.md) 
- [当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

