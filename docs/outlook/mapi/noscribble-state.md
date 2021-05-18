---
title: NoScribble 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0246138f-c55e-4353-8e53-e973f524d52c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 239f11cf27cdebff3d51645319d7ada3b9bb9ff6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326199"
---
# <a name="noscribble-state"></a><span data-ttu-id="c8e1f-103">NoScribble 状态</span><span class="sxs-lookup"><span data-stu-id="c8e1f-103">NoScribble State</span></span>

  
  
<span data-ttu-id="c8e1f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8e1f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c8e1f-105">NoScribble 状态指示正在保存对邮件的更改。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-105">The NoScribble state indicates that changes to a message are being saved.</span></span> <span data-ttu-id="c8e1f-106">当客户端应用程序调用表单对象的 [IPersistMessage：：Save](ipersistmessage-save.md) 方法时，将实际保存表单对象用户界面中存储的值。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-106">The actual saving of values stored in the form object's user interface occurs when the form object's [IPersistMessage::Save](ipersistmessage-save.md) method is called by the client application.</span></span> <span data-ttu-id="c8e1f-107">下表介绍了允许从 NoScribble 状态转换。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-107">The following table describes allowed transitions from the NoScribble state.</span></span> 
  
|<span data-ttu-id="c8e1f-108">IPersistMessage\*\* 方法\*\*</span><span class="sxs-lookup"><span data-stu-id="c8e1f-108">\*\*\*\*IPersistMessage\*\* method\*\*</span></span>|<span data-ttu-id="c8e1f-109">**Action**</span><span class="sxs-lookup"><span data-stu-id="c8e1f-109">**Action**</span></span>|<span data-ttu-id="c8e1f-110">**新状态**</span><span class="sxs-lookup"><span data-stu-id="c8e1f-110">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8e1f-111">[IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) (_pMessage ==_ NULL) </span><span class="sxs-lookup"><span data-stu-id="c8e1f-111">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage ==_ NULL)</span></span>  <br/> |<span data-ttu-id="c8e1f-112">如果  _fSameAsLoad_ 标记在导致表单进入 NoScribble 状态且消息已修改的 [IPersistMessage：：Save](ipersistmessage-save.md) 调用上为 TRUE，请在内部将更改标记为已保存并调用 [IMAPIViewAdviseSink：：OnSaved](imapiviewadvisesink-onsaved.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-112">If  _fSameAsLoad_ flag was TRUE on the [IPersistMessage::Save](ipersistmessage-save.md) call that caused the form to enter the NoScribble state and the message has been modified, internally mark the changes as saved and call the [IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md) method.</span></span>  <br/> |[<span data-ttu-id="c8e1f-113">Normal</span><span class="sxs-lookup"><span data-stu-id="c8e1f-113">Normal</span></span>](normal-state.md) <br/> |
|<span data-ttu-id="c8e1f-114">**IPersistMessage：：SaveCompleted** _(pMessage ！=_ NULL) </span><span class="sxs-lookup"><span data-stu-id="c8e1f-114">**IPersistMessage::SaveCompleted**(_pMessage !=_ NULL)</span></span>  <br/> |<span data-ttu-id="c8e1f-115">调用 [IPersistMessage：：HandsOffMessage](ipersistmessage-handsoffmessage.md) 方法 (类似于 OLE [IPersistStorage：：HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx) 方法) 后跟常规 **SaveCompleted** 操作。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-115">Call the [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) method (similar to the OLE [IPersistStorage::HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx) method) followed by the normal **SaveCompleted** actions.</span></span> <span data-ttu-id="c8e1f-116">如果 **SaveCompleted** 成功，请输入 Normal 状态。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-116">If **SaveCompleted** was successful, enter the Normal state.</span></span> <span data-ttu-id="c8e1f-117">否则，输入 [HandsOffAfterSave](handsoffaftersave-state.md) 状态。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-117">Otherwise, enter the [HandsOffAfterSave](handsoffaftersave-state.md) state.</span></span>  <br/> |<span data-ttu-id="c8e1f-118">Normal 或 HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="c8e1f-118">Normal or HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="c8e1f-119">**HandsOffMessage**</span><span class="sxs-lookup"><span data-stu-id="c8e1f-119">**HandsOffMessage**</span></span> <br/> |<span data-ttu-id="c8e1f-120">对嵌入的邮件递归调用 **HandsOffMessage** 方法，或对嵌入的 OLE 对象调用 OLE **IPersistStorage：：HandsOffStorage** 方法。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-120">Recursively invoke the **HandsOffMessage** method on embedded messages or the OLE **IPersistStorage::HandsOffStorage** method on embedded OLE objects.</span></span> <span data-ttu-id="c8e1f-121">释放邮件对象和任何嵌入的邮件或对象。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-121">Release the message object and any embedded messages or objects.</span></span>  <br/> |<span data-ttu-id="c8e1f-122">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="c8e1f-122">HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="c8e1f-123">**Save** [、IPersistMessage：：InitNew](ipersistmessage-initnew.md)或 [IPersistMessage：：Load](ipersistmessage-load.md)</span><span class="sxs-lookup"><span data-stu-id="c8e1f-123">**Save**, [IPersistMessage::InitNew](ipersistmessage-initnew.md), or [IPersistMessage::Load](ipersistmessage-load.md)</span></span> <br/> |<span data-ttu-id="c8e1f-124">将最后一个错误设置为 并返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-124">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="c8e1f-125">NoScribble</span><span class="sxs-lookup"><span data-stu-id="c8e1f-125">NoScribble</span></span>  <br/> |
|[<span data-ttu-id="c8e1f-126">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="c8e1f-126">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="c8e1f-127">返回最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-127">Return the last error.</span></span>  <br/> |<span data-ttu-id="c8e1f-128">NoScribble</span><span class="sxs-lookup"><span data-stu-id="c8e1f-128">NoScribble</span></span>  <br/> |
|<span data-ttu-id="c8e1f-129">其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法</span><span class="sxs-lookup"><span data-stu-id="c8e1f-129">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="c8e1f-130">将最后一个错误设置为 并返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="c8e1f-130">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="c8e1f-131">NoScribble</span><span class="sxs-lookup"><span data-stu-id="c8e1f-131">NoScribble</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c8e1f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8e1f-132">See also</span></span>



[<span data-ttu-id="c8e1f-133">表单状态</span><span class="sxs-lookup"><span data-stu-id="c8e1f-133">Form States</span></span>](form-states.md)

