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
ms.openlocfilehash: 85630965c7e78e6fa76e348bfe98cc9060665057
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299522"
---
# <a name="handsoffaftersave-state"></a><span data-ttu-id="2b1b5-103">HandsOffAfterSave 状态</span><span class="sxs-lookup"><span data-stu-id="2b1b5-103">HandsOffAfterSave State</span></span>

  
  
<span data-ttu-id="2b1b5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2b1b5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2b1b5-105">HandsOffAfterSave 状态是将表单内容保存到永久存储的过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-105">The HandsOffAfterSave state is part of the process of saving the contents of a form to permanent storage.</span></span> <span data-ttu-id="2b1b5-106">在此状态下, form 对象应避免对邮件属性值的内存中的值进行更改, 因为可能没有其他机会保存这些更改。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-106">When in this state, the form object should refrain from making changes to the in-memory copies of values of the message's properties, because there may not be another opportunity to save those changes.</span></span> <span data-ttu-id="2b1b5-107">下表介绍了允许从 HandsOffAfterSave 状态进行的转换。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-107">The following table describes allowed transitions from the HandsOffAfterSave state.</span></span>
  
|<span data-ttu-id="2b1b5-108">**IPersistMessage 方法**</span><span class="sxs-lookup"><span data-stu-id="2b1b5-108">**IPersistMessage method**</span></span>|<span data-ttu-id="2b1b5-109">**Action**</span><span class="sxs-lookup"><span data-stu-id="2b1b5-109">**Action**</span></span>|<span data-ttu-id="2b1b5-110">**新状态**</span><span class="sxs-lookup"><span data-stu-id="2b1b5-110">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2b1b5-111">[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage! =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="2b1b5-111">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage !=_ NULL)</span></span>  <br/> |<span data-ttu-id="2b1b5-112">打开任何嵌入的对象。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-112">Open any embedded objects.</span></span> <span data-ttu-id="2b1b5-113">_pMessage_中存储的邮件中的数据保证与前[IPersistMessage:: Save](ipersistmessage-save.md)调用中的邮件相同。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-113">The data in the message stored in  _pMessage_ is guaranteed to be the same as the message in the previous [IPersistMessage::Save](ipersistmessage-save.md) call.</span></span> <span data-ttu-id="2b1b5-114">如果**SaveCompleted**调用成功, 则输入正常状态。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-114">If the **SaveCompleted** call succeeds, enter the Normal state.</span></span> <span data-ttu-id="2b1b5-115">否则, 将最后一个错误设置为 E_OUTOFMEMORY, 并保持 HandsOffAfterSave 状态。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-115">Otherwise, set the last error to E_OUTOFMEMORY and stay in the HandsOffAfterSave state.</span></span>  <br/> |<span data-ttu-id="2b1b5-116">[Normal](normal-state.md)或 HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="2b1b5-116">[Normal](normal-state.md) or HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="2b1b5-117">**IPersistMessage:: SaveCompleted**(_pMessage = =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="2b1b5-117">**IPersistMessage::SaveCompleted**(_pMessage ==_ NULL)</span></span>  <br/> |<span data-ttu-id="2b1b5-118">将最后一个错误设置为 E_INVALIDARG 或 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-118">Set the last error to E_INVALIDARG or E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="2b1b5-119">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="2b1b5-119">HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="2b1b5-120">[IPersistMessage:: HandsOffMessage](ipersistmessage-handsoffmessage.md)、 **Save**或[IPersistMessage:: InitNew](ipersistmessage-initnew.md)</span><span class="sxs-lookup"><span data-stu-id="2b1b5-120">[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md), **Save**, or [IPersistMessage::InitNew](ipersistmessage-initnew.md)</span></span> <br/> |<span data-ttu-id="2b1b5-121">将上一个错误设置为并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-121">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="2b1b5-122">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="2b1b5-122">HandsOffAfterSave</span></span>  <br/> |
|[<span data-ttu-id="2b1b5-123">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="2b1b5-123">IPersistMessage::Load</span></span>](ipersistmessage-load.md) <br/> |<span data-ttu-id="2b1b5-124">使用目标邮件中的数据加载 form 对象。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-124">Load the form object with data from the target message.</span></span> <span data-ttu-id="2b1b5-125">当窗体对象转到文件夹中的下一封邮件或上一封邮件时, 可能会发生此调用。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-125">This call can occur when the form object is going to the next or previous message in a folder.</span></span>  <br/> |<span data-ttu-id="2b1b5-126">一般</span><span class="sxs-lookup"><span data-stu-id="2b1b5-126">Normal</span></span>  <br/> |
|[<span data-ttu-id="2b1b5-127">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="2b1b5-127">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="2b1b5-128">返回上一个错误。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-128">Return the last error.</span></span>  <br/> |<span data-ttu-id="2b1b5-129">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="2b1b5-129">HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="2b1b5-130">其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口的方法</span><span class="sxs-lookup"><span data-stu-id="2b1b5-130">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="2b1b5-131">将上一个错误设置为并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="2b1b5-131">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="2b1b5-132">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="2b1b5-132">HandsOffAfterSave</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2b1b5-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b1b5-133">See also</span></span>



[<span data-ttu-id="2b1b5-134">表单状态</span><span class="sxs-lookup"><span data-stu-id="2b1b5-134">Form States</span></span>](form-states.md)

