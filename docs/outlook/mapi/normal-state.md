---
title: Normal 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b2acad7-5ef8-44db-911f-3bd2a7ca2778
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d5c92c243069e5b8b500df086169c8e5b961976d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570714"
---
# <a name="normal-state"></a><span data-ttu-id="70e1c-103">Normal 状态</span><span class="sxs-lookup"><span data-stu-id="70e1c-103">Normal State</span></span>

  
  
<span data-ttu-id="70e1c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70e1c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70e1c-105">正常状态是时间的其中 form 对象花费大量其启动操作，如保存更改，或关闭窗体的客户端应用程序等待。</span><span class="sxs-lookup"><span data-stu-id="70e1c-105">The Normal state is where the form object spends most of its time, waiting for client applications to initiate an action such as saving changes or closing the form.</span></span> <span data-ttu-id="70e1c-106">下表介绍允许的切换从正常状态。</span><span class="sxs-lookup"><span data-stu-id="70e1c-106">The following table describes allowed transitions from the Normal state.</span></span>
  
|<span data-ttu-id="70e1c-107">**IPersistMessage 方法**</span><span class="sxs-lookup"><span data-stu-id="70e1c-107">**IPersistMessage method**</span></span>|<span data-ttu-id="70e1c-108">**操作**</span><span class="sxs-lookup"><span data-stu-id="70e1c-108">**Action**</span></span>|<span data-ttu-id="70e1c-109">**新的状态**</span><span class="sxs-lookup"><span data-stu-id="70e1c-109">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="70e1c-110">[IPersistMessage::Save](ipersistmessage-save.md)(_pMessage = =_ NULL， _fSameAsLoad = =_ ，则返回 TRUE)</span><span class="sxs-lookup"><span data-stu-id="70e1c-110">[IPersistMessage::Save](ipersistmessage-save.md)(_pMessage ==_ NULL,  _fSameAsLoad ==_ TRUE)</span></span>  <br/> <span data-ttu-id="70e1c-111">-或者-</span><span class="sxs-lookup"><span data-stu-id="70e1c-111">-or-</span></span>  <br/> <span data-ttu-id="70e1c-112">**IPersistMessage::Save**(_pMessage ！ =_ NULL， _fSameAsLoad = =_ FALSE)</span><span class="sxs-lookup"><span data-stu-id="70e1c-112">**IPersistMessage::Save**(_pMessage !=_ NULL,  _fSameAsLoad ==_ FALSE)</span></span>  <br/> |<span data-ttu-id="70e1c-113">以递归方式保存已修改的任何嵌入的 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="70e1c-113">Recursively save any embedded OLE objects that have been modified.</span></span> <span data-ttu-id="70e1c-114">将邮件数据保存回 message 对象。</span><span class="sxs-lookup"><span data-stu-id="70e1c-114">Save message data back to the message object.</span></span> <span data-ttu-id="70e1c-115">存储在[NoScribble](noscribble-state.md)状态以供以后使用_fSameAsLoad_标志。</span><span class="sxs-lookup"><span data-stu-id="70e1c-115">Store the  _fSameAsLoad_ flag for later use in the [NoScribble](noscribble-state.md) state.</span></span>  <br/> |<span data-ttu-id="70e1c-116">NoScribble</span><span class="sxs-lookup"><span data-stu-id="70e1c-116">NoScribble</span></span>  <br/> |
|<span data-ttu-id="70e1c-117">**IPersistMessage::Save**(_pMessage ！ =_ NULL， _fSameAsLoad = =_ ，则返回 TRUE)</span><span class="sxs-lookup"><span data-stu-id="70e1c-117">**IPersistMessage::Save**(_pMessage !=_ NULL,  _fSameAsLoad ==_ TRUE)</span></span>  <br/> |<span data-ttu-id="70e1c-118">这是相同的以前的情况下，只不过此**保存**呼叫中内存不足的情况下使用和不得缺少内存导致失败。</span><span class="sxs-lookup"><span data-stu-id="70e1c-118">This is the same as the previous case, except that this **Save** call is used in low-memory situations and must not fail for lack of memory.</span></span>  <br/> |<span data-ttu-id="70e1c-119">NoScribble</span><span class="sxs-lookup"><span data-stu-id="70e1c-119">NoScribble</span></span>  <br/> |
|[<span data-ttu-id="70e1c-120">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="70e1c-120">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md) <br/> |<span data-ttu-id="70e1c-121">以递归方式调用嵌入邮件上的**HandsOffMessage**方法或嵌入的 OLE 对象的 OLE [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="70e1c-121">Recursively invoke the **HandsOffMessage** method on embedded messages or the OLE [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx) method on embedded OLE objects.</span></span> <span data-ttu-id="70e1c-122">发布的消息对象和任何嵌入式的邮件或对象。</span><span class="sxs-lookup"><span data-stu-id="70e1c-122">Release the message object and any embedded messages or objects.</span></span>  <br/> |[<span data-ttu-id="70e1c-123">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="70e1c-123">HandsOffFromNormal</span></span>](handsofffromnormal-state.md) <br/> |
|<span data-ttu-id="70e1c-124">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)、 [IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md)</span><span class="sxs-lookup"><span data-stu-id="70e1c-124">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md), [IPersistMessage::InitNew](ipersistmessage-initnew.md) or [IPersistMessage::Load](ipersistmessage-load.md)</span></span> <br/> |<span data-ttu-id="70e1c-125">设置为上一个错误，并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="70e1c-125">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="70e1c-126">常规</span><span class="sxs-lookup"><span data-stu-id="70e1c-126">Normal</span></span>  <br/> |
|[<span data-ttu-id="70e1c-127">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="70e1c-127">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="70e1c-128">返回的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="70e1c-128">Return the last error.</span></span>  <br/> |<span data-ttu-id="70e1c-129">常规</span><span class="sxs-lookup"><span data-stu-id="70e1c-129">Normal</span></span>  <br/> |
|<span data-ttu-id="70e1c-130">其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法</span><span class="sxs-lookup"><span data-stu-id="70e1c-130">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="70e1c-131">实现的文档中所述[IPersistMessage: IUnknown](ipersistmessageiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="70e1c-131">Implement as described in the documentation for the [IPersistMessage : IUnknown](ipersistmessageiunknown.md) interface.</span></span>  <br/> |<span data-ttu-id="70e1c-132">常规</span><span class="sxs-lookup"><span data-stu-id="70e1c-132">Normal</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="70e1c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70e1c-133">See also</span></span>



[<span data-ttu-id="70e1c-134">表单状态</span><span class="sxs-lookup"><span data-stu-id="70e1c-134">Form States</span></span>](form-states.md)

