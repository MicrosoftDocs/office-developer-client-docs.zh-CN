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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fa3f1d6339000fcc53e0ee22dafec4362e65ca7f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309616"
---
# <a name="ipersistmessagesave"></a><span data-ttu-id="f9ec0-103">IPersistMessage::Save</span><span class="sxs-lookup"><span data-stu-id="f9ec0-103">IPersistMessage::Save</span></span>

  
  
<span data-ttu-id="f9ec0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f9ec0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f9ec0-105">将修改后的窗体保存回已加载或创建该窗体的邮件。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-105">Saves a revised form back to the message from which it was loaded or created.</span></span>
  
```cpp
HRESULT Save(
  LPMESSAGE pMessage,
  ULONG fSameAsLoad
);
```

## <a name="parameters"></a><span data-ttu-id="f9ec0-106">参数</span><span class="sxs-lookup"><span data-stu-id="f9ec0-106">Parameters</span></span>

 <span data-ttu-id="f9ec0-107">_pMessage_</span><span class="sxs-lookup"><span data-stu-id="f9ec0-107">_pMessage_</span></span>
  
> <span data-ttu-id="f9ec0-108">[in]指向消息的指针。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-108">[in] A pointer to the message.</span></span>
    
 <span data-ttu-id="f9ec0-109">_fSameAsLoad_</span><span class="sxs-lookup"><span data-stu-id="f9ec0-109">_fSameAsLoad_</span></span>
  
> <span data-ttu-id="f9ec0-110">[in]若要指示  _pMessage_ 指向的邮件是加载或创建表单的邮件，则其为 TRUE;否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-110">[in] TRUE to indicate that the message pointed to by  _pMessage_ is the message from which the form was loaded or created; otherwise, FALSE.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f9ec0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="f9ec0-111">Return value</span></span>

<span data-ttu-id="f9ec0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f9ec0-112">S_OK</span></span> 
  
> <span data-ttu-id="f9ec0-113">已成功保存表单。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-113">The form was successfully saved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f9ec0-114">备注</span><span class="sxs-lookup"><span data-stu-id="f9ec0-114">Remarks</span></span>

<span data-ttu-id="f9ec0-115">表单查看器调用 **IPersistMessage：：Save** 方法，将修改后的表单保存回加载或创建表单的邮件。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-115">Form viewers call the **IPersistMessage::Save** method to save a revised form back to the message from which it was loaded or created.</span></span> 
  
 <span data-ttu-id="f9ec0-116">**只有在** 表单的状态为"正常"时，才应 [调用 Save。](normal-state.md)</span><span class="sxs-lookup"><span data-stu-id="f9ec0-116">**Save** should only be called when the form is in its [Normal](normal-state.md) state.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="f9ec0-117">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="f9ec0-117">Notes to implementers</span></span>

<span data-ttu-id="f9ec0-118">不提交保存的更改;由调用方提交更改。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-118">Do not commit the saved changes; it is up to the caller to commit the changes.</span></span> <span data-ttu-id="f9ec0-119">从不对属于窗体邮件的属性进行更改，Save 调用 **期间** 除外。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-119">Never make changes to the properties that belong to the form's message except during the **Save** call.</span></span> 
  
<span data-ttu-id="f9ec0-120">如果  _fSameAsLoad_ 设置为 TRUE，您可以将更改保存到表单的现有邮件中。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-120">If  _fSameAsLoad_ is set to TRUE, you can save the changes to the form's existing message.</span></span> <span data-ttu-id="f9ec0-121">如果  _fSameAsLoad_ 设置为 FALSE，则在执行保存之前，必须将原始邮件的所有属性复制到  _pMessage_ 指向的邮件中。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-121">If  _fSameAsLoad_ is set to FALSE, you must copy all of the properties from the original message into the message pointed to by  _pMessage_ before performing the save.</span></span> <span data-ttu-id="f9ec0-122">使用原始邮件的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法复制属性。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-122">Use the original message's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the properties.</span></span> 
  
<span data-ttu-id="f9ec0-123">复制所有属性后，输入 [NoScribble](noscribble-state.md) 状态。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-123">When all of the properties have been copied, enter the [NoScribble](noscribble-state.md) state.</span></span> <span data-ttu-id="f9ec0-124">如果未发生错误，则返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-124">If no errors occur, return S_OK.</span></span> <span data-ttu-id="f9ec0-125">否则，从失败操作返回错误。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-125">Otherwise, return the error from the failed action.</span></span> 
  
<span data-ttu-id="f9ec0-126">如果 **当窗体** 位于除 Normal 外的任何状态时调用 Save，则返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-126">If **Save** is called when the form is in any state other than Normal, return E_UNEXPECTED.</span></span> 
  
<span data-ttu-id="f9ec0-127">有关保存存储对象的信息，请参阅 [有关 IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx) 方法的文档。</span><span class="sxs-lookup"><span data-stu-id="f9ec0-127">For more information about saving storage objects, see the documentation on the [IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx) methods.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f9ec0-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9ec0-128">See also</span></span>



[<span data-ttu-id="f9ec0-129">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f9ec0-129">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)


[<span data-ttu-id="f9ec0-130">表单状态</span><span class="sxs-lookup"><span data-stu-id="f9ec0-130">Form States</span></span>](form-states.md)

