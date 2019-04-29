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
ms.openlocfilehash: 17fa0f3d4e74ce7d717a94378880f2cc46150fc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426469"
---
# <a name="handsofffromnormal-state"></a><span data-ttu-id="c8e2e-103">HandsOffFromNormal 状态</span><span class="sxs-lookup"><span data-stu-id="c8e2e-103">HandsOffFromNormal State</span></span>

  
  
<span data-ttu-id="c8e2e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8e2e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c8e2e-105">HandsOffFromNormal 状态非常类似于[HandsOffAfterSave](handsoffaftersave-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-105">The HandsOffFromNormal state is very similar to the [HandsOffAfterSave](handsoffaftersave-state.md) state.</span></span> <span data-ttu-id="c8e2e-106">它是将表单内容保存到永久存储的过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-106">It is part of the process of saving the contents of a form to permanent storage.</span></span> <span data-ttu-id="c8e2e-107">在此状态下, form 对象应避免对邮件属性值的内存中的值进行更改, 因为可能没有其他机会保存这些更改。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-107">When in this state, the form object should refrain from making changes to the in-memory copies of values of the message's properties, because there may not be another opportunity to save those changes.</span></span> <span data-ttu-id="c8e2e-108">下表介绍了允许从 HandsOffFromNormal 状态进行的转换。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-108">The following table describes allowed transitions from the HandsOffFromNormal state.</span></span> 
  
|<span data-ttu-id="c8e2e-109">IPersistMessage \* \* 方法 \* \*</span><span class="sxs-lookup"><span data-stu-id="c8e2e-109">\*\*\*\*IPersistMessage\*\* method\*\*</span></span>|<span data-ttu-id="c8e2e-110">**操作**</span><span class="sxs-lookup"><span data-stu-id="c8e2e-110">**Action**</span></span>|<span data-ttu-id="c8e2e-111">**新状态**</span><span class="sxs-lookup"><span data-stu-id="c8e2e-111">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8e2e-112">[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage! =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="c8e2e-112">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage !=_ NULL)</span></span>  <br/> |<span data-ttu-id="c8e2e-113">将邮件对象的邮件替换为_pMessage_, 这是以前调用[IPersistMessage:: HandsOffMessage](ipersistmessage-handsoffmessage.md)吊销的邮件的替代邮件。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-113">Replace the message object's message with  _pMessage_, which is the replacement for the message revoked by the previous call to [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md).</span></span> <span data-ttu-id="c8e2e-114">确保新邮件中的数据与吊销的邮件中的数据相同。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-114">The data in the new message is guaranteed to be the same as in the revoked message.</span></span> <span data-ttu-id="c8e2e-115">不应将邮件标记为 "干净", 也不应[IMAPIViewAdviseSink:: OnSaved](imapiviewadvisesink-onsaved.md)在此调用之后调用。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-115">The message should not be marked as clean, nor should [IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md) be called after this call.</span></span> <span data-ttu-id="c8e2e-116">如果**SaveCompleted**调用成功, 则输入[正常](normal-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-116">If the **SaveCompleted** call succeeds, enter the [Normal](normal-state.md) state.</span></span> <span data-ttu-id="c8e2e-117">否则, 保持 HandsOffFromNormal 状态。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-117">Otherwise, stay in the HandsOffFromNormal state.</span></span>  <br/> |<span data-ttu-id="c8e2e-118">Normal 或 HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="c8e2e-118">Normal or HandsOffFromNormal</span></span>  <br/> |
|<span data-ttu-id="c8e2e-119">**IPersistMessage:: SaveCompleted**(_pMessage = =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="c8e2e-119">**IPersistMessage::SaveCompleted**(_pMessage ==_ NULL)</span></span>  <br/> |<span data-ttu-id="c8e2e-120">将最后一个错误设置为 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-120">Set the last error to E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="c8e2e-121">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="c8e2e-121">HandsOffFromNormal</span></span>  <br/> |
|<span data-ttu-id="c8e2e-122">**HandsOffMessage**、 [IPersistMessage:: Save](ipersistmessage-save.md)、 [IPersistMessage:: InitNew](ipersistmessage-initnew.md)或[IPersistMessage:: Load](ipersistmessage-load.md)</span><span class="sxs-lookup"><span data-stu-id="c8e2e-122">**HandsOffMessage**, [IPersistMessage::Save](ipersistmessage-save.md), [IPersistMessage::InitNew](ipersistmessage-initnew.md), or [IPersistMessage::Load](ipersistmessage-load.md)</span></span> <br/> |<span data-ttu-id="c8e2e-123">将最后一个错误设置为 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-123">Set the last error to E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="c8e2e-124">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="c8e2e-124">HandsOffFromNormal</span></span>  <br/> |
|[<span data-ttu-id="c8e2e-125">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="c8e2e-125">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="c8e2e-126">返回上一个错误。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-126">Return the last error.</span></span>  <br/> |<span data-ttu-id="c8e2e-127">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="c8e2e-127">HandsOffFromNormal</span></span>  <br/> |
|<span data-ttu-id="c8e2e-128">其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口的方法</span><span class="sxs-lookup"><span data-stu-id="c8e2e-128">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="c8e2e-129">将最后一个错误设置为 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="c8e2e-129">Set the last error to E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="c8e2e-130">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="c8e2e-130">HandsOffFromNormal</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c8e2e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8e2e-131">See also</span></span>



[<span data-ttu-id="c8e2e-132">表单状态</span><span class="sxs-lookup"><span data-stu-id="c8e2e-132">Form States</span></span>](form-states.md)

