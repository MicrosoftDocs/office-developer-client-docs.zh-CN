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
ms.openlocfilehash: c68e4fbda661a119416918a2c35d1780f1deccda
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321362"
---
# <a name="imapimessagesitemovemessage"></a><span data-ttu-id="f1680-103">IMAPIMessageSite::MoveMessage</span><span class="sxs-lookup"><span data-stu-id="f1680-103">IMAPIMessageSite::MoveMessage</span></span>

  
  
<span data-ttu-id="f1680-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1680-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1680-105">将当前邮件移动到文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f1680-105">Moves the current message to a folder.</span></span>
  
```cpp
HRESULT MoveMessage(
  LPFOLDER pFolderDestination,
  LPMAPIVIEWCONTEXT pViewContext,
  LPCRECT prcPosRect
);
```

## <a name="parameters"></a><span data-ttu-id="f1680-106">参数</span><span class="sxs-lookup"><span data-stu-id="f1680-106">Parameters</span></span>

 <span data-ttu-id="f1680-107">_pFolderDestination_</span><span class="sxs-lookup"><span data-stu-id="f1680-107">_pFolderDestination_</span></span>
  
> <span data-ttu-id="f1680-108">实时指向要将邮件移动到的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="f1680-108">[in] A pointer to the folder where the message is to be moved.</span></span>
    
 <span data-ttu-id="f1680-109">_pViewContext_</span><span class="sxs-lookup"><span data-stu-id="f1680-109">_pViewContext_</span></span>
  
> <span data-ttu-id="f1680-110">实时指向视图上下文对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f1680-110">[in] A pointer to a view context object.</span></span>
    
 <span data-ttu-id="f1680-111">_prcPosRect_</span><span class="sxs-lookup"><span data-stu-id="f1680-111">_prcPosRect_</span></span>
  
> <span data-ttu-id="f1680-112">实时指向包含当前窗体的窗口大小和位置的[RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="f1680-112">[in] A pointer to a [RECT](https://msdn.microsoft.com/library/dd162897%28VS.85%29.aspx) structure that contains the current form's window size and position.</span></span> <span data-ttu-id="f1680-113">下一个显示的窗体也使用此窗口矩形。</span><span class="sxs-lookup"><span data-stu-id="f1680-113">The next form displayed also uses this window rectangle.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f1680-114">返回值</span><span class="sxs-lookup"><span data-stu-id="f1680-114">Return value</span></span>

<span data-ttu-id="f1680-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1680-115">S_OK</span></span> 
  
> <span data-ttu-id="f1680-116">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="f1680-116">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="f1680-117">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="f1680-117">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="f1680-118">此邮件网站不支持该操作。</span><span class="sxs-lookup"><span data-stu-id="f1680-118">The operation is not supported by this message site.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f1680-119">注解</span><span class="sxs-lookup"><span data-stu-id="f1680-119">Remarks</span></span>

<span data-ttu-id="f1680-120">表单对象调用**IMAPIMessageSite:: MoveMessage**方法将当前邮件移动到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1680-120">Form objects call the **IMAPIMessageSite::MoveMessage** method to move the current message to a new folder.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="f1680-121">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="f1680-121">Notes to implementers</span></span>

<span data-ttu-id="f1680-122">表单查看器的**MoveMessage**实现必须先调用[IMAPIViewContext:: ActivateNext](imapiviewcontext-activatenext.md)方法, 并传递 VCDIR_MOVE 标志, 然后再将邮件实际移动到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1680-122">A form viewer's implementation of **MoveMessage** must call the [IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md) method, passing the VCDIR_MOVE flag, before actually moving the message to a new folder.</span></span> <span data-ttu-id="f1680-123">若要获取窗体窗口使用的**RECT**结构, 请调用 Windows [GetWindowRect](https://msdn.microsoft.com/library/ms633519)函数。</span><span class="sxs-lookup"><span data-stu-id="f1680-123">To obtain the **RECT** structure used by a form's window, call the Windows [GetWindowRect](https://msdn.microsoft.com/library/ms633519) function.</span></span> 
  
<span data-ttu-id="f1680-124">有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="f1680-124">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="f1680-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f1680-125">Notes to callers</span></span>

<span data-ttu-id="f1680-126">在返回**MoveMessage**之后, 表单必须检查当前邮件, 如果不存在, 则解除自己。</span><span class="sxs-lookup"><span data-stu-id="f1680-126">Following the return of **MoveMessage**, forms must check for a current message and then dismiss themselves if none exists.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f1680-127">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f1680-127">MFCMAPI reference</span></span>

<span data-ttu-id="f1680-128">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f1680-128">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f1680-129">**文件**</span><span class="sxs-lookup"><span data-stu-id="f1680-129">**File**</span></span>|<span data-ttu-id="f1680-130">**函数**</span><span class="sxs-lookup"><span data-stu-id="f1680-130">**Function**</span></span>|<span data-ttu-id="f1680-131">**备注**</span><span class="sxs-lookup"><span data-stu-id="f1680-131">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1680-132">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="f1680-132">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="f1680-133">CMyMAPIFormViewer:: MoveMessage</span><span class="sxs-lookup"><span data-stu-id="f1680-133">CMyMAPIFormViewer::MoveMessage</span></span>  <br/> |<span data-ttu-id="f1680-134">未实现。</span><span class="sxs-lookup"><span data-stu-id="f1680-134">Not implemented.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f1680-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1680-135">See also</span></span>



[<span data-ttu-id="f1680-136">IMAPIViewContext::ActivateNext</span><span class="sxs-lookup"><span data-stu-id="f1680-136">IMAPIViewContext::ActivateNext</span></span>](imapiviewcontext-activatenext.md)
  
[<span data-ttu-id="f1680-137">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f1680-137">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="f1680-138">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f1680-138">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="f1680-139">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="f1680-139">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

