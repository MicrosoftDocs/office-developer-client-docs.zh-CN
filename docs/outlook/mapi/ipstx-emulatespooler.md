---
title: IPSTXEmulateSpooler
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX.EmulateSpooler
api_type:
- COM
ms.assetid: aec72e51-1f75-b2c5-76ca-626cd21fbc7d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 024583926b5d0be638b33b1b60c5d4c5dc74d05b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315090"
---
# <a name="ipstxemulatespooler"></a><span data-ttu-id="0c627-103">IPSTX::EmulateSpooler</span><span class="sxs-lookup"><span data-stu-id="0c627-103">IPSTX::EmulateSpooler</span></span>

  
  
<span data-ttu-id="0c627-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c627-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c627-105">将本地存储设置为模拟 Outlook 协议管理器以将传出邮件后台处理到服务器。</span><span class="sxs-lookup"><span data-stu-id="0c627-105">Sets a local store to emulate the Outlook Protocol Manager to spool outgoing messages to a server.</span></span>
  
```cpp
HRESULT EmulateSpooler( 
    BOOL fEmulate 
);
```

 <span data-ttu-id="0c627-106">_fEmulate_</span><span class="sxs-lookup"><span data-stu-id="0c627-106">_fEmulate_</span></span>
  
>  <span data-ttu-id="0c627-107">实时如果本地存储应模拟后台处理程序, 则将此参数设置为 True;如果不是, 则将其设置为 False。</span><span class="sxs-lookup"><span data-stu-id="0c627-107">[in] Set this parameter to True if the local store should emulate the spooler; set it to False if not.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="0c627-108">注解</span><span class="sxs-lookup"><span data-stu-id="0c627-108">Remarks</span></span>

<span data-ttu-id="0c627-109">本地存储调用**IPSTX:: EmulateSpooler**作为 Outlook 协议管理器, 将传出队列中的邮件后台打印到后端服务器 (例如, MSN server 或 AOL server) 进行处理。</span><span class="sxs-lookup"><span data-stu-id="0c627-109">A local store calls **IPSTX::EmulateSpooler** to act as an Outlook Protocol Manager, spooling messages in the outgoing queue to the back-end server (for example, MSN server or AOL server) for processing.</span></span> <span data-ttu-id="0c627-110">在同步期间模拟后台打印程序时, 存储将调用以下两种方法:</span><span class="sxs-lookup"><span data-stu-id="0c627-110">Emulating a spooler during synchronization, the store then calls these two methods:</span></span> 
  
1. <span data-ttu-id="0c627-111">**[IMsgStore:: GetOutgoingQueue](imsgstore-getoutgoingqueue.md)** 获取存储中的邮件的传出队列。</span><span class="sxs-lookup"><span data-stu-id="0c627-111">**[IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)** to get the outgoing queue of messages in the store.</span></span> <span data-ttu-id="0c627-112">仅当存储模拟 Outlook 协议管理器时, 此方法才会成功。</span><span class="sxs-lookup"><span data-stu-id="0c627-112">This method succeeds only if the store is emulating the Outlook Protocol Manager.</span></span> 
    
2. <span data-ttu-id="0c627-113">**[IMsgStore:: SetLockState](imsgstore-setlockstate.md)** 在将邮件发送到服务器之前, 仅保护对传出队列中的邮件的唯一访问权限。</span><span class="sxs-lookup"><span data-stu-id="0c627-113">**[IMsgStore::SetLockState](imsgstore-setlockstate.md)** to secure sole access to a message in the outgoing queue just before sending it to the server.</span></span> <span data-ttu-id="0c627-114">仅当存储模拟 Outlook 协议管理器时, 此方法才会成功。</span><span class="sxs-lookup"><span data-stu-id="0c627-114">This method succeeds only if the store is emulating the Outlook Protocol Manager.</span></span> <span data-ttu-id="0c627-115">发送邮件后, store 再次调用此方法以释放对它的唯一访问权限。</span><span class="sxs-lookup"><span data-stu-id="0c627-115">After sending the message, the store calls this method again to release sole access to it.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0c627-116">由于 outlook 2002, outlook 协议管理器将替换 MAPI 后台处理程序, 并负责将传出邮件假脱机到后端服务器。</span><span class="sxs-lookup"><span data-stu-id="0c627-116">Since Outlook 2002, the Outlook Protocol Manager replaced the MAPI spooler and became responsible for spooling outgoing messages to back-end servers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0c627-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c627-117">See also</span></span>



[<span data-ttu-id="0c627-118">IPSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="0c627-118">IPSTX::GetLastError</span></span>](ipstx-getlasterror.md)
  
[<span data-ttu-id="0c627-119">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="0c627-119">IPSTX::GetSyncObject</span></span>](ipstx-getsyncobject.md)

