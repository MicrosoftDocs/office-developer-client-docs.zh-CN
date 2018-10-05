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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392563"
---
# <a name="noscribble-state"></a><span data-ttu-id="7bf68-103">NoScribble 状态</span><span class="sxs-lookup"><span data-stu-id="7bf68-103">NoScribble State</span></span>

  
  
<span data-ttu-id="7bf68-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7bf68-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7bf68-105">NoScribble 状态指示邮件的更改将被保存。</span><span class="sxs-lookup"><span data-stu-id="7bf68-105">The NoScribble state indicates that changes to a message are being saved.</span></span> <span data-ttu-id="7bf68-106">Form 对象的[IPersistMessage::Save](ipersistmessage-save.md)方法由客户端应用程序时发生实际将保存 form 对象的用户界面中存储的值。</span><span class="sxs-lookup"><span data-stu-id="7bf68-106">The actual saving of values stored in the form object's user interface occurs when the form object's [IPersistMessage::Save](ipersistmessage-save.md) method is called by the client application.</span></span> <span data-ttu-id="7bf68-107">下表介绍允许的 NoScribble 状态转换。</span><span class="sxs-lookup"><span data-stu-id="7bf68-107">The following table describes allowed transitions from the NoScribble state.</span></span> 
  
|<span data-ttu-id="7bf68-108">IPersistMessage \* \* 方法 \* \*</span><span class="sxs-lookup"><span data-stu-id="7bf68-108">\*\*\*\*IPersistMessage\*\* method\*\*</span></span>|<span data-ttu-id="7bf68-109">**操作**</span><span class="sxs-lookup"><span data-stu-id="7bf68-109">**Action**</span></span>|<span data-ttu-id="7bf68-110">**新的状态**</span><span class="sxs-lookup"><span data-stu-id="7bf68-110">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7bf68-111">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage = =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="7bf68-111">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage ==_ NULL)</span></span>  <br/> |<span data-ttu-id="7bf68-112">如果_fSameAsLoad_标志上已 TRUE [IPersistMessage::Save](ipersistmessage-save.md)呼叫导致该窗体输入 NoScribble 状态和邮件已被修改、 内部标记为已保存的更改，并调用[IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7bf68-112">If  _fSameAsLoad_ flag was TRUE on the [IPersistMessage::Save](ipersistmessage-save.md) call that caused the form to enter the NoScribble state and the message has been modified, internally mark the changes as saved and call the [IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md) method.</span></span>  <br/> |[<span data-ttu-id="7bf68-113">Normal</span><span class="sxs-lookup"><span data-stu-id="7bf68-113">Normal</span></span>](normal-state.md) <br/> |
|<span data-ttu-id="7bf68-114">**IPersistMessage::SaveCompleted**(_pMessage ！ =_ NULL)</span><span class="sxs-lookup"><span data-stu-id="7bf68-114">**IPersistMessage::SaveCompleted**(_pMessage !=_ NULL)</span></span>  <br/> |<span data-ttu-id="7bf68-115">调用[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)方法 （类似于 OLE [IPersistStorage::HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx)方法） 跟普通**SaveCompleted**操作。</span><span class="sxs-lookup"><span data-stu-id="7bf68-115">Call the [IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) method (similar to the OLE [IPersistStorage::HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx) method) followed by the normal **SaveCompleted** actions.</span></span> <span data-ttu-id="7bf68-116">如果**SaveCompleted**成功，则输入正常状态。</span><span class="sxs-lookup"><span data-stu-id="7bf68-116">If **SaveCompleted** was successful, enter the Normal state.</span></span> <span data-ttu-id="7bf68-117">否则，请输入[HandsOffAfterSave](handsoffaftersave-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="7bf68-117">Otherwise, enter the [HandsOffAfterSave](handsoffaftersave-state.md) state.</span></span>  <br/> |<span data-ttu-id="7bf68-118">普通或 HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="7bf68-118">Normal or HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="7bf68-119">**HandsOffMessage**</span><span class="sxs-lookup"><span data-stu-id="7bf68-119">**HandsOffMessage**</span></span> <br/> |<span data-ttu-id="7bf68-120">以递归方式调用嵌入邮件上的**HandsOffMessage**方法或嵌入的 OLE 对象的 OLE **IPersistStorage::HandsOffStorage**方法。</span><span class="sxs-lookup"><span data-stu-id="7bf68-120">Recursively invoke the **HandsOffMessage** method on embedded messages or the OLE **IPersistStorage::HandsOffStorage** method on embedded OLE objects.</span></span> <span data-ttu-id="7bf68-121">发布的消息对象和任何嵌入式的邮件或对象。</span><span class="sxs-lookup"><span data-stu-id="7bf68-121">Release the message object and any embedded messages or objects.</span></span>  <br/> |<span data-ttu-id="7bf68-122">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="7bf68-122">HandsOffAfterSave</span></span>  <br/> |
|<span data-ttu-id="7bf68-123">**保存**、 [IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md)</span><span class="sxs-lookup"><span data-stu-id="7bf68-123">**Save**, [IPersistMessage::InitNew](ipersistmessage-initnew.md), or [IPersistMessage::Load](ipersistmessage-load.md)</span></span> <br/> |<span data-ttu-id="7bf68-124">设置为上一个错误，并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="7bf68-124">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="7bf68-125">NoScribble</span><span class="sxs-lookup"><span data-stu-id="7bf68-125">NoScribble</span></span>  <br/> |
|[<span data-ttu-id="7bf68-126">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="7bf68-126">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="7bf68-127">返回的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="7bf68-127">Return the last error.</span></span>  <br/> |<span data-ttu-id="7bf68-128">NoScribble</span><span class="sxs-lookup"><span data-stu-id="7bf68-128">NoScribble</span></span>  <br/> |
|<span data-ttu-id="7bf68-129">其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法</span><span class="sxs-lookup"><span data-stu-id="7bf68-129">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="7bf68-130">设置为上一个错误，并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="7bf68-130">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="7bf68-131">NoScribble</span><span class="sxs-lookup"><span data-stu-id="7bf68-131">NoScribble</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7bf68-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bf68-132">See also</span></span>



[<span data-ttu-id="7bf68-133">表单状态</span><span class="sxs-lookup"><span data-stu-id="7bf68-133">Form States</span></span>](form-states.md)

