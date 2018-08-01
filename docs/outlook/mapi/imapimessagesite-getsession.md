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
ms.openlocfilehash: d5d0f465ecdf4865ca86448448c56d54d5df4505
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775467"
---
# <a name="imapimessagesitegetsession"></a><span data-ttu-id="f7e34-103">IMAPIMessageSite::GetSession</span><span class="sxs-lookup"><span data-stu-id="f7e34-103">IMAPIMessageSite::GetSession</span></span>

  
  
<span data-ttu-id="f7e34-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f7e34-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f7e34-105">返回当前消息是创建或打开的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="f7e34-105">Returns the MAPI session in which the current message was created or opened.</span></span>
  
```cpp
HRESULT GetSession(
  LPMAPISESSION FAR * ppSession
);
```

## <a name="parameters"></a><span data-ttu-id="f7e34-106">参数</span><span class="sxs-lookup"><span data-stu-id="f7e34-106">Parameters</span></span>

 <span data-ttu-id="f7e34-107">_ppSession_</span><span class="sxs-lookup"><span data-stu-id="f7e34-107">_ppSession_</span></span>
  
> <span data-ttu-id="f7e34-108">[输出]指向与返回的会话对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f7e34-108">[out] A pointer to a pointer to the returned session object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f7e34-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f7e34-109">Return value</span></span>

<span data-ttu-id="f7e34-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7e34-110">S_OK</span></span> 
  
> <span data-ttu-id="f7e34-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="f7e34-111">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="f7e34-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f7e34-112">S_FALSE</span></span> 
  
> <span data-ttu-id="f7e34-113">为当前消息不存在任何会话。</span><span class="sxs-lookup"><span data-stu-id="f7e34-113">No session exists for the current message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f7e34-114">说明</span><span class="sxs-lookup"><span data-stu-id="f7e34-114">Remarks</span></span>

<span data-ttu-id="f7e34-115">向窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="f7e34-115">For a list of interfaces that are related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f7e34-116">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="f7e34-116">MFCMAPI reference</span></span>

<span data-ttu-id="f7e34-117">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f7e34-117">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f7e34-118">**文件**</span><span class="sxs-lookup"><span data-stu-id="f7e34-118">**File**</span></span>|<span data-ttu-id="f7e34-119">**函数**</span><span class="sxs-lookup"><span data-stu-id="f7e34-119">**Function**</span></span>|<span data-ttu-id="f7e34-120">**Comment**</span><span class="sxs-lookup"><span data-stu-id="f7e34-120">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7e34-121">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="f7e34-121">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="f7e34-122">CMyMAPIFormViewer::GetSession</span><span class="sxs-lookup"><span data-stu-id="f7e34-122">CMyMAPIFormViewer::GetSession</span></span>  <br/> |<span data-ttu-id="f7e34-123">MFCMAPI 使用**IMAPIMessageSite::GetSession**方法可返回当前缓存的会话指针，它是否可用。</span><span class="sxs-lookup"><span data-stu-id="f7e34-123">MFCMAPI uses the **IMAPIMessageSite::GetSession** method to return the currently cached session pointer, if it is available.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f7e34-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7e34-124">See also</span></span>



[<span data-ttu-id="f7e34-125">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f7e34-125">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="f7e34-126">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f7e34-126">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

