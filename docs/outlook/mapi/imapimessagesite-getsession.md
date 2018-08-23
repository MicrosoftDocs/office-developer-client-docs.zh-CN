---
title: IMAPIMessageSiteGetSession
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetSession
api_type:
- COM
ms.assetid: c35d9e38-f4cf-4908-aaa1-a4263b58f7e8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d5d86af111bc778839a78f9b56ba7126e6c973d5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567375"
---
# <a name="imapimessagesitegetsession"></a><span data-ttu-id="0476f-103">IMAPIMessageSite::GetSession</span><span class="sxs-lookup"><span data-stu-id="0476f-103">IMAPIMessageSite::GetSession</span></span>

  
  
<span data-ttu-id="0476f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0476f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0476f-105">返回当前消息是创建或打开的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="0476f-105">Returns the MAPI session in which the current message was created or opened.</span></span>
  
```cpp
HRESULT GetSession(
  LPMAPISESSION FAR * ppSession
);
```

## <a name="parameters"></a><span data-ttu-id="0476f-106">参数</span><span class="sxs-lookup"><span data-stu-id="0476f-106">Parameters</span></span>

 <span data-ttu-id="0476f-107">_ppSession_</span><span class="sxs-lookup"><span data-stu-id="0476f-107">_ppSession_</span></span>
  
> <span data-ttu-id="0476f-108">[输出]指向与返回的会话对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="0476f-108">[out] A pointer to a pointer to the returned session object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0476f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0476f-109">Return value</span></span>

<span data-ttu-id="0476f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0476f-110">S_OK</span></span> 
  
> <span data-ttu-id="0476f-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="0476f-111">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="0476f-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0476f-112">S_FALSE</span></span> 
  
> <span data-ttu-id="0476f-113">为当前消息不存在任何会话。</span><span class="sxs-lookup"><span data-stu-id="0476f-113">No session exists for the current message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0476f-114">注解</span><span class="sxs-lookup"><span data-stu-id="0476f-114">Remarks</span></span>

<span data-ttu-id="0476f-115">向窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="0476f-115">For a list of interfaces that are related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="0476f-116">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="0476f-116">MFCMAPI reference</span></span>

<span data-ttu-id="0476f-117">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="0476f-117">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="0476f-118">**文件**</span><span class="sxs-lookup"><span data-stu-id="0476f-118">**File**</span></span>|<span data-ttu-id="0476f-119">**函数**</span><span class="sxs-lookup"><span data-stu-id="0476f-119">**Function**</span></span>|<span data-ttu-id="0476f-120">**Comment**</span><span class="sxs-lookup"><span data-stu-id="0476f-120">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0476f-121">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="0476f-121">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="0476f-122">CMyMAPIFormViewer::GetSession</span><span class="sxs-lookup"><span data-stu-id="0476f-122">CMyMAPIFormViewer::GetSession</span></span>  <br/> |<span data-ttu-id="0476f-123">MFCMAPI 使用**IMAPIMessageSite::GetSession**方法可返回当前缓存的会话指针，它是否可用。</span><span class="sxs-lookup"><span data-stu-id="0476f-123">MFCMAPI uses the **IMAPIMessageSite::GetSession** method to return the currently cached session pointer, if it is available.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0476f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0476f-124">See also</span></span>



[<span data-ttu-id="0476f-125">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0476f-125">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="0476f-126">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="0476f-126">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

