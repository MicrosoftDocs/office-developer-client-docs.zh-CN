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
ms.openlocfilehash: 1f4e6c49ca1c537f78ccce708c4a0b00f81ad7e4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567928"
---
# <a name="imapimessagesitegetstore"></a><span data-ttu-id="3b488-103">IMAPIMessageSite::GetStore</span><span class="sxs-lookup"><span data-stu-id="3b488-103">IMAPIMessageSite::GetStore</span></span>

  
  
<span data-ttu-id="3b488-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b488-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3b488-105">如果存在此类存储，返回包含当前邮件的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="3b488-105">Returns the message store that contains the current message, if such a store exists.</span></span> <span data-ttu-id="3b488-106">此方法将返回 NULL 中嵌入的邮件，而不是直接在消息存储库中的其他邮件中存储的_ppStore_参数。</span><span class="sxs-lookup"><span data-stu-id="3b488-106">This method will return NULL in the  _ppStore_ parameter for embedded messages, which are stored in another message instead of directly in a message store.</span></span> 
  
```cpp
HRESULT GetStore(
  LPMDB FAR * ppStore
);
```

## <a name="parameters"></a><span data-ttu-id="3b488-107">参数</span><span class="sxs-lookup"><span data-stu-id="3b488-107">Parameters</span></span>

 <span data-ttu-id="3b488-108">_ppStore_</span><span class="sxs-lookup"><span data-stu-id="3b488-108">_ppStore_</span></span>
  
> <span data-ttu-id="3b488-109">[输出]指向消息存储的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3b488-109">[out] A pointer to a pointer to the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3b488-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3b488-110">Return value</span></span>

<span data-ttu-id="3b488-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b488-111">S_OK</span></span> 
  
> <span data-ttu-id="3b488-112">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="3b488-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="3b488-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3b488-113">S_FALSE</span></span> 
  
> <span data-ttu-id="3b488-114">包含邮件没有存储区。</span><span class="sxs-lookup"><span data-stu-id="3b488-114">There is no store that contains the message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3b488-115">注解</span><span class="sxs-lookup"><span data-stu-id="3b488-115">Remarks</span></span>

<span data-ttu-id="3b488-116">有关与窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="3b488-116">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3b488-117">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="3b488-117">MFCMAPI reference</span></span>

<span data-ttu-id="3b488-118">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3b488-118">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3b488-119">**文件**</span><span class="sxs-lookup"><span data-stu-id="3b488-119">**File**</span></span>|<span data-ttu-id="3b488-120">**函数**</span><span class="sxs-lookup"><span data-stu-id="3b488-120">**Function**</span></span>|<span data-ttu-id="3b488-121">**Comment**</span><span class="sxs-lookup"><span data-stu-id="3b488-121">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b488-122">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="3b488-122">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="3b488-123">CMyMAPIFormViewer::GetStore</span><span class="sxs-lookup"><span data-stu-id="3b488-123">CMyMAPIFormViewer::GetStore</span></span>  <br/> |<span data-ttu-id="3b488-124">MFCMAPI 使用**IMAPIMessageSite::GetStore**方法来获取当前缓存的指针到指定的存储，它是否可用。</span><span class="sxs-lookup"><span data-stu-id="3b488-124">MFCMAPI uses the **IMAPIMessageSite::GetStore** method to get the currently cached pointer to the specified store, if it is available.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3b488-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b488-125">See also</span></span>



[<span data-ttu-id="3b488-126">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3b488-126">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="3b488-127">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="3b488-127">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="3b488-128">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="3b488-128">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

