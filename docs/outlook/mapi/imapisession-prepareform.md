---
title: IMAPISessionPrepareForm
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.PrepareForm
api_type:
- COM
ms.assetid: 98c0eab1-fd7e-46c3-8619-ccd6dc7cf8f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3d8b1901123743b25b5bb9df174b297398c953b8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335760"
---
# <a name="imapisessionprepareform"></a><span data-ttu-id="29aff-103">IMAPISession::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="29aff-103">IMAPISession::PrepareForm</span></span>

  
  
<span data-ttu-id="29aff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29aff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29aff-105">创建 [IMAPISession：：ShowForm](imapisession-showform.md) 方法用于访问消息的数字令牌。</span><span class="sxs-lookup"><span data-stu-id="29aff-105">Creates a numeric token that the [IMAPISession::ShowForm](imapisession-showform.md) method uses to access a message.</span></span> 
  
```cpp
HRESULT PrepareForm(
  LPCIID lpInterface,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMessageToken
);
```

## <a name="parameters"></a><span data-ttu-id="29aff-106">参数</span><span class="sxs-lookup"><span data-stu-id="29aff-106">Parameters</span></span>

 <span data-ttu-id="29aff-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="29aff-107">_lpInterface_</span></span>
  
> <span data-ttu-id="29aff-108">[in]一个指向接口标识符 (IID) 表示用于访问邮件的接口的 IID 标识符。</span><span class="sxs-lookup"><span data-stu-id="29aff-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the message.</span></span> <span data-ttu-id="29aff-109">传递 **null** 会导致使用标准接口或 [IMessage。](imessageimapiprop.md)</span><span class="sxs-lookup"><span data-stu-id="29aff-109">Passing **null** results in the standard interface, or [IMessage](imessageimapiprop.md), being used.</span></span> <span data-ttu-id="29aff-110">_lpInterface_ 参数必须为空 **或** IID_IMessage。</span><span class="sxs-lookup"><span data-stu-id="29aff-110">The  _lpInterface_ parameter must be **null** or IID_IMessage.</span></span> 
    
 <span data-ttu-id="29aff-111">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="29aff-111">_lpMessage_</span></span>
  
> <span data-ttu-id="29aff-112">[in]指向要显示在窗体中的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="29aff-112">[in] A pointer to the message to be displayed in the form.</span></span>
    
 <span data-ttu-id="29aff-113">_lpulMessageToken_</span><span class="sxs-lookup"><span data-stu-id="29aff-113">_lpulMessageToken_</span></span>
  
> <span data-ttu-id="29aff-114">[out]指向消息令牌的指针 **，IMAPISession：：ShowForm** 方法使用它访问  _lpMessage 指向的消息_。</span><span class="sxs-lookup"><span data-stu-id="29aff-114">[out] A pointer to a message token, which is used by the **IMAPISession::ShowForm** method to access the message pointed to by  _lpMessage_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="29aff-115">返回值</span><span class="sxs-lookup"><span data-stu-id="29aff-115">Return value</span></span>

<span data-ttu-id="29aff-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="29aff-116">S_OK</span></span> 
  
> <span data-ttu-id="29aff-117">表单准备成功。</span><span class="sxs-lookup"><span data-stu-id="29aff-117">The form preparation was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="29aff-118">备注</span><span class="sxs-lookup"><span data-stu-id="29aff-118">Remarks</span></span>

<span data-ttu-id="29aff-119">**IMAPISession：:P repareForm** 方法为 _lpMessage_ 参数指向的消息创建消息令牌，并调用消息的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="29aff-119">The **IMAPISession::PrepareForm** method creates a message token for the message pointed to by the  _lpMessage_ parameter and calls the message's [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method.</span></span> <span data-ttu-id="29aff-120">此令牌在  _ulMessageToken_ 参数中传递到 **IMAPISession：：ShowForm**。</span><span class="sxs-lookup"><span data-stu-id="29aff-120">This token is passed in the  _ulMessageToken_ parameter to **IMAPISession::ShowForm**.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="29aff-121">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="29aff-121">Notes to callers</span></span>

<span data-ttu-id="29aff-122">如果 **对 PrepareForm** 的调用成功，在调用 **ShowForm** 之前，通过调用其 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法释放 _lpMessage_ 指向的消息。</span><span class="sxs-lookup"><span data-stu-id="29aff-122">If the call to **PrepareForm** succeeds, release the message pointed to by  _lpMessage_ by calling its [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method before you call **ShowForm**.</span></span> <span data-ttu-id="29aff-123">调用 **ShowForm** 之前释放消息失败可能会导致内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="29aff-123">Failure to release the message before you call **ShowForm** can cause memory leaks.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="29aff-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="29aff-124">MFCMAPI reference</span></span>

<span data-ttu-id="29aff-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="29aff-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="29aff-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="29aff-126">**File**</span></span>|<span data-ttu-id="29aff-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="29aff-127">**Function**</span></span>|<span data-ttu-id="29aff-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="29aff-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="29aff-129">MAPIFormFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="29aff-129">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="29aff-130">OpenMessageModal</span><span class="sxs-lookup"><span data-stu-id="29aff-130">OpenMessageModal</span></span>  <br/> |<span data-ttu-id="29aff-131">MFCMAPI 使用 **IMAPISession：:P repareForm** 方法以及 **IMAPISession：：ShowForm** 在模式表单中显示消息。</span><span class="sxs-lookup"><span data-stu-id="29aff-131">MFCMAPI uses the **IMAPISession::PrepareForm** method, along with **IMAPISession::ShowForm**, to display a message in a modal form.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="29aff-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29aff-132">See also</span></span>



[<span data-ttu-id="29aff-133">IMAPISession::ShowForm</span><span class="sxs-lookup"><span data-stu-id="29aff-133">IMAPISession::ShowForm</span></span>](imapisession-showform.md)
  
[<span data-ttu-id="29aff-134">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="29aff-134">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="29aff-135">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="29aff-135">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

