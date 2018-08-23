---
title: HandsOffFromNormal 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1afe6a2e-a5e6-4844-9f82-908894fc6759
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 92c604c621e2837b76e9e49fd182524ad17fbcac
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588340"
---
# <a name="handsofffromnormal-state"></a><span data-ttu-id="f4b3f-103">HandsOffFromNormal 状态</span><span class="sxs-lookup"><span data-stu-id="f4b3f-103">HandsOffFromNormal State</span></span>

  
  
<span data-ttu-id="f4b3f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f4b3f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f4b3f-105">非常类似于[HandsOffAfterSave](handsoffaftersave-state.md)状态 HandsOffFromNormal 状态。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-105">The HandsOffFromNormal state is very similar to the [HandsOffAfterSave](handsoffaftersave-state.md) state.</span></span> <span data-ttu-id="f4b3f-106">它是将窗体的内容保存到永久存储过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-106">It is part of the process of saving the contents of a form to permanent storage.</span></span> <span data-ttu-id="f4b3f-107">在此状态下，窗体对象应避免更改消息的属性的值的内存中副本因为可能没有其他机会保存这些更改。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-107">When in this state, the form object should refrain from making changes to the in-memory copies of values of the message's properties, because there may not be another opportunity to save those changes.</span></span> <span data-ttu-id="f4b3f-108">下表介绍允许的 HandsOffFromNormal 状态转换。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-108">The following table describes allowed transitions from the HandsOffFromNormal state.</span></span> 
  
|<span data-ttu-id="f4b3f-109">IPersistMessage * * 方法 * *</span><span class="sxs-lookup"><span data-stu-id="f4b3f-109">****IPersistMessage** method**</span></span>|<span data-ttu-id="f4b3f-110">**操作**</span><span class="sxs-lookup"><span data-stu-id="f4b3f-110">**Action**</span></span>|<span data-ttu-id="f4b3f-111">**新的状态**</span><span class="sxs-lookup"><span data-stu-id="f4b3f-111">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4b3f-112">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage ！ =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="f4b3f-112">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage !=_ NULL)</span></span>  <br/> |<span data-ttu-id="f4b3f-113">将 message 对象的消息替换_pMessage_，这是替换为[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)到以前的呼叫被吊销的邮件。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-113">Replace the message object's message with  _pMessage_, which is the replacement for the message revoked by the previous call to [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md).</span></span> <span data-ttu-id="f4b3f-114">在新邮件中的数据保证是已吊销消息相同。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-114">The data in the new message is guaranteed to be the same as in the revoked message.</span></span> <span data-ttu-id="f4b3f-115">不应将邮件标记为干净，也不应[IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md)调用后此呼叫。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-115">The message should not be marked as clean, nor should [IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md) be called after this call.</span></span> <span data-ttu-id="f4b3f-116">如果**SaveCompleted**调用成功，则输入[正常](normal-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-116">If the **SaveCompleted** call succeeds, enter the [Normal](normal-state.md) state.</span></span> <span data-ttu-id="f4b3f-117">否则，保持 HandsOffFromNormal 状态。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-117">Otherwise, stay in the HandsOffFromNormal state.</span></span>  <br/> |<span data-ttu-id="f4b3f-118">普通或 HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="f4b3f-118">Normal or HandsOffFromNormal</span></span>  <br/> |
|<span data-ttu-id="f4b3f-119">**IPersistMessage::SaveCompleted**(_pMessage = =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="f4b3f-119">**IPersistMessage::SaveCompleted**(_pMessage ==_ NULL)</span></span>  <br/> |<span data-ttu-id="f4b3f-120">设置为 E_UNEXPECTED 最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-120">Set the last error to E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="f4b3f-121">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="f4b3f-121">HandsOffFromNormal</span></span>  <br/> |
|<span data-ttu-id="f4b3f-122">**HandsOffMessage**、 [IPersistMessage::Save](ipersistmessage-save.md)、 [IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md)</span><span class="sxs-lookup"><span data-stu-id="f4b3f-122">**HandsOffMessage**, [IPersistMessage::Save](ipersistmessage-save.md), [IPersistMessage::InitNew](ipersistmessage-initnew.md), or [IPersistMessage::Load](ipersistmessage-load.md)</span></span> <br/> |<span data-ttu-id="f4b3f-123">设置为 E_UNEXPECTED 最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-123">Set the last error to E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="f4b3f-124">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="f4b3f-124">HandsOffFromNormal</span></span>  <br/> |
|[<span data-ttu-id="f4b3f-125">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="f4b3f-125">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="f4b3f-126">返回的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-126">Return the last error.</span></span>  <br/> |<span data-ttu-id="f4b3f-127">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="f4b3f-127">HandsOffFromNormal</span></span>  <br/> |
|<span data-ttu-id="f4b3f-128">其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法</span><span class="sxs-lookup"><span data-stu-id="f4b3f-128">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="f4b3f-129">设置为 E_UNEXPECTED 最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="f4b3f-129">Set the last error to E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="f4b3f-130">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="f4b3f-130">HandsOffFromNormal</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f4b3f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4b3f-131">See also</span></span>



[<span data-ttu-id="f4b3f-132">表单状态</span><span class="sxs-lookup"><span data-stu-id="f4b3f-132">Form States</span></span>](form-states.md)

