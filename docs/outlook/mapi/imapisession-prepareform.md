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
# <a name="imapisessionprepareform"></a><span data-ttu-id="50f1d-103">IMAPISession::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="50f1d-103">IMAPISession::PrepareForm</span></span>

  
  
<span data-ttu-id="50f1d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="50f1d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="50f1d-105">创建[IMAPISession:: ShowForm](imapisession-showform.md)方法用于访问邮件的数字标记。</span><span class="sxs-lookup"><span data-stu-id="50f1d-105">Creates a numeric token that the [IMAPISession::ShowForm](imapisession-showform.md) method uses to access a message.</span></span> 
  
```cpp
HRESULT PrepareForm(
  LPCIID lpInterface,
  LPMESSAGE lpMessage,
  ULONG FAR * lpulMessageToken
);
```

## <a name="parameters"></a><span data-ttu-id="50f1d-106">参数</span><span class="sxs-lookup"><span data-stu-id="50f1d-106">Parameters</span></span>

 <span data-ttu-id="50f1d-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="50f1d-107">_lpInterface_</span></span>
  
> <span data-ttu-id="50f1d-108">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问邮件的接口。</span><span class="sxs-lookup"><span data-stu-id="50f1d-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the message.</span></span> <span data-ttu-id="50f1d-109">在使用的标准接口或[IMessage](imessageimapiprop.md)中传递**null**结果。</span><span class="sxs-lookup"><span data-stu-id="50f1d-109">Passing **null** results in the standard interface, or [IMessage](imessageimapiprop.md), being used.</span></span> <span data-ttu-id="50f1d-110">_lpInterface_参数必须为**null**或 IID_IMessage。</span><span class="sxs-lookup"><span data-stu-id="50f1d-110">The  _lpInterface_ parameter must be **null** or IID_IMessage.</span></span> 
    
 <span data-ttu-id="50f1d-111">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="50f1d-111">_lpMessage_</span></span>
  
> <span data-ttu-id="50f1d-112">实时指向要在表单中显示的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="50f1d-112">[in] A pointer to the message to be displayed in the form.</span></span>
    
 <span data-ttu-id="50f1d-113">_lpulMessageToken_</span><span class="sxs-lookup"><span data-stu-id="50f1d-113">_lpulMessageToken_</span></span>
  
> <span data-ttu-id="50f1d-114">排除指向邮件令牌的指针, **IMAPISession:: ShowForm**方法使用该指针访问_lpMessage_指向的邮件。</span><span class="sxs-lookup"><span data-stu-id="50f1d-114">[out] A pointer to a message token, which is used by the **IMAPISession::ShowForm** method to access the message pointed to by  _lpMessage_.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="50f1d-115">返回值</span><span class="sxs-lookup"><span data-stu-id="50f1d-115">Return value</span></span>

<span data-ttu-id="50f1d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="50f1d-116">S_OK</span></span> 
  
> <span data-ttu-id="50f1d-117">表单准备成功。</span><span class="sxs-lookup"><span data-stu-id="50f1d-117">The form preparation was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="50f1d-118">注解</span><span class="sxs-lookup"><span data-stu-id="50f1d-118">Remarks</span></span>

<span data-ttu-id="50f1d-119">**IMAPISession::P repareform**方法为_lpMessage_参数所指向的邮件创建一个邮件令牌, 并调用邮件的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="50f1d-119">The **IMAPISession::PrepareForm** method creates a message token for the message pointed to by the  _lpMessage_ parameter and calls the message's [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method.</span></span> <span data-ttu-id="50f1d-120">此令牌在_ulMessageToken_参数中传递到**IMAPISession:: ShowForm**。</span><span class="sxs-lookup"><span data-stu-id="50f1d-120">This token is passed in the  _ulMessageToken_ parameter to **IMAPISession::ShowForm**.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="50f1d-121">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="50f1d-121">Notes to callers</span></span>

<span data-ttu-id="50f1d-122">如果对**PrepareForm**的调用成功, 请通过在调用**ShowForm**之前调用其[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法来释放_lpMessage_所指向的消息。</span><span class="sxs-lookup"><span data-stu-id="50f1d-122">If the call to **PrepareForm** succeeds, release the message pointed to by  _lpMessage_ by calling its [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method before you call **ShowForm**.</span></span> <span data-ttu-id="50f1d-123">调用**ShowForm**之前无法释放邮件可能会导致内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="50f1d-123">Failure to release the message before you call **ShowForm** can cause memory leaks.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="50f1d-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="50f1d-124">MFCMAPI reference</span></span>

<span data-ttu-id="50f1d-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="50f1d-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="50f1d-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="50f1d-126">**File**</span></span>|<span data-ttu-id="50f1d-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="50f1d-127">**Function**</span></span>|<span data-ttu-id="50f1d-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="50f1d-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="50f1d-129">MAPIFormFunctions</span><span class="sxs-lookup"><span data-stu-id="50f1d-129">MAPIFormFunctions.cpp</span></span>  <br/> |<span data-ttu-id="50f1d-130">OpenMessageModal</span><span class="sxs-lookup"><span data-stu-id="50f1d-130">OpenMessageModal</span></span>  <br/> |<span data-ttu-id="50f1d-131">MFCMAPI 使用**IMAPISession::P repareform**方法以及**IMAPISession:: ShowForm**在模式窗体中显示消息。</span><span class="sxs-lookup"><span data-stu-id="50f1d-131">MFCMAPI uses the **IMAPISession::PrepareForm** method, along with **IMAPISession::ShowForm**, to display a message in a modal form.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="50f1d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50f1d-132">See also</span></span>



[<span data-ttu-id="50f1d-133">IMAPISession::ShowForm</span><span class="sxs-lookup"><span data-stu-id="50f1d-133">IMAPISession::ShowForm</span></span>](imapisession-showform.md)
  
[<span data-ttu-id="50f1d-134">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="50f1d-134">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="50f1d-135">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="50f1d-135">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

