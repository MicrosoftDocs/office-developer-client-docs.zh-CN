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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351189"
---
# <a name="imapiviewcontextsetadvisesink"></a><span data-ttu-id="a2829-103">IMAPIViewContext::SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="a2829-103">IMAPIViewContext::SetAdviseSink</span></span>

  
  
<span data-ttu-id="a2829-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2829-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2829-105">管理表单注册, 以便在查看器中接收有关更改的通知。</span><span class="sxs-lookup"><span data-stu-id="a2829-105">Manages a form's registration to receive notifications about changes in the viewer.</span></span> 
  
```cpp
HRESULT SetAdviseSink(
LPMAPIFORMADVISESINK pmvns
);
```

## <a name="parameters"></a><span data-ttu-id="a2829-106">参数</span><span class="sxs-lookup"><span data-stu-id="a2829-106">Parameters</span></span>

 <span data-ttu-id="a2829-107">_pmvns_</span><span class="sxs-lookup"><span data-stu-id="a2829-107">_pmvns_</span></span>
  
> <span data-ttu-id="a2829-108">实时指向表单建议接收器对象或空值的指针。</span><span class="sxs-lookup"><span data-stu-id="a2829-108">[in] Pointer to a form advise sink object or NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a2829-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a2829-109">Return value</span></span>

<span data-ttu-id="a2829-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2829-110">S_OK</span></span> 
  
> <span data-ttu-id="a2829-111">表单通知的注册或取消已成功。</span><span class="sxs-lookup"><span data-stu-id="a2829-111">The registration or cancellation for form notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a2829-112">注解</span><span class="sxs-lookup"><span data-stu-id="a2829-112">Remarks</span></span>

<span data-ttu-id="a2829-113">表单对象调用**IMAPIViewContext:: SetAdviseSink**方法以注册, 以了解有关表单查看器中的更改或取消之前的注册。</span><span class="sxs-lookup"><span data-stu-id="a2829-113">Form objects call the **IMAPIViewContext::SetAdviseSink** method to either register to learn about changes in the form viewer or cancel a prior registration.</span></span> <span data-ttu-id="a2829-114">当_pmvns_设置为 NULL 时, 窗体要取消注册。</span><span class="sxs-lookup"><span data-stu-id="a2829-114">When  _pmvns_ is set to NULL, the form wants to cancel a registration.</span></span> <span data-ttu-id="a2829-115">当_pmvns_指向有效的窗体建议接收器时, 该表单希望注册将来的通知。</span><span class="sxs-lookup"><span data-stu-id="a2829-115">When  _pmvns_ points to a valid form advise sink, the form wants to register for future notifications.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a2829-116">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="a2829-116">Notes to implementers</span></span>

<span data-ttu-id="a2829-117">当**SetAdviseSink**包含窗体建议接收器指针时, 保留对它的引用, 直到再次调用**SetAdviseSink**以取消通知。</span><span class="sxs-lookup"><span data-stu-id="a2829-117">When **SetAdviseSink** includes a form advise sink pointer, keep a reference to it until another **SetAdviseSink** call is made to cancel notification.</span></span> <span data-ttu-id="a2829-118">在查看器中发生更改时, 以及在加载新邮件时发送通知。</span><span class="sxs-lookup"><span data-stu-id="a2829-118">Send a notification when a change occurs in your viewer and when you are loading a new message.</span></span> 
  
<span data-ttu-id="a2829-119">有关详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="a2829-119">For more information, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a2829-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a2829-120">MFCMAPI reference</span></span>

<span data-ttu-id="a2829-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a2829-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a2829-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="a2829-122">**File**</span></span>|<span data-ttu-id="a2829-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="a2829-123">**Function**</span></span>|<span data-ttu-id="a2829-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="a2829-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2829-125">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="a2829-125">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="a2829-126">CMyMAPIFormViewer:: SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="a2829-126">CMyMAPIFormViewer::SetAdviseSink</span></span>  <br/> |<span data-ttu-id="a2829-127">MFCMAPI 实现此函数中的**IMAPIViewContext:: SetAdviseSink**方法。</span><span class="sxs-lookup"><span data-stu-id="a2829-127">MFCMAPI implements the **IMAPIViewContext::SetAdviseSink** method in this function.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a2829-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2829-128">See also</span></span>



[<span data-ttu-id="a2829-129">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a2829-129">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

