---
title: 当远程服务器在缓存模式Outlook访问Exchange存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5c6df156-4015-2d0f-26b7-07055a3f7810
description: 上次修改时间：2012 年 7 月 2 日
ms.openlocfilehash: 0d977507f6aff8aa5fbf437b4b718486a71f67dc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420729"
---
# <a name="access-a-store-on-the-remote-server-when-outlook-is-in-cached-exchange-mode"></a><span data-ttu-id="89f29-103">当远程服务器在缓存模式Outlook访问Exchange存储</span><span class="sxs-lookup"><span data-stu-id="89f29-103">Access a store on the remote server when Outlook is in Cached Exchange Mode</span></span>
 
<span data-ttu-id="89f29-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="89f29-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="89f29-105">本主题包含一个 C++ 代码示例，该示例演示如何在 Microsoft Office Outlook 位于缓存模式时，使用 **MAPI_NO_CACHE** 标志打开远程服务器上邮件存储中的文件夹或Exchange。</span><span class="sxs-lookup"><span data-stu-id="89f29-105">This topic contains a code sample in C++ that shows how to use the **MAPI_NO_CACHE** flag to open a folder or a message on a message store on the remote server when Microsoft Office Outlook is in Cached Exchange Mode.</span></span> 
  
<span data-ttu-id="89f29-106">缓存Exchange模式Outlook使用用户邮箱的本地副本，而 Outlook 在远程 Exchange 服务器上维护与用户邮箱的远程副本的联机连接。</span><span class="sxs-lookup"><span data-stu-id="89f29-106">Cached Exchange Mode permits Outlook to use a local copy of a user's mailbox while Outlook maintains an online connection to a remote copy of the user's mailbox on the remote Exchange server.</span></span> <span data-ttu-id="89f29-107">默认情况下Outlook在缓存Exchange模式下运行时，登录到同一会话的任何 MAPI 解决方案也会连接到缓存的邮件存储。</span><span class="sxs-lookup"><span data-stu-id="89f29-107">When Outlook is running in Cached Exchange Mode, by default, any MAPI solutions that log on to the same session are also connected to the cached message store.</span></span> <span data-ttu-id="89f29-108">访问的任何数据和对邮箱的本地副本进行的任何更改。</span><span class="sxs-lookup"><span data-stu-id="89f29-108">Any data that is accessed and any changes that are made are made against the local copy of the mailbox.</span></span>
  
<span data-ttu-id="89f29-109">客户端或服务提供商可以在调用 **[IMsgStore：：OpenEntry](imsgstore-openentry.md)** 时，在 *ulFlags* 参数中设置 **MAPI_NO_CACHE** 的位，覆盖与本地邮件存储的连接，并打开远程存储上的邮件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="89f29-109">A client or service provider can override the connection to the local message store and open a message or a folder on the remote store by setting the bit for **MAPI_NO_CACHE** in the  *ulFlags*  parameter when calling **[IMsgStore::OpenEntry](imsgstore-openentry.md)**.</span></span> 
  
<span data-ttu-id="89f29-110">下面的代码示例演示如何使用 *ulFlags* 参数中设置的 **MAPI_NO_CACHE** 标志调用 **IMsgStore：：OpenEntry** 以打开远程邮件存储上的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="89f29-110">The following code sample shows how to call **IMsgStore::OpenEntry** with the **MAPI_NO_CACHE** flag set in the  *ulFlags*  parameter to open the root folder on the remote message store.</span></span> 
  
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

<span data-ttu-id="89f29-111">如果在远程服务器上使用 MDB_ONLINE 标志打开邮件存储，则不需要使用 MAPI_NO_CACHE **标志。**</span><span class="sxs-lookup"><span data-stu-id="89f29-111">If you opened the message store with the **MDB_ONLINE** flag on the remote server, you do not have to use the **MAPI_NO_CACHE** flag.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="89f29-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89f29-112">See also</span></span>

- [<span data-ttu-id="89f29-113">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="89f29-113">About MAPI Additions</span></span>](about-mapi-additions.md)
- [<span data-ttu-id="89f29-114">当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="89f29-114">Open a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="89f29-115">在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）</span><span class="sxs-lookup"><span data-stu-id="89f29-115">Manage a Message in an OST Without Invoking a Synchronization in Cached Exchange Mode</span></span>](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

