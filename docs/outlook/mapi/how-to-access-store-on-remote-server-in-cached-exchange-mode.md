---
title: 缓存 Exchange 模式 Outlook 时访问远程服务器上的存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5c6df156-4015-2d0f-26b7-07055a3f7810
description: 上次修改时间： 2012 年 7 月 2 日
ms.openlocfilehash: 8f1afd31f017b73fa5270d8fbf4c2a1c8fa08880
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775102"
---
# <a name="access-a-store-on-the-remote-server-when-outlook-is-in-cached-exchange-mode"></a>缓存 Exchange 模式 Outlook 时访问远程服务器上的存储
 
**适用于**： Outlook 
  
本主题包含演示如何使用**MAPI_NO_CACHE**标志 Microsoft Office Outlook 时在缓存 Exchange 模式下打开文件夹或远程服务器上的消息存储上一条消息的 c + + 中的代码示例。 
  
缓存的 Exchange 模式允许 Outlook 使用用户的邮箱的本地副本，而 Outlook 保持联机连接到的远程副本的远程 Exchange 服务器上的用户的邮箱。 默认情况下，在缓存 Exchange 模式下运行 Outlook 时登录到同一个会话任何 MAPI 解决方案还会连接到缓存的邮件存储区。 对邮箱的本地副本进行访问的任何数据和所做的任何更改。
  
客户端或服务提供程序可以重写与本地消息存储库的连接并通过调用**[IMsgStore::OpenEntry](imsgstore-openentry.md)** 时为**MAPI_NO_CACHE** *ulFlags*参数中设置了位打开一条消息或远程存储上的文件夹。 
  
下面的代码示例演示如何使用*ulFlags*参数中的设置以打开上的远程邮件存储区的根文件夹**MAPI_NO_CACHE**标志调用**IMsgStore::OpenEntry** 。 
  
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

如果使用远程服务器上的**MDB_ONLINE**标志中打开的消息存储，您不必使用**MAPI_NO_CACHE**标志。 
  
## <a name="see-also"></a>另请参阅

- [关于 MAPI 添加件](about-mapi-additions.md)
- [当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

