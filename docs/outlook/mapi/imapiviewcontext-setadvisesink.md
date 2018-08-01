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
ms.openlocfilehash: abee768dd29cc807b605a7d13570a579cb271b2c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775742"
---
# <a name="imapiviewcontextsetadvisesink"></a><span data-ttu-id="2023b-103">IMAPIViewContext::SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="2023b-103">IMAPIViewContext::SetAdviseSink</span></span>

  
  
<span data-ttu-id="2023b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2023b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2023b-105">管理窗体的注册中查看者接收有关更改的通知。</span><span class="sxs-lookup"><span data-stu-id="2023b-105">Manages a form's registration to receive notifications about changes in the viewer.</span></span> 
  
```cpp
HRESULT SetAdviseSink(
LPMAPIFORMADVISESINK pmvns
);
```

## <a name="parameters"></a><span data-ttu-id="2023b-106">参数</span><span class="sxs-lookup"><span data-stu-id="2023b-106">Parameters</span></span>

 <span data-ttu-id="2023b-107">_pmvns_</span><span class="sxs-lookup"><span data-stu-id="2023b-107">_pmvns_</span></span>
  
> <span data-ttu-id="2023b-108">[in]向窗体的指针建议接收器对象或 NULL。</span><span class="sxs-lookup"><span data-stu-id="2023b-108">[in] Pointer to a form advise sink object or NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2023b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2023b-109">Return value</span></span>

<span data-ttu-id="2023b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2023b-110">S_OK</span></span> 
  
> <span data-ttu-id="2023b-111">成功注册或取消的窗体通知。</span><span class="sxs-lookup"><span data-stu-id="2023b-111">The registration or cancellation for form notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2023b-112">说明</span><span class="sxs-lookup"><span data-stu-id="2023b-112">Remarks</span></span>

<span data-ttu-id="2023b-113">表单对象调用任一注册，以了解有关表单查看器中更改或取消预先注册到**IMAPIViewContext::SetAdviseSink**方法。</span><span class="sxs-lookup"><span data-stu-id="2023b-113">Form objects call the **IMAPIViewContext::SetAdviseSink** method to either register to learn about changes in the form viewer or cancel a prior registration.</span></span> <span data-ttu-id="2023b-114">当_pmvns_设置为 NULL 时，表单想要取消注册。</span><span class="sxs-lookup"><span data-stu-id="2023b-114">When  _pmvns_ is set to NULL, the form wants to cancel a registration.</span></span> <span data-ttu-id="2023b-115">时有效的窗体的_pmvns_指向告知接收器，窗体想要注册将来的通知。</span><span class="sxs-lookup"><span data-stu-id="2023b-115">When  _pmvns_ points to a valid form advise sink, the form wants to register for future notifications.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2023b-116">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="2023b-116">Notes to implementers</span></span>

<span data-ttu-id="2023b-117">如果**SetAdviseSink**包含窗体告知接收器指针，请继续对它的引用，直到进行另一个**SetAdviseSink**调用取消通知。</span><span class="sxs-lookup"><span data-stu-id="2023b-117">When **SetAdviseSink** includes a form advise sink pointer, keep a reference to it until another **SetAdviseSink** call is made to cancel notification.</span></span> <span data-ttu-id="2023b-118">在您查看器和所加载新消息时，将发生更改时发送通知。</span><span class="sxs-lookup"><span data-stu-id="2023b-118">Send a notification when a change occurs in your viewer and when you are loading a new message.</span></span> 
  
<span data-ttu-id="2023b-119">有关详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="2023b-119">For more information, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2023b-120">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="2023b-120">MFCMAPI reference</span></span>

<span data-ttu-id="2023b-121">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2023b-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2023b-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="2023b-122">**File**</span></span>|<span data-ttu-id="2023b-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="2023b-123">**Function**</span></span>|<span data-ttu-id="2023b-124">**Comment**</span><span class="sxs-lookup"><span data-stu-id="2023b-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2023b-125">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="2023b-125">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="2023b-126">CMyMAPIFormViewer::SetAdviseSink</span><span class="sxs-lookup"><span data-stu-id="2023b-126">CMyMAPIFormViewer::SetAdviseSink</span></span>  <br/> |<span data-ttu-id="2023b-127">MFCMAPI 此函数中实现**IMAPIViewContext::SetAdviseSink**方法。</span><span class="sxs-lookup"><span data-stu-id="2023b-127">MFCMAPI implements the **IMAPIViewContext::SetAdviseSink** method in this function.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2023b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2023b-128">See also</span></span>



[<span data-ttu-id="2023b-129">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="2023b-129">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

