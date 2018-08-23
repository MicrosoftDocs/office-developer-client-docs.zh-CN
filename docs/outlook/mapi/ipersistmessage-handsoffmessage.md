---
title: IPersistMessageHandsOffMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.HandsOffMessage
api_type:
- COM
ms.assetid: 0e56b21d-0a2e-4fe6-83f4-c9daab2f3055
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2cd4c86dc45bca85632a3fadc9023c9ad25cfa37
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583027"
---
# <a name="ipersistmessagehandsoffmessage"></a><span data-ttu-id="36a03-103">IPersistMessage::HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="36a03-103">IPersistMessage::HandsOffMessage</span></span>

  
  
<span data-ttu-id="36a03-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="36a03-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="36a03-105">使窗体释放其当前邮件。</span><span class="sxs-lookup"><span data-stu-id="36a03-105">Causes the form to release its current message.</span></span>
  
```cpp
HRESULT HandsOffMessage( void );
```

## <a name="parameters"></a><span data-ttu-id="36a03-106">参数</span><span class="sxs-lookup"><span data-stu-id="36a03-106">Parameters</span></span>

<span data-ttu-id="36a03-107">无</span><span class="sxs-lookup"><span data-stu-id="36a03-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="36a03-108">返回值</span><span class="sxs-lookup"><span data-stu-id="36a03-108">Return value</span></span>

<span data-ttu-id="36a03-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="36a03-109">S_OK</span></span> 
  
> <span data-ttu-id="36a03-110">邮件已成功发布。</span><span class="sxs-lookup"><span data-stu-id="36a03-110">The message was successfully released.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="36a03-111">注解</span><span class="sxs-lookup"><span data-stu-id="36a03-111">Remarks</span></span>

<span data-ttu-id="36a03-112">窗体过渡到两个 HandsOff 状态：</span><span class="sxs-lookup"><span data-stu-id="36a03-112">Forms transition into two HandsOff states:</span></span>
  
- [<span data-ttu-id="36a03-113">HandsOffAfterSave</span><span class="sxs-lookup"><span data-stu-id="36a03-113">HandsOffAfterSave</span></span>](handsoffaftersave-state.md)
    
- [<span data-ttu-id="36a03-114">HandsOffFromNormal</span><span class="sxs-lookup"><span data-stu-id="36a03-114">HandsOffFromNormal</span></span>](handsofffromnormal-state.md)
    
<span data-ttu-id="36a03-115">当窗体处于以下状态之一时，它是被永久存储的过程。</span><span class="sxs-lookup"><span data-stu-id="36a03-115">When a form is in either of these states, it is in the process of being stored permanently.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="36a03-116">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="36a03-116">Notes to implementers</span></span>

<span data-ttu-id="36a03-117">当窗体处于[普通](normal-state.md)或[NoScribble](noscribble-state.md)状态时，窗体查看器调用**IPersistMessage::HandsOffMessage**方法时，对每封邮件以递归方式调用**HandsOffMessage**嵌入在当前消息和[IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d.aspx)当前消息中嵌入在每个 OLE 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="36a03-117">When a form viewer calls the **IPersistMessage::HandsOffMessage** method while your form is in the [Normal](normal-state.md) or [NoScribble](noscribble-state.md) state, recursively call **HandsOffMessage** on each message embedded in the current message and the [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d.aspx) method on each OLE object embedded in the current message.</span></span> <span data-ttu-id="36a03-118">然后释放所有嵌入的邮件当前消息和 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="36a03-118">Then release the current message and all embedded messages and OLE objects.</span></span> <span data-ttu-id="36a03-119">如果您的窗体处于正常状态转换为 HandsOffFromNormal 状态。</span><span class="sxs-lookup"><span data-stu-id="36a03-119">If your form was in the Normal state, transition to the HandsOffFromNormal state.</span></span> <span data-ttu-id="36a03-120">如果您的窗体 NoScribble 状态，转换为 HandsOffAfterSave 状态。</span><span class="sxs-lookup"><span data-stu-id="36a03-120">If your form was in the NoScribble state, transition to the HandsOffAfterSave state.</span></span> <span data-ttu-id="36a03-121">成功转换之后, 调用消息的[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法，并返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="36a03-121">After a successful transition, call the message's [IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method and return S_OK.</span></span> 
  
<span data-ttu-id="36a03-122">当窗体查看器调用**HandsOffMessage** HandsOff 状态的某一窗体时，返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="36a03-122">When a form viewer calls **HandsOffMessage** while your form is in either of the HandsOff states, return E_UNEXPECTED.</span></span> 
  
<span data-ttu-id="36a03-123">有关窗体的不同状态的详细信息，请参阅[窗体状态](form-states.md)。</span><span class="sxs-lookup"><span data-stu-id="36a03-123">For more information about the different states of a form, see [Form States](form-states.md).</span></span> <span data-ttu-id="36a03-124">有关如何使用存储对象的 HandsOff 状态的详细信息，请参阅[IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="36a03-124">For more information about how to work with the HandsOff state of storage objects, see the [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d.aspx) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="36a03-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36a03-125">See also</span></span>



[<span data-ttu-id="36a03-126">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="36a03-126">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)


[<span data-ttu-id="36a03-127">表单状态</span><span class="sxs-lookup"><span data-stu-id="36a03-127">Form States</span></span>](form-states.md)

