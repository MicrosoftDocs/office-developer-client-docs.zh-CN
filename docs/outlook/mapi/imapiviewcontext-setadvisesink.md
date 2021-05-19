---
title: IMAPIViewContextSetAdviseSink
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.SetAdviseSink
api_type:
- COM
ms.assetid: 4799084a-b5d1-48c3-a889-b2f0e9d68c30
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7ee641214e1eaae667af356fd8dbe51ff7dc7982
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419392"
---
# <a name="imapiviewcontextsetadvisesink"></a><span data-ttu-id="cf387-103">IMAPIViewContext::SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="cf387-103">IMAPIViewContext::SetAdviseSink</span></span>

  
  
<span data-ttu-id="cf387-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cf387-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cf387-105">管理表单的注册以接收有关查看器中更改的通知。</span><span class="sxs-lookup"><span data-stu-id="cf387-105">Manages a form's registration to receive notifications about changes in the viewer.</span></span> 
  
```cpp
HRESULT SetAdviseSink(
LPMAPIFORMADVISESINK pmvns
);
```

## <a name="parameters"></a><span data-ttu-id="cf387-106">参数</span><span class="sxs-lookup"><span data-stu-id="cf387-106">Parameters</span></span>

 <span data-ttu-id="cf387-107">_pmvns_</span><span class="sxs-lookup"><span data-stu-id="cf387-107">_pmvns_</span></span>
  
> <span data-ttu-id="cf387-108">[in]指向窗体的指针建议接收对象或 NULL。</span><span class="sxs-lookup"><span data-stu-id="cf387-108">[in] Pointer to a form advise sink object or NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cf387-109">返回值</span><span class="sxs-lookup"><span data-stu-id="cf387-109">Return value</span></span>

<span data-ttu-id="cf387-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf387-110">S_OK</span></span> 
  
> <span data-ttu-id="cf387-111">表单通知的注册或取消成功。</span><span class="sxs-lookup"><span data-stu-id="cf387-111">The registration or cancellation for form notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cf387-112">备注</span><span class="sxs-lookup"><span data-stu-id="cf387-112">Remarks</span></span>

<span data-ttu-id="cf387-113">Form 对象调用 **IMAPIViewContext：：SetAdviseSink** 方法，以注册以了解表单查看器中的更改或取消以前的注册。</span><span class="sxs-lookup"><span data-stu-id="cf387-113">Form objects call the **IMAPIViewContext::SetAdviseSink** method to either register to learn about changes in the form viewer or cancel a prior registration.</span></span> <span data-ttu-id="cf387-114">当  _pmvns_ 设置为 NULL 时，表单想要取消注册。</span><span class="sxs-lookup"><span data-stu-id="cf387-114">When  _pmvns_ is set to NULL, the form wants to cancel a registration.</span></span> <span data-ttu-id="cf387-115">当  _pmvns_ 指向有效的表单通知接收器时，表单想要注册将来通知。</span><span class="sxs-lookup"><span data-stu-id="cf387-115">When  _pmvns_ points to a valid form advise sink, the form wants to register for future notifications.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="cf387-116">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="cf387-116">Notes to implementers</span></span>

<span data-ttu-id="cf387-117">当 **SetAdviseSink** 包含窗体通知接收器指针时，请保留对它的引用，直到进行另一个 **SetAdviseSink** 调用以取消通知。</span><span class="sxs-lookup"><span data-stu-id="cf387-117">When **SetAdviseSink** includes a form advise sink pointer, keep a reference to it until another **SetAdviseSink** call is made to cancel notification.</span></span> <span data-ttu-id="cf387-118">在查看器中发生更改时以及加载新邮件时发送通知。</span><span class="sxs-lookup"><span data-stu-id="cf387-118">Send a notification when a change occurs in your viewer and when you are loading a new message.</span></span> 
  
<span data-ttu-id="cf387-119">有关详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="cf387-119">For more information, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="cf387-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="cf387-120">MFCMAPI reference</span></span>

<span data-ttu-id="cf387-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="cf387-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="cf387-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="cf387-122">**File**</span></span>|<span data-ttu-id="cf387-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="cf387-123">**Function**</span></span>|<span data-ttu-id="cf387-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="cf387-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cf387-125">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="cf387-125">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="cf387-126">CMyMAPIFormViewer：：SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="cf387-126">CMyMAPIFormViewer::SetAdviseSink</span></span>  <br/> |<span data-ttu-id="cf387-127">MFCMAPI 在此函数中实现 **IMAPIViewContext：：SetAdviseSink** 方法。</span><span class="sxs-lookup"><span data-stu-id="cf387-127">MFCMAPI implements the **IMAPIViewContext::SetAdviseSink** method in this function.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cf387-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf387-128">See also</span></span>



[<span data-ttu-id="cf387-129">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="cf387-129">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

