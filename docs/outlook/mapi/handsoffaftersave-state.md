---
title: HandsOffAfterSave 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ffdfed49-2c52-445c-8051-6e566f61eedc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4bc4d680903d81b51a39ed39db3861597443d116
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775069"
---
# <a name="handsoffaftersave-state"></a><span data-ttu-id="83962-103">HandsOffAfterSave 状态</span><span class="sxs-lookup"><span data-stu-id="83962-103">HandsOffAfterSave State</span></span>

  
  
<span data-ttu-id="83962-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="83962-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="83962-105">HandsOffAfterSave 状态是将窗体的内容保存到永久存储过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="83962-105">The HandsOffAfterSave state is part of the process of saving the contents of a form to permanent storage.</span></span> <span data-ttu-id="83962-106">在此状态下，窗体对象应避免更改消息的属性的值的内存中副本因为可能没有其他机会保存这些更改。</span><span class="sxs-lookup"><span data-stu-id="83962-106">When in this state, the form object should refrain from making changes to the in-memory copies of values of the message's properties, because there may not be another opportunity to save those changes.</span></span> <span data-ttu-id="83962-107">下表介绍允许的 HandsOffAfterSave 状态转换。</span><span class="sxs-lookup"><span data-stu-id="83962-107">The following table describes allowed transitions from the HandsOffAfterSave state.</span></span>
  
|<span data-ttu-id="83962-108">**IPersistMessage 方法**</span><span class="sxs-lookup"><span data-stu-id="83962-108">**IPersistMessage method**</span></span>|<span data-ttu-id="83962-109">**操作**</span><span class="sxs-lookup"><span data-stu-id="83962-109">**Action**</span></span>|<span data-ttu-id="83962-110">**新的状态**</span><span class="sxs-lookup"><span data-stu-id="83962-110">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="83962-111">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage ！ =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="83962-111">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage !=_ NULL)</span></span>  <br/> |<span data-ttu-id="83962-112">打开任何嵌入的对象。</span><span class="sxs-lookup"><span data-stu-id="83962-112">Open any embedded objects.</span></span> <span data-ttu-id="83962-113">保证_pMessage_中存储的邮件中的数据与以前的[IPersistMessage::Save](ipersistmessage-save.md)呼叫中的消息。</span><span class="sxs-lookup"><span data-stu-id="83962-113">The data in the message stored in  _pMessage_ is guaranteed to be the same as the message in the previous [IPersistMessage::Save](ipersistmessage-save.md) call.</span></span> <span data-ttu-id="83962-114">如果**SaveCompleted**调用成功，则输入正常状态。</span><span class="sxs-lookup"><span data-stu-id="83962-114">If the **SaveCompleted** call succeeds, enter the Normal state.</span></span> <span data-ttu-id="83962-115">否则为设置为 E_OUTOFMEMORY 的最后一个错误，并保持 HandsOffAfterSave 状态。</span><span class="sxs-lookup"><span data-stu-id="83962-115">Otherwise, set the last error to E_OUTOFMEMORY and stay in the HandsOffAfterSave state.</span></span>  <br/> |<span data-ttu-id="83962-116">[普通](normal-state.md)或 HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="83962-116">[Normal](normal-state.md) or HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="83962-117">**IPersistMessage::SaveCompleted**(_pMessage = =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="83962-117">**IPersistMessage::SaveCompleted**(_pMessage ==_ NULL)</span></span>  <br/> |<span data-ttu-id="83962-118">设置为 E_INVALIDARG 或 E_UNEXPECTED 的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="83962-118">Set the last error to E_INVALIDARG or E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="83962-119">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="83962-119">HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="83962-120">[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)、**保存**或[IPersistMessage::InitNew](ipersistmessage-initnew.md)</span><span class="sxs-lookup"><span data-stu-id="83962-120">[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md), **Save**, or [IPersistMessage::InitNew](ipersistmessage-initnew.md)</span></span> <br/> |<span data-ttu-id="83962-121">设置为上一个错误，并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="83962-121">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="83962-122">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="83962-122">HandsOffAfterSave</span></span>  <br/> |
|[<span data-ttu-id="83962-123">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="83962-123">IPersistMessage::Load</span></span>](ipersistmessage-load.md) <br/> |<span data-ttu-id="83962-124">从目标邮件加载数据的窗体对象。</span><span class="sxs-lookup"><span data-stu-id="83962-124">Load the form object with data from the target message.</span></span> <span data-ttu-id="83962-125">Form 对象转到文件夹中的下一页或上一页消息时，可能出现此呼叫。</span><span class="sxs-lookup"><span data-stu-id="83962-125">This call can occur when the form object is going to the next or previous message in a folder.</span></span>  <br/> |<span data-ttu-id="83962-126">常规</span><span class="sxs-lookup"><span data-stu-id="83962-126">Normal</span></span>  <br/> |
|[<span data-ttu-id="83962-127">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="83962-127">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="83962-128">返回的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="83962-128">Return the last error.</span></span>  <br/> |<span data-ttu-id="83962-129">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="83962-129">HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="83962-130">其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法</span><span class="sxs-lookup"><span data-stu-id="83962-130">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="83962-131">设置为上一个错误，并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="83962-131">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="83962-132">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="83962-132">HandsOffAfterSave</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="83962-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83962-133">See also</span></span>



[<span data-ttu-id="83962-134">表单状态</span><span class="sxs-lookup"><span data-stu-id="83962-134">Form States</span></span>](form-states.md)

