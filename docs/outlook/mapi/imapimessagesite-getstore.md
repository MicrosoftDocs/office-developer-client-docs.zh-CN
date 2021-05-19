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
ms.openlocfilehash: 0c78574f213245a5c30ff589ade824e5c5bd84ee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410467"
---
# <a name="imapimessagesitegetstore"></a><span data-ttu-id="26914-103">IMAPIMessageSite::GetStore</span><span class="sxs-lookup"><span data-stu-id="26914-103">IMAPIMessageSite::GetStore</span></span>

  
  
<span data-ttu-id="26914-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="26914-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="26914-105">返回包含当前邮件的邮件存储（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="26914-105">Returns the message store that contains the current message, if such a store exists.</span></span> <span data-ttu-id="26914-106">此方法将在嵌入邮件的  _ppStore_ 参数中返回 NULL，这些嵌入邮件存储在其他邮件中，而不是直接存储在邮件存储中。</span><span class="sxs-lookup"><span data-stu-id="26914-106">This method will return NULL in the  _ppStore_ parameter for embedded messages, which are stored in another message instead of directly in a message store.</span></span> 
  
```cpp
HRESULT GetStore(
  LPMDB FAR * ppStore
);
```

## <a name="parameters"></a><span data-ttu-id="26914-107">参数</span><span class="sxs-lookup"><span data-stu-id="26914-107">Parameters</span></span>

 <span data-ttu-id="26914-108">_ppStore_</span><span class="sxs-lookup"><span data-stu-id="26914-108">_ppStore_</span></span>
  
> <span data-ttu-id="26914-109">[out]指向指向消息存储的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="26914-109">[out] A pointer to a pointer to the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="26914-110">返回值</span><span class="sxs-lookup"><span data-stu-id="26914-110">Return value</span></span>

<span data-ttu-id="26914-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="26914-111">S_OK</span></span> 
  
> <span data-ttu-id="26914-112">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="26914-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="26914-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="26914-113">S_FALSE</span></span> 
  
> <span data-ttu-id="26914-114">没有包含邮件的存储区。</span><span class="sxs-lookup"><span data-stu-id="26914-114">There is no store that contains the message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="26914-115">备注</span><span class="sxs-lookup"><span data-stu-id="26914-115">Remarks</span></span>

<span data-ttu-id="26914-116">有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="26914-116">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="26914-117">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="26914-117">MFCMAPI reference</span></span>

<span data-ttu-id="26914-118">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="26914-118">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="26914-119">**文件**</span><span class="sxs-lookup"><span data-stu-id="26914-119">**File**</span></span>|<span data-ttu-id="26914-120">**函数**</span><span class="sxs-lookup"><span data-stu-id="26914-120">**Function**</span></span>|<span data-ttu-id="26914-121">**备注**</span><span class="sxs-lookup"><span data-stu-id="26914-121">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="26914-122">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="26914-122">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="26914-123">CMyMAPIFormViewer：：GetStore</span><span class="sxs-lookup"><span data-stu-id="26914-123">CMyMAPIFormViewer::GetStore</span></span>  <br/> |<span data-ttu-id="26914-124">MFCMAPI 使用 **IMAPIMessageSite：：GetStore** 方法获取当前缓存的指向指定存储的指针（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="26914-124">MFCMAPI uses the **IMAPIMessageSite::GetStore** method to get the currently cached pointer to the specified store, if it is available.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="26914-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26914-125">See also</span></span>



[<span data-ttu-id="26914-126">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="26914-126">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="26914-127">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="26914-127">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="26914-128">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="26914-128">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

