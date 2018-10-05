---
title: IPersistMessageSave
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.Save
api_type:
- COM
ms.assetid: 17875c13-f55b-4538-ac6f-c020281c3175
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fa3f1d6339000fcc53e0ee22dafec4362e65ca7f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397154"
---
# <a name="ipersistmessagesave"></a><span data-ttu-id="2815f-103">IPersistMessage::Save</span><span class="sxs-lookup"><span data-stu-id="2815f-103">IPersistMessage::Save</span></span>

  
  
<span data-ttu-id="2815f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2815f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2815f-105">将修订后的表单保存回其已加载或创建的邮件。</span><span class="sxs-lookup"><span data-stu-id="2815f-105">Saves a revised form back to the message from which it was loaded or created.</span></span>
  
```cpp
HRESULT Save(
  LPMESSAGE pMessage,
  ULONG fSameAsLoad
);
```

## <a name="parameters"></a><span data-ttu-id="2815f-106">参数</span><span class="sxs-lookup"><span data-stu-id="2815f-106">Parameters</span></span>

 <span data-ttu-id="2815f-107">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="2815f-107">_pMessage_</span></span>
  
> <span data-ttu-id="2815f-108">[in]指向邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="2815f-108">[in] A pointer to the message.</span></span>
    
 <span data-ttu-id="2815f-109">_fSameAsLoad_</span><span class="sxs-lookup"><span data-stu-id="2815f-109">_fSameAsLoad_</span></span>
  
> <span data-ttu-id="2815f-110">[in]若要指示邮件指向_pMessage_是从中加载或创建; 窗体的邮件否则为返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="2815f-110">[in] TRUE to indicate that the message pointed to by  _pMessage_ is the message from which the form was loaded or created; otherwise, FALSE.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="2815f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="2815f-111">Return value</span></span>

<span data-ttu-id="2815f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2815f-112">S_OK</span></span> 
  
> <span data-ttu-id="2815f-113">已成功保存表单。</span><span class="sxs-lookup"><span data-stu-id="2815f-113">The form was successfully saved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2815f-114">说明</span><span class="sxs-lookup"><span data-stu-id="2815f-114">Remarks</span></span>

<span data-ttu-id="2815f-115">表单查看器调用**IPersistMessage::Save**方法将修订后的表单保存回其已加载或创建的邮件。</span><span class="sxs-lookup"><span data-stu-id="2815f-115">Form viewers call the **IPersistMessage::Save** method to save a revised form back to the message from which it was loaded or created.</span></span> 
  
 <span data-ttu-id="2815f-116">在窗体以[正常](normal-state.md)状态时应仅调用**保存**。</span><span class="sxs-lookup"><span data-stu-id="2815f-116">**Save** should only be called when the form is in its [Normal](normal-state.md) state.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2815f-117">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="2815f-117">Notes to implementers</span></span>

<span data-ttu-id="2815f-118">未提交的已保存的更改;由呼叫者进行提交的更改。</span><span class="sxs-lookup"><span data-stu-id="2815f-118">Do not commit the saved changes; it is up to the caller to commit the changes.</span></span> <span data-ttu-id="2815f-119">从不对窗体的邮件，但属于**保存**呼叫期间的属性进行更改。</span><span class="sxs-lookup"><span data-stu-id="2815f-119">Never make changes to the properties that belong to the form's message except during the **Save** call.</span></span> 
  
<span data-ttu-id="2815f-120">如果_fSameAsLoad_设置为 TRUE，您可以将所做的更改保存到窗体的现有邮件。</span><span class="sxs-lookup"><span data-stu-id="2815f-120">If  _fSameAsLoad_ is set to TRUE, you can save the changes to the form's existing message.</span></span> <span data-ttu-id="2815f-121">如果_fSameAsLoad_设置为 FALSE，则必须向邮件所指的_pMessage_执行保存之前从原始邮件复制的所有属性。</span><span class="sxs-lookup"><span data-stu-id="2815f-121">If  _fSameAsLoad_ is set to FALSE, you must copy all of the properties from the original message into the message pointed to by  _pMessage_ before performing the save.</span></span> <span data-ttu-id="2815f-122">使用原始消息的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法复制的属性。</span><span class="sxs-lookup"><span data-stu-id="2815f-122">Use the original message's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the properties.</span></span> 
  
<span data-ttu-id="2815f-123">复制的所有属性，都输入[NoScribble](noscribble-state.md)状态。</span><span class="sxs-lookup"><span data-stu-id="2815f-123">When all of the properties have been copied, enter the [NoScribble](noscribble-state.md) state.</span></span> <span data-ttu-id="2815f-124">如果没有错误，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="2815f-124">If no errors occur, return S_OK.</span></span> <span data-ttu-id="2815f-125">从失败的操作，否则，返回错误。</span><span class="sxs-lookup"><span data-stu-id="2815f-125">Otherwise, return the error from the failed action.</span></span> 
  
<span data-ttu-id="2815f-126">如果**保存**窗体处于普通之外的任何状态时调用，，返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="2815f-126">If **Save** is called when the form is in any state other than Normal, return E_UNEXPECTED.</span></span> 
  
<span data-ttu-id="2815f-127">有关保存存储对象的详细信息，请参阅[IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx)方法的文档。</span><span class="sxs-lookup"><span data-stu-id="2815f-127">For more information about saving storage objects, see the documentation on the [IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx) methods.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2815f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2815f-128">See also</span></span>



[<span data-ttu-id="2815f-129">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2815f-129">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)


[<span data-ttu-id="2815f-130">表单状态</span><span class="sxs-lookup"><span data-stu-id="2815f-130">Form States</span></span>](form-states.md)

