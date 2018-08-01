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
# <a name="access-a-store-on-the-remote-server-when-outlook-is-in-cached-exchange-mode"></a><span data-ttu-id="e6b80-103">缓存 Exchange 模式 Outlook 时访问远程服务器上的存储</span><span class="sxs-lookup"><span data-stu-id="e6b80-103">Access a store on the remote server when Outlook is in Cached Exchange Mode</span></span>
 
<span data-ttu-id="e6b80-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e6b80-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e6b80-105">本主题包含演示如何使用**MAPI_NO_CACHE**标志 Microsoft Office Outlook 时在缓存 Exchange 模式下打开文件夹或远程服务器上的消息存储上一条消息的 c + + 中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="e6b80-105">This topic contains a code sample in C++ that shows how to use the **MAPI_NO_CACHE** flag to open a folder or a message on a message store on the remote server when Microsoft Office Outlook is in Cached Exchange Mode.</span></span> 
  
<span data-ttu-id="e6b80-106">缓存的 Exchange 模式允许 Outlook 使用用户的邮箱的本地副本，而 Outlook 保持联机连接到的远程副本的远程 Exchange 服务器上的用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e6b80-106">Cached Exchange Mode permits Outlook to use a local copy of a user's mailbox while Outlook maintains an online connection to a remote copy of the user's mailbox on the remote Exchange server.</span></span> <span data-ttu-id="e6b80-107">默认情况下，在缓存 Exchange 模式下运行 Outlook 时登录到同一个会话任何 MAPI 解决方案还会连接到缓存的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="e6b80-107">When Outlook is running in Cached Exchange Mode, by default, any MAPI solutions that log on to the same session are also connected to the cached message store.</span></span> <span data-ttu-id="e6b80-108">对邮箱的本地副本进行访问的任何数据和所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="e6b80-108">Any data that is accessed and any changes that are made are made against the local copy of the mailbox.</span></span>
  
<span data-ttu-id="e6b80-109">客户端或服务提供程序可以重写与本地消息存储库的连接并通过调用**[IMsgStore::OpenEntry](imsgstore-openentry.md)** 时为**MAPI_NO_CACHE** *ulFlags*参数中设置了位打开一条消息或远程存储上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e6b80-109">A client or service provider can override the connection to the local message store and open a message or a folder on the remote store by setting the bit for **MAPI_NO_CACHE** in the  *ulFlags*  parameter when calling **[IMsgStore::OpenEntry](imsgstore-openentry.md)**.</span></span> 
  
<span data-ttu-id="e6b80-110">下面的代码示例演示如何使用*ulFlags*参数中的设置以打开上的远程邮件存储区的根文件夹**MAPI_NO_CACHE**标志调用**IMsgStore::OpenEntry** 。</span><span class="sxs-lookup"><span data-stu-id="e6b80-110">The following code sample shows how to call **IMsgStore::OpenEntry** with the **MAPI_NO_CACHE** flag set in the  *ulFlags*  parameter to open the root folder on the remote message store.</span></span> 
  
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

<span data-ttu-id="e6b80-111">如果使用远程服务器上的**MDB_ONLINE**标志中打开的消息存储，您不必使用**MAPI_NO_CACHE**标志。</span><span class="sxs-lookup"><span data-stu-id="e6b80-111">If you opened the message store with the **MDB_ONLINE** flag on the remote server, you do not have to use the **MAPI_NO_CACHE** flag.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e6b80-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6b80-112">See also</span></span>

- [<span data-ttu-id="e6b80-113">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="e6b80-113">About MAPI Additions</span></span>](about-mapi-additions.md)
- [<span data-ttu-id="e6b80-114">当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="e6b80-114">Open a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="e6b80-115">在缓存 Exchange 模式下管理 OST 中的邮件（不调用同步）</span><span class="sxs-lookup"><span data-stu-id="e6b80-115">Manage a Message in an OST Without Invoking a Synchronization in Cached Exchange Mode</span></span>](how-to-manage-a-message-in-an-ost-without-invoking-a-synchronization.md)

