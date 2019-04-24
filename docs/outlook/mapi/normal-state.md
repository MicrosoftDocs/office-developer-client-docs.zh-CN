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
# <a name="normal-state"></a><span data-ttu-id="1d3a7-103">正常状态</span><span class="sxs-lookup"><span data-stu-id="1d3a7-103">Normal State</span></span>

  
  
<span data-ttu-id="1d3a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1d3a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1d3a7-105">正常状态是 form 对象的大部分时间, 等待客户端应用程序启动操作 (如保存更改或关闭窗体)。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-105">The Normal state is where the form object spends most of its time, waiting for client applications to initiate an action such as saving changes or closing the form.</span></span> <span data-ttu-id="1d3a7-106">下表介绍了允许从正常状态进行的转换。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-106">The following table describes allowed transitions from the Normal state.</span></span>
  
|<span data-ttu-id="1d3a7-107">**IPersistMessage 方法**</span><span class="sxs-lookup"><span data-stu-id="1d3a7-107">**IPersistMessage method**</span></span>|<span data-ttu-id="1d3a7-108">**Action**</span><span class="sxs-lookup"><span data-stu-id="1d3a7-108">**Action**</span></span>|<span data-ttu-id="1d3a7-109">**新状态**</span><span class="sxs-lookup"><span data-stu-id="1d3a7-109">**New state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d3a7-110">[IPersistMessage:: Save](ipersistmessage-save.md)(_pMessage = =_ NULL, _fSameAsLoad = =_ TRUE)</span><span class="sxs-lookup"><span data-stu-id="1d3a7-110">[IPersistMessage::Save](ipersistmessage-save.md)(_pMessage ==_ NULL,  _fSameAsLoad ==_ TRUE)</span></span>  <br/> <span data-ttu-id="1d3a7-111">- 或 -</span><span class="sxs-lookup"><span data-stu-id="1d3a7-111">-or-</span></span>  <br/> <span data-ttu-id="1d3a7-112">**IPersistMessage:: Save**(_pMessage! =_ NULL, _fSameAsLoad = =_ FALSE)</span><span class="sxs-lookup"><span data-stu-id="1d3a7-112">**IPersistMessage::Save**(_pMessage !=_ NULL,  _fSameAsLoad ==_ FALSE)</span></span>  <br/> |<span data-ttu-id="1d3a7-113">以递归方式保存所有已修改的嵌入 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-113">Recursively save any embedded OLE objects that have been modified.</span></span> <span data-ttu-id="1d3a7-114">将邮件数据保存回 message 对象。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-114">Save message data back to the message object.</span></span> <span data-ttu-id="1d3a7-115">存储_fSameAsLoad_标志以供以后在[NoScribble](noscribble-state.md)状态中使用。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-115">Store the  _fSameAsLoad_ flag for later use in the [NoScribble](noscribble-state.md) state.</span></span>  <br/> |<span data-ttu-id="1d3a7-116">NoScribble</span><span class="sxs-lookup"><span data-stu-id="1d3a7-116">NoScribble</span></span>  <br/> |
|<span data-ttu-id="1d3a7-117">**IPersistMessage:: Save**(_pMessage! =_ NULL, _fSameAsLoad = =_ TRUE)</span><span class="sxs-lookup"><span data-stu-id="1d3a7-117">**IPersistMessage::Save**(_pMessage !=_ NULL,  _fSameAsLoad ==_ TRUE)</span></span>  <br/> |<span data-ttu-id="1d3a7-118">这与前一种情况相同, 不同之处在于此**保存**调用在内存不足的情况下使用, 如果内存不足, 则不能失败。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-118">This is the same as the previous case, except that this **Save** call is used in low-memory situations and must not fail for lack of memory.</span></span>  <br/> |<span data-ttu-id="1d3a7-119">NoScribble</span><span class="sxs-lookup"><span data-stu-id="1d3a7-119">NoScribble</span></span>  <br/> |
|[<span data-ttu-id="1d3a7-120">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="1d3a7-120">IPersistMessage::HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md) <br/> |<span data-ttu-id="1d3a7-121">对嵌入的邮件或 ole [IPersistStorage:: HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx)方法, 对嵌入的 ole 对象以递归方式调用**HandsOffMessage**方法。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-121">Recursively invoke the **HandsOffMessage** method on embedded messages or the OLE [IPersistStorage::HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx) method on embedded OLE objects.</span></span> <span data-ttu-id="1d3a7-122">释放邮件对象和任何嵌入的邮件或对象。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-122">Release the message object and any embedded messages or objects.</span></span>  <br/> |[<span data-ttu-id="1d3a7-123">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="1d3a7-123">HandsOffFromNormal</span></span>](handsofffromnormal-state.md) <br/> |
|<span data-ttu-id="1d3a7-124">[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md), [IPersistMessage:: InitNew](ipersistmessage-initnew.md)或[IPersistMessage:: Load](ipersistmessage-load.md)</span><span class="sxs-lookup"><span data-stu-id="1d3a7-124">[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md), [IPersistMessage::InitNew](ipersistmessage-initnew.md) or [IPersistMessage::Load](ipersistmessage-load.md)</span></span> <br/> |<span data-ttu-id="1d3a7-125">将上一个错误设置为并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-125">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="1d3a7-126">一般</span><span class="sxs-lookup"><span data-stu-id="1d3a7-126">Normal</span></span>  <br/> |
|[<span data-ttu-id="1d3a7-127">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="1d3a7-127">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="1d3a7-128">返回上一个错误。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-128">Return the last error.</span></span>  <br/> |<span data-ttu-id="1d3a7-129">一般</span><span class="sxs-lookup"><span data-stu-id="1d3a7-129">Normal</span></span>  <br/> |
|<span data-ttu-id="1d3a7-130">其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口的方法</span><span class="sxs-lookup"><span data-stu-id="1d3a7-130">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="1d3a7-131">按照[IPersistMessage: IUnknown](ipersistmessageiunknown.md)接口的文档中所述实现。</span><span class="sxs-lookup"><span data-stu-id="1d3a7-131">Implement as described in the documentation for the [IPersistMessage : IUnknown](ipersistmessageiunknown.md) interface.</span></span>  <br/> |<span data-ttu-id="1d3a7-132">一般</span><span class="sxs-lookup"><span data-stu-id="1d3a7-132">Normal</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1d3a7-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d3a7-133">See also</span></span>



[<span data-ttu-id="1d3a7-134">表单状态</span><span class="sxs-lookup"><span data-stu-id="1d3a7-134">Form States</span></span>](form-states.md)

