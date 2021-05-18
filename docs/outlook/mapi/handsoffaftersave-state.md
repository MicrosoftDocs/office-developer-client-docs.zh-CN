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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406603"
---
# <a name="handsoffaftersave-state"></a><span data-ttu-id="23efd-103">HandsOffAfterSave 状态</span><span class="sxs-lookup"><span data-stu-id="23efd-103">HandsOffAfterSave State</span></span>

  
  
<span data-ttu-id="23efd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="23efd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="23efd-105">HandsOffAfterSave 状态是将表单的内容保存为永久存储过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="23efd-105">The HandsOffAfterSave state is part of the process of saving the contents of a form to permanent storage.</span></span> <span data-ttu-id="23efd-106">在此状态中时，form 对象应避免对邮件属性值的内存中副本进行更改，因为可能再没有保存这些更改的机会。</span><span class="sxs-lookup"><span data-stu-id="23efd-106">When in this state, the form object should refrain from making changes to the in-memory copies of values of the message's properties, because there may not be another opportunity to save those changes.</span></span> <span data-ttu-id="23efd-107">下表介绍了允许从 HandsOffAfterSave 状态转换。</span><span class="sxs-lookup"><span data-stu-id="23efd-107">The following table describes allowed transitions from the HandsOffAfterSave state.</span></span>
  
|<span data-ttu-id="23efd-108">**IPersistMessage 方法**</span><span class="sxs-lookup"><span data-stu-id="23efd-108">**IPersistMessage method**</span></span>|<span data-ttu-id="23efd-109">**Action**</span><span class="sxs-lookup"><span data-stu-id="23efd-109">**Action**</span></span>|<span data-ttu-id="23efd-110">**新状态**</span><span class="sxs-lookup"><span data-stu-id="23efd-110">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23efd-111">[IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) _(pMessage ！=_ NULL) </span><span class="sxs-lookup"><span data-stu-id="23efd-111">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage !=_ NULL)</span></span>  <br/> |<span data-ttu-id="23efd-112">打开任何嵌入的对象。</span><span class="sxs-lookup"><span data-stu-id="23efd-112">Open any embedded objects.</span></span> <span data-ttu-id="23efd-113">_pMessage_ 中存储的邮件数据保证与上一 [个 IPersistMessage：：Save](ipersistmessage-save.md)调用中的邮件相同。</span><span class="sxs-lookup"><span data-stu-id="23efd-113">The data in the message stored in  _pMessage_ is guaranteed to be the same as the message in the previous [IPersistMessage::Save](ipersistmessage-save.md) call.</span></span> <span data-ttu-id="23efd-114">如果 **SaveCompleted** 调用成功，请输入 Normal 状态。</span><span class="sxs-lookup"><span data-stu-id="23efd-114">If the **SaveCompleted** call succeeds, enter the Normal state.</span></span> <span data-ttu-id="23efd-115">否则，将最后一个错误设置为 E_OUTOFMEMORY并保持 HandsOffAfterSave 状态。</span><span class="sxs-lookup"><span data-stu-id="23efd-115">Otherwise, set the last error to E_OUTOFMEMORY and stay in the HandsOffAfterSave state.</span></span>  <br/> |<span data-ttu-id="23efd-116">[Normal](normal-state.md) 或 HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="23efd-116">[Normal](normal-state.md) or HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="23efd-117">**IPersistMessage：：SaveCompleted** (_pMessage ==_ NULL) </span><span class="sxs-lookup"><span data-stu-id="23efd-117">**IPersistMessage::SaveCompleted**(_pMessage ==_ NULL)</span></span>  <br/> |<span data-ttu-id="23efd-118">将最后一个错误设置为E_INVALIDARG或E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="23efd-118">Set the last error to E_INVALIDARG or E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="23efd-119">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="23efd-119">HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="23efd-120">[IPersistMessage：：HandsOffMessage、Save](ipersistmessage-handsoffmessage.md)或[IPersistMessage：：InitNew](ipersistmessage-initnew.md) </span><span class="sxs-lookup"><span data-stu-id="23efd-120">[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md), **Save**, or [IPersistMessage::InitNew](ipersistmessage-initnew.md)</span></span> <br/> |<span data-ttu-id="23efd-121">将最后一个错误设置为 并返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="23efd-121">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="23efd-122">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="23efd-122">HandsOffAfterSave</span></span>  <br/> |
|[<span data-ttu-id="23efd-123">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="23efd-123">IPersistMessage::Load</span></span>](ipersistmessage-load.md) <br/> |<span data-ttu-id="23efd-124">使用来自目标邮件的数据加载表单对象。</span><span class="sxs-lookup"><span data-stu-id="23efd-124">Load the form object with data from the target message.</span></span> <span data-ttu-id="23efd-125">当窗体对象发送到文件夹中的下一封邮件或上一封邮件时，可能会发生此调用。</span><span class="sxs-lookup"><span data-stu-id="23efd-125">This call can occur when the form object is going to the next or previous message in a folder.</span></span>  <br/> |<span data-ttu-id="23efd-126">一般</span><span class="sxs-lookup"><span data-stu-id="23efd-126">Normal</span></span>  <br/> |
|[<span data-ttu-id="23efd-127">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="23efd-127">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="23efd-128">返回最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="23efd-128">Return the last error.</span></span>  <br/> |<span data-ttu-id="23efd-129">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="23efd-129">HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="23efd-130">其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法</span><span class="sxs-lookup"><span data-stu-id="23efd-130">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="23efd-131">将最后一个错误设置为 并返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="23efd-131">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="23efd-132">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="23efd-132">HandsOffAfterSave</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="23efd-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23efd-133">See also</span></span>



[<span data-ttu-id="23efd-134">表单状态</span><span class="sxs-lookup"><span data-stu-id="23efd-134">Form States</span></span>](form-states.md)

