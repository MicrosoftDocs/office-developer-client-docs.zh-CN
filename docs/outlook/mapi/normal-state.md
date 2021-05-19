---
title: 正常状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b2acad7-5ef8-44db-911f-3bd2a7ca2778
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d7b50a92c58dd7ab1f03cb4cf84acc2d4a2b404b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335740"
---
# <a name="normal-state"></a><span data-ttu-id="e0c5b-103">正常状态</span><span class="sxs-lookup"><span data-stu-id="e0c5b-103">Normal State</span></span>

  
  
<span data-ttu-id="e0c5b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e0c5b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e0c5b-105">"正常"状态是表单对象花费大部分时间等待客户端应用程序启动操作（如保存更改或关闭表单）的地方。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-105">The Normal state is where the form object spends most of its time, waiting for client applications to initiate an action such as saving changes or closing the form.</span></span> <span data-ttu-id="e0c5b-106">下表介绍了允许从 Normal 状态转换。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-106">The following table describes allowed transitions from the Normal state.</span></span>
  
|<span data-ttu-id="e0c5b-107">**IPersistMessage 方法**</span><span class="sxs-lookup"><span data-stu-id="e0c5b-107">**IPersistMessage method**</span></span>|<span data-ttu-id="e0c5b-108">**Action**</span><span class="sxs-lookup"><span data-stu-id="e0c5b-108">**Action**</span></span>|<span data-ttu-id="e0c5b-109">**新状态**</span><span class="sxs-lookup"><span data-stu-id="e0c5b-109">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e0c5b-110">[IPersistMessage：：Save](ipersistmessage-save.md) (_pMessage ==_ NULL，fSameAsLoad  _==_ TRUE) </span><span class="sxs-lookup"><span data-stu-id="e0c5b-110">[IPersistMessage::Save](ipersistmessage-save.md)(_pMessage ==_ NULL,  _fSameAsLoad ==_ TRUE)</span></span>  <br/> <span data-ttu-id="e0c5b-111">- 或 -</span><span class="sxs-lookup"><span data-stu-id="e0c5b-111">-or-</span></span>  <br/> <span data-ttu-id="e0c5b-112">**IPersistMessage：：Save** _(pMessage ！=_ NULL，fSameAsLoad  _==_ FALSE) </span><span class="sxs-lookup"><span data-stu-id="e0c5b-112">**IPersistMessage::Save**(_pMessage !=_ NULL,  _fSameAsLoad ==_ FALSE)</span></span>  <br/> |<span data-ttu-id="e0c5b-113">递归保存任何已修改的嵌入 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-113">Recursively save any embedded OLE objects that have been modified.</span></span> <span data-ttu-id="e0c5b-114">将邮件数据保存回 message 对象。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-114">Save message data back to the message object.</span></span> <span data-ttu-id="e0c5b-115">存储  _fSameAsLoad_ 标志，供以后在 [NoScribble 状态使用](noscribble-state.md) 。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-115">Store the  _fSameAsLoad_ flag for later use in the [NoScribble](noscribble-state.md) state.</span></span>  <br/> |<span data-ttu-id="e0c5b-116">NoScribble</span><span class="sxs-lookup"><span data-stu-id="e0c5b-116">NoScribble</span></span>  <br/> |
|<span data-ttu-id="e0c5b-117">**IPersistMessage：：Save** (_pMessage ！=_  _NULL，fSameAsLoad ==_ TRUE) </span><span class="sxs-lookup"><span data-stu-id="e0c5b-117">**IPersistMessage::Save**(_pMessage !=_ NULL,  _fSameAsLoad ==_ TRUE)</span></span>  <br/> |<span data-ttu-id="e0c5b-118">这一点与上一种情况相同，只不过此 **Save** 调用在内存不足的情况下使用，并且不得因内存不足而失败。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-118">This is the same as the previous case, except that this **Save** call is used in low-memory situations and must not fail for lack of memory.</span></span>  <br/> |<span data-ttu-id="e0c5b-119">NoScribble</span><span class="sxs-lookup"><span data-stu-id="e0c5b-119">NoScribble</span></span>  <br/> |
|[<span data-ttu-id="e0c5b-120">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="e0c5b-120">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md) <br/> |<span data-ttu-id="e0c5b-121">对嵌入的邮件递归调用 **HandsOffMessage** 方法，或对嵌入的 OLE 对象调用 OLE [IPersistStorage：：HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-121">Recursively invoke the **HandsOffMessage** method on embedded messages or the OLE [IPersistStorage::HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx) method on embedded OLE objects.</span></span> <span data-ttu-id="e0c5b-122">释放邮件对象和任何嵌入的邮件或对象。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-122">Release the message object and any embedded messages or objects.</span></span>  <br/> |[<span data-ttu-id="e0c5b-123">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="e0c5b-123">HandsOffFromNormal</span></span>](handsofffromnormal-state.md) <br/> |
|<span data-ttu-id="e0c5b-124">[IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) [、IPersistMessage：：InitNew](ipersistmessage-initnew.md) 或 [IPersistMessage：：Load](ipersistmessage-load.md)</span><span class="sxs-lookup"><span data-stu-id="e0c5b-124">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md), [IPersistMessage::InitNew](ipersistmessage-initnew.md) or [IPersistMessage::Load](ipersistmessage-load.md)</span></span> <br/> |<span data-ttu-id="e0c5b-125">将最后一个错误设置为 并返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-125">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="e0c5b-126">一般</span><span class="sxs-lookup"><span data-stu-id="e0c5b-126">Normal</span></span>  <br/> |
|[<span data-ttu-id="e0c5b-127">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="e0c5b-127">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="e0c5b-128">返回最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-128">Return the last error.</span></span>  <br/> |<span data-ttu-id="e0c5b-129">一般</span><span class="sxs-lookup"><span data-stu-id="e0c5b-129">Normal</span></span>  <br/> |
|<span data-ttu-id="e0c5b-130">其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法</span><span class="sxs-lookup"><span data-stu-id="e0c5b-130">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="e0c5b-131">实现如 [IPersistMessage ： IUnknown 接口的文档](ipersistmessageiunknown.md) 中所述。</span><span class="sxs-lookup"><span data-stu-id="e0c5b-131">Implement as described in the documentation for the [IPersistMessage : IUnknown](ipersistmessageiunknown.md) interface.</span></span>  <br/> |<span data-ttu-id="e0c5b-132">一般</span><span class="sxs-lookup"><span data-stu-id="e0c5b-132">Normal</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e0c5b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0c5b-133">See also</span></span>



[<span data-ttu-id="e0c5b-134">表单状态</span><span class="sxs-lookup"><span data-stu-id="e0c5b-134">Form States</span></span>](form-states.md)

