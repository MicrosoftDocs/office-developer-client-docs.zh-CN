---
title: IMAPIMessageSiteMoveMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.MoveMessage
api_type:
- COM
ms.assetid: cd4d7b11-fad0-4f05-a99e-9567abcab45c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0451d8635848705ef912b9a575d6390898251f4f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775466"
---
# <a name="imapimessagesitemovemessage"></a><span data-ttu-id="22c8a-103">IMAPIMessageSite::MoveMessage</span><span class="sxs-lookup"><span data-stu-id="22c8a-103">IMAPIMessageSite::MoveMessage</span></span>

  
  
<span data-ttu-id="22c8a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="22c8a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="22c8a-105">将当前邮件移动到文件夹中。</span><span class="sxs-lookup"><span data-stu-id="22c8a-105">Moves the current message to a folder.</span></span>
  
```cpp
HRESULT MoveMessage(
  LPFOLDER pFolderDestination,
  LPMAPIVIEWCONTEXT pViewContext,
  LPCRECT prcPosRect
);
```

## <a name="parameters"></a><span data-ttu-id="22c8a-106">参数</span><span class="sxs-lookup"><span data-stu-id="22c8a-106">Parameters</span></span>

 <span data-ttu-id="22c8a-107">_pFolderDestination_</span><span class="sxs-lookup"><span data-stu-id="22c8a-107">_pFolderDestination_</span></span>
  
> <span data-ttu-id="22c8a-108">[in]一个指向邮件将被移动其中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="22c8a-108">[in] A pointer to the folder where the message is to be moved.</span></span>
    
 <span data-ttu-id="22c8a-109">_pViewContext_</span><span class="sxs-lookup"><span data-stu-id="22c8a-109">_pViewContext_</span></span>
  
> <span data-ttu-id="22c8a-110">[in]指向视图上下文对象的指针。</span><span class="sxs-lookup"><span data-stu-id="22c8a-110">[in] A pointer to a view context object.</span></span>
    
 <span data-ttu-id="22c8a-111">_prcPosRect_</span><span class="sxs-lookup"><span data-stu-id="22c8a-111">_prcPosRect_</span></span>
  
> <span data-ttu-id="22c8a-112">[in]指向[矩形](http://msdn.microsoft.com/en-us/library/dd162897%28VS.85%29.aspx)结构，其中包含当前表单的窗口的大小和位置的指针。</span><span class="sxs-lookup"><span data-stu-id="22c8a-112">[in] A pointer to a [RECT](http://msdn.microsoft.com/en-us/library/dd162897%28VS.85%29.aspx) structure that contains the current form's window size and position.</span></span> <span data-ttu-id="22c8a-113">显示的下一个窗体也使用此窗口矩形。</span><span class="sxs-lookup"><span data-stu-id="22c8a-113">The next form displayed also uses this window rectangle.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="22c8a-114">返回值</span><span class="sxs-lookup"><span data-stu-id="22c8a-114">Return value</span></span>

<span data-ttu-id="22c8a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="22c8a-115">S_OK</span></span> 
  
> <span data-ttu-id="22c8a-116">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="22c8a-116">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="22c8a-117">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="22c8a-117">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="22c8a-118">该操作不受此消息网站。</span><span class="sxs-lookup"><span data-stu-id="22c8a-118">The operation is not supported by this message site.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="22c8a-119">说明</span><span class="sxs-lookup"><span data-stu-id="22c8a-119">Remarks</span></span>

<span data-ttu-id="22c8a-120">表单对象调用**IMAPIMessageSite::MoveMessage**方法将当前邮件移至新文件夹。</span><span class="sxs-lookup"><span data-stu-id="22c8a-120">Form objects call the **IMAPIMessageSite::MoveMessage** method to move the current message to a new folder.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="22c8a-121">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="22c8a-121">Notes to implementers</span></span>

<span data-ttu-id="22c8a-122">表单查看器的实现**MoveMessage**必须调用传递 VCDIR_MOVE 标志，实际上将邮件移至新文件夹前的[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)方法。</span><span class="sxs-lookup"><span data-stu-id="22c8a-122">A form viewer's implementation of **MoveMessage** must call the [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) method, passing the VCDIR_MOVE flag, before actually moving the message to a new folder.</span></span> <span data-ttu-id="22c8a-123">若要获取使用窗体的窗口的**矩形**结构，请调用 Windows [GetWindowRect](http://msdn.microsoft.com/en-us/library/ms633519)函数。</span><span class="sxs-lookup"><span data-stu-id="22c8a-123">To obtain the **RECT** structure used by a form's window, call the Windows [GetWindowRect](http://msdn.microsoft.com/en-us/library/ms633519) function.</span></span> 
  
<span data-ttu-id="22c8a-124">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="22c8a-124">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="22c8a-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="22c8a-125">Notes to callers</span></span>

<span data-ttu-id="22c8a-126">**MoveMessage**返回时，以下窗体必须检查当前消息，然后关闭本身，如果不存在。</span><span class="sxs-lookup"><span data-stu-id="22c8a-126">Following the return of **MoveMessage**, forms must check for a current message and then dismiss themselves if none exists.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="22c8a-127">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="22c8a-127">MFCMAPI reference</span></span>

<span data-ttu-id="22c8a-128">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="22c8a-128">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="22c8a-129">**文件**</span><span class="sxs-lookup"><span data-stu-id="22c8a-129">**File**</span></span>|<span data-ttu-id="22c8a-130">**函数**</span><span class="sxs-lookup"><span data-stu-id="22c8a-130">**Function**</span></span>|<span data-ttu-id="22c8a-131">**Comment**</span><span class="sxs-lookup"><span data-stu-id="22c8a-131">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22c8a-132">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="22c8a-132">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="22c8a-133">CMyMAPIFormViewer::MoveMessage</span><span class="sxs-lookup"><span data-stu-id="22c8a-133">CMyMAPIFormViewer::MoveMessage</span></span>  <br/> |<span data-ttu-id="22c8a-134">未实现。</span><span class="sxs-lookup"><span data-stu-id="22c8a-134">Not implemented.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="22c8a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22c8a-135">See also</span></span>



[<span data-ttu-id="22c8a-136">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="22c8a-136">IMAPIViewContext::ActivateNext</span></span>](imapiviewcontext-activatenext.md)
  
[<span data-ttu-id="22c8a-137">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="22c8a-137">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="22c8a-138">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="22c8a-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="22c8a-139">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="22c8a-139">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

