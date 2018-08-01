---
title: IMAPIMessageSiteGetStore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetStore
api_type:
- COM
ms.assetid: d1ca619e-8bdc-417b-aed6-23dd30e6eafa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2787150a9fa0fc41e04c58b4a4310ffa844f3743
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775465"
---
# <a name="imapimessagesitegetstore"></a><span data-ttu-id="854ea-103">IMAPIMessageSite::GetStore</span><span class="sxs-lookup"><span data-stu-id="854ea-103">IMAPIMessageSite::GetStore</span></span>

  
  
<span data-ttu-id="854ea-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="854ea-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="854ea-105">如果存在此类存储，返回包含当前邮件的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="854ea-105">Returns the message store that contains the current message, if such a store exists.</span></span> <span data-ttu-id="854ea-106">此方法将返回 NULL 中嵌入的邮件，而不是直接在消息存储库中的其他邮件中存储的_ppStore_参数。</span><span class="sxs-lookup"><span data-stu-id="854ea-106">This method will return NULL in the  _ppStore_ parameter for embedded messages, which are stored in another message instead of directly in a message store.</span></span> 
  
```cpp
HRESULT GetStore(
  LPMDB FAR * ppStore
);
```

## <a name="parameters"></a><span data-ttu-id="854ea-107">参数</span><span class="sxs-lookup"><span data-stu-id="854ea-107">Parameters</span></span>

 <span data-ttu-id="854ea-108">_ppStore_</span><span class="sxs-lookup"><span data-stu-id="854ea-108">_ppStore_</span></span>
  
> <span data-ttu-id="854ea-109">[输出]指向消息存储的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="854ea-109">[out] A pointer to a pointer to the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="854ea-110">返回值</span><span class="sxs-lookup"><span data-stu-id="854ea-110">Return value</span></span>

<span data-ttu-id="854ea-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="854ea-111">S_OK</span></span> 
  
> <span data-ttu-id="854ea-112">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="854ea-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="854ea-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="854ea-113">S_FALSE</span></span> 
  
> <span data-ttu-id="854ea-114">包含邮件没有存储区。</span><span class="sxs-lookup"><span data-stu-id="854ea-114">There is no store that contains the message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="854ea-115">说明</span><span class="sxs-lookup"><span data-stu-id="854ea-115">Remarks</span></span>

<span data-ttu-id="854ea-116">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="854ea-116">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="854ea-117">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="854ea-117">MFCMAPI reference</span></span>

<span data-ttu-id="854ea-118">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="854ea-118">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="854ea-119">**文件**</span><span class="sxs-lookup"><span data-stu-id="854ea-119">**File**</span></span>|<span data-ttu-id="854ea-120">**函数**</span><span class="sxs-lookup"><span data-stu-id="854ea-120">**Function**</span></span>|<span data-ttu-id="854ea-121">**Comment**</span><span class="sxs-lookup"><span data-stu-id="854ea-121">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="854ea-122">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="854ea-122">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="854ea-123">CMyMAPIFormViewer::GetStore</span><span class="sxs-lookup"><span data-stu-id="854ea-123">CMyMAPIFormViewer::GetStore</span></span>  <br/> |<span data-ttu-id="854ea-124">MFCMAPI 使用**IMAPIMessageSite::GetStore**方法来获取当前缓存的指针到指定的存储，它是否可用。</span><span class="sxs-lookup"><span data-stu-id="854ea-124">MFCMAPI uses the **IMAPIMessageSite::GetStore** method to get the currently cached pointer to the specified store, if it is available.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="854ea-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="854ea-125">See also</span></span>



[<span data-ttu-id="854ea-126">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="854ea-126">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="854ea-127">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="854ea-127">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="854ea-128">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="854ea-128">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

