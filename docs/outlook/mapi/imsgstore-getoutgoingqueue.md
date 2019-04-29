---
title: IMsgStoreGetOutgoingQueue
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.GetOutgoingQueue
api_type:
- COM
ms.assetid: 8316ff89-104d-43fd-902b-476fe567e23b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8ccb732dd587b2e5107290b2db7c48e85d0145d4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434149"
---
# <a name="imsgstoregetoutgoingqueue"></a><span data-ttu-id="8289a-103">IMsgStore::GetOutgoingQueue</span><span class="sxs-lookup"><span data-stu-id="8289a-103">IMsgStore::GetOutgoingQueue</span></span>

  
  
<span data-ttu-id="8289a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8289a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8289a-105">提供对传出队列表的访问权限, 该表包含有关邮件存储的传出队列中的所有邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="8289a-105">Provides access to the outgoing queue table, a table that has information about all of the messages in the message store's outgoing queue.</span></span> <span data-ttu-id="8289a-106">此方法仅由 MAPI 后台处理程序调用。</span><span class="sxs-lookup"><span data-stu-id="8289a-106">This method is called only by the MAPI spooler.</span></span>
  
```cpp
HRESULT GetOutgoingQueue(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="8289a-107">参数</span><span class="sxs-lookup"><span data-stu-id="8289a-107">Parameters</span></span>

 <span data-ttu-id="8289a-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8289a-108">_ulFlags_</span></span>
  
> <span data-ttu-id="8289a-109">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="8289a-109">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="8289a-110">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="8289a-110">_lppTable_</span></span>
  
> <span data-ttu-id="8289a-111">排除指向传出队列表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8289a-111">[out] A pointer to a pointer to the outgoing queue table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8289a-112">返回值</span><span class="sxs-lookup"><span data-stu-id="8289a-112">Return value</span></span>

<span data-ttu-id="8289a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8289a-113">S_OK</span></span> 
  
> <span data-ttu-id="8289a-114">已成功返回传出队列表。</span><span class="sxs-lookup"><span data-stu-id="8289a-114">The outgoing queue table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8289a-115">说明</span><span class="sxs-lookup"><span data-stu-id="8289a-115">Remarks</span></span>

<span data-ttu-id="8289a-116">**IMsgStore:: GetOutgoingQueue**方法为 MAPI 后台处理程序提供对显示邮件存储的传出邮件队列的表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8289a-116">The **IMsgStore::GetOutgoingQueue** method provides the MAPI spooler with access to the table that shows the message store's queue of outgoing messages.</span></span> <span data-ttu-id="8289a-117">通常情况下, 在调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法后, 邮件将放入传出队列表中。</span><span class="sxs-lookup"><span data-stu-id="8289a-117">Typically, messages are placed in the outgoing queue table after their [IMessage::SubmitMessage](imessage-submitmessage.md) method is called.</span></span> <span data-ttu-id="8289a-118">但是, 由于提交顺序影响了预处理和提交到传输提供程序的顺序, 因此一些已标记为发送的邮件可能不会立即显示在传出队列表中。</span><span class="sxs-lookup"><span data-stu-id="8289a-118">However, because the order of submission affects the order of preprocessing and submission to the transport provider, some messages that have been marked for sending might not appear in the outgoing queue table immediately.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="8289a-119">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="8289a-119">Notes to implementers</span></span>

<span data-ttu-id="8289a-120">有关必须作为传出队列表中的列包含的属性的列表, 请参阅[传出队列表](outgoing-queue-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="8289a-120">For a list of the properties that must be included as columns in your outgoing queue table, see [Outgoing Queue Tables](outgoing-queue-tables.md).</span></span> 
  
<span data-ttu-id="8289a-121">由于 mapi 后台处理程序旨在按提交时间的升序顺序从邮件存储区接受邮件, 因此允许 MAPI 后台处理程序对传出队列表进行排序以匹配此顺序, 或将其设置为默认的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="8289a-121">Because the MAPI spooler is designed to accept messages from a message store in ascending order of submission time, either allow the MAPI spooler to sort the outgoing queue table to match this order or establish it as the default sort order.</span></span>
  
<span data-ttu-id="8289a-122">您必须支持传出邮件队列表的通知, 以确保在队列的内容发生更改时通知 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="8289a-122">You must support notifications for the outgoing message queue table, ensuring that the MAPI spooler is notified when the contents of the queue change.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8289a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8289a-123">See also</span></span>



[<span data-ttu-id="8289a-124">IMessage::SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="8289a-124">IMessage::SubmitMessage</span></span>](imessage-submitmessage.md)
  
[<span data-ttu-id="8289a-125">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="8289a-125">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)

