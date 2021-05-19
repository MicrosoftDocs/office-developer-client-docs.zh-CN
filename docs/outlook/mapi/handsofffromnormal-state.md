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
# <a name="handsofffromnormal-state"></a><span data-ttu-id="1a4fa-103">HandsOffFromNormal 状态</span><span class="sxs-lookup"><span data-stu-id="1a4fa-103">HandsOffFromNormal State</span></span>

  
  
<span data-ttu-id="1a4fa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1a4fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1a4fa-105">HandsOffFromNormal 状态非常类似于 [HandsOffAfterSave](handsoffaftersave-state.md) 状态。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-105">The HandsOffFromNormal state is very similar to the [HandsOffAfterSave](handsoffaftersave-state.md) state.</span></span> <span data-ttu-id="1a4fa-106">它是将表单的内容保存为永久存储的过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-106">It is part of the process of saving the contents of a form to permanent storage.</span></span> <span data-ttu-id="1a4fa-107">在此状态中时，form 对象应避免对邮件属性值的内存中副本进行更改，因为可能再没有保存这些更改的机会。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-107">When in this state, the form object should refrain from making changes to the in-memory copies of values of the message's properties, because there may not be another opportunity to save those changes.</span></span> <span data-ttu-id="1a4fa-108">下表介绍了允许从 HandsOffFromNormal 状态转换。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-108">The following table describes allowed transitions from the HandsOffFromNormal state.</span></span> 
  
|<span data-ttu-id="1a4fa-109">IPersistMessage\*\* 方法\*\*</span><span class="sxs-lookup"><span data-stu-id="1a4fa-109">\*\*\*\*IPersistMessage\*\* method\*\*</span></span>|<span data-ttu-id="1a4fa-110">**Action**</span><span class="sxs-lookup"><span data-stu-id="1a4fa-110">**Action**</span></span>|<span data-ttu-id="1a4fa-111">**新状态**</span><span class="sxs-lookup"><span data-stu-id="1a4fa-111">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a4fa-112">[IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) _(pMessage ！=_ NULL) </span><span class="sxs-lookup"><span data-stu-id="1a4fa-112">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage !=_ NULL)</span></span>  <br/> |<span data-ttu-id="1a4fa-113">将邮件对象的邮件替换为  _pMessage_，这是上一次调用 [IPersistMessage：：HandsOffMessage 时吊销的邮件的替换](ipersistmessage-handsoffmessage.md)。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-113">Replace the message object's message with  _pMessage_, which is the replacement for the message revoked by the previous call to [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md).</span></span> <span data-ttu-id="1a4fa-114">新邮件中的数据保证与吊销的邮件中的数据相同。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-114">The data in the new message is guaranteed to be the same as in the revoked message.</span></span> <span data-ttu-id="1a4fa-115">不应将邮件标记为干净，也不应在此调用后调用[IMAPIViewAdviseSink：：OnSaved。](imapiviewadvisesink-onsaved.md)</span><span class="sxs-lookup"><span data-stu-id="1a4fa-115">The message should not be marked as clean, nor should [IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md) be called after this call.</span></span> <span data-ttu-id="1a4fa-116">如果 **SaveCompleted** 调用成功，请输入 [Normal](normal-state.md) 状态。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-116">If the **SaveCompleted** call succeeds, enter the [Normal](normal-state.md) state.</span></span> <span data-ttu-id="1a4fa-117">否则，请保持 HandsOffFromNormal 状态。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-117">Otherwise, stay in the HandsOffFromNormal state.</span></span>  <br/> |<span data-ttu-id="1a4fa-118">Normal 或 HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="1a4fa-118">Normal or HandsOffFromNormal</span></span>  <br/> |
|<span data-ttu-id="1a4fa-119">**IPersistMessage：：SaveCompleted** (_pMessage ==_ NULL) </span><span class="sxs-lookup"><span data-stu-id="1a4fa-119">**IPersistMessage::SaveCompleted**(_pMessage ==_ NULL)</span></span>  <br/> |<span data-ttu-id="1a4fa-120">将最后一个错误设置为E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-120">Set the last error to E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="1a4fa-121">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="1a4fa-121">HandsOffFromNormal</span></span>  <br/> |
|<span data-ttu-id="1a4fa-122">**HandsOffMessage** [、IPersistMessage：：Save、IPersistMessage：：InitNew](ipersistmessage-save.md)或 [IPersistMessage：：Load](ipersistmessage-load.md) [](ipersistmessage-initnew.md)</span><span class="sxs-lookup"><span data-stu-id="1a4fa-122">**HandsOffMessage**, [IPersistMessage::Save](ipersistmessage-save.md), [IPersistMessage::InitNew](ipersistmessage-initnew.md), or [IPersistMessage::Load](ipersistmessage-load.md)</span></span> <br/> |<span data-ttu-id="1a4fa-123">将最后一个错误设置为E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-123">Set the last error to E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="1a4fa-124">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="1a4fa-124">HandsOffFromNormal</span></span>  <br/> |
|[<span data-ttu-id="1a4fa-125">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="1a4fa-125">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="1a4fa-126">返回最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-126">Return the last error.</span></span>  <br/> |<span data-ttu-id="1a4fa-127">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="1a4fa-127">HandsOffFromNormal</span></span>  <br/> |
|<span data-ttu-id="1a4fa-128">其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法</span><span class="sxs-lookup"><span data-stu-id="1a4fa-128">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="1a4fa-129">将最后一个错误设置为E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="1a4fa-129">Set the last error to E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="1a4fa-130">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="1a4fa-130">HandsOffFromNormal</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1a4fa-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a4fa-131">See also</span></span>



[<span data-ttu-id="1a4fa-132">表单状态</span><span class="sxs-lookup"><span data-stu-id="1a4fa-132">Form States</span></span>](form-states.md)

