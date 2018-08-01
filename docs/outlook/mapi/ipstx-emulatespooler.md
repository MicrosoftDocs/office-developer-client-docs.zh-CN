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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a8e353bbb4f276169ae26ba9d05821158bf55f00
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776063"
---
# <a name="ipstxemulatespooler"></a><span data-ttu-id="d7e92-103">IPSTX::EmulateSpooler</span><span class="sxs-lookup"><span data-stu-id="d7e92-103">IPSTX::EmulateSpooler</span></span>

  
  
<span data-ttu-id="d7e92-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d7e92-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d7e92-105">设置要模拟 Outlook 协议管理器后台打印到的服务器的传出邮件的本地存储。</span><span class="sxs-lookup"><span data-stu-id="d7e92-105">Sets a local store to emulate the Outlook Protocol Manager to spool outgoing messages to a server.</span></span>
  
```cpp
HRESULT EmulateSpooler( 
    BOOL fEmulate 
);
```

 <span data-ttu-id="d7e92-106">_fEmulate_</span><span class="sxs-lookup"><span data-stu-id="d7e92-106">_fEmulate_</span></span>
  
>  <span data-ttu-id="d7e92-107">[in]将此参数设置为 True，如果本地存储应模拟后台处理程序;将其设置为 false，则如果不需要。</span><span class="sxs-lookup"><span data-stu-id="d7e92-107">[in] Set this parameter to True if the local store should emulate the spooler; set it to False if not.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d7e92-108">说明</span><span class="sxs-lookup"><span data-stu-id="d7e92-108">Remarks</span></span>

<span data-ttu-id="d7e92-109">本地存储调用**IPSTX::EmulateSpooler**操作作为 Outlook 协议管理器中，为后端服务器 （例如，MSN 服务器或 AOL 服务器） 进行处理传出队列中的后台打印邮件。</span><span class="sxs-lookup"><span data-stu-id="d7e92-109">A local store calls **IPSTX::EmulateSpooler** to act as an Outlook Protocol Manager, spooling messages in the outgoing queue to the back-end server (for example, MSN server or AOL server) for processing.</span></span> <span data-ttu-id="d7e92-110">存储同步过程中模拟后台处理程序，然后调用这两种方法：</span><span class="sxs-lookup"><span data-stu-id="d7e92-110">Emulating a spooler during synchronization, the store then calls these two methods:</span></span> 
  
1. <span data-ttu-id="d7e92-111">**[IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)** ，以获取存储中的传出消息的队列。</span><span class="sxs-lookup"><span data-stu-id="d7e92-111">**[IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)** to get the outgoing queue of messages in the store.</span></span> <span data-ttu-id="d7e92-112">此方法成功，仅当存储在模拟 Outlook 协议管理器。</span><span class="sxs-lookup"><span data-stu-id="d7e92-112">This method succeeds only if the store is emulating the Outlook Protocol Manager.</span></span> 
    
2. <span data-ttu-id="d7e92-113">**[IMsgStore::SetLockState](imsgstore-setlockstate.md)** 保护之前将其发送到服务器的唯一的访问权传出队列中的邮件。</span><span class="sxs-lookup"><span data-stu-id="d7e92-113">**[IMsgStore::SetLockState](imsgstore-setlockstate.md)** to secure sole access to a message in the outgoing queue just before sending it to the server.</span></span> <span data-ttu-id="d7e92-114">此方法成功，仅当存储在模拟 Outlook 协议管理器。</span><span class="sxs-lookup"><span data-stu-id="d7e92-114">This method succeeds only if the store is emulating the Outlook Protocol Manager.</span></span> <span data-ttu-id="d7e92-115">发送消息后, 存储调用此方法再次来释放唯一访问它。</span><span class="sxs-lookup"><span data-stu-id="d7e92-115">After sending the message, the store calls this method again to release sole access to it.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="d7e92-116">Outlook 2002 相 Outlook 协议经理替换 MAPI 后台处理程序和变为负责对后端服务器进行后台打印传出邮件。</span><span class="sxs-lookup"><span data-stu-id="d7e92-116">Since Outlook 2002, the Outlook Protocol Manager replaced the MAPI spooler and became responsible for spooling outgoing messages to back-end servers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d7e92-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7e92-117">See also</span></span>



[<span data-ttu-id="d7e92-118">IPSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="d7e92-118">IPSTX::GetLastError</span></span>](ipstx-getlasterror.md)
  
[<span data-ttu-id="d7e92-119">IPSTX::GetSyncObject</span><span class="sxs-lookup"><span data-stu-id="d7e92-119">IPSTX::GetSyncObject</span></span>](ipstx-getsyncobject.md)

