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
ms.openlocfilehash: e1ea68a7690a93915cd80ad5406c4d71d3a97400
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321439"
---
# <a name="imapimessagesitegetsession"></a><span data-ttu-id="8aeb6-103">IMAPIMessageSite::GetSession</span><span class="sxs-lookup"><span data-stu-id="8aeb6-103">IMAPIMessageSite::GetSession</span></span>

  
  
<span data-ttu-id="8aeb6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8aeb6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8aeb6-105">返回在其中创建或打开当前邮件的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-105">Returns the MAPI session in which the current message was created or opened.</span></span>
  
```cpp
HRESULT GetSession(
  LPMAPISESSION FAR * ppSession
);
```

## <a name="parameters"></a><span data-ttu-id="8aeb6-106">参数</span><span class="sxs-lookup"><span data-stu-id="8aeb6-106">Parameters</span></span>

 <span data-ttu-id="8aeb6-107">_ppSession_</span><span class="sxs-lookup"><span data-stu-id="8aeb6-107">_ppSession_</span></span>
  
> <span data-ttu-id="8aeb6-108">排除指向指向返回的 session 对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-108">[out] A pointer to a pointer to the returned session object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8aeb6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8aeb6-109">Return value</span></span>

<span data-ttu-id="8aeb6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8aeb6-110">S_OK</span></span> 
  
> <span data-ttu-id="8aeb6-111">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-111">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="8aeb6-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8aeb6-112">S_FALSE</span></span> 
  
> <span data-ttu-id="8aeb6-113">当前邮件不存在会话。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-113">No session exists for the current message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8aeb6-114">注解</span><span class="sxs-lookup"><span data-stu-id="8aeb6-114">Remarks</span></span>

<span data-ttu-id="8aeb6-115">有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-115">For a list of interfaces that are related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="8aeb6-116">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="8aeb6-116">MFCMAPI reference</span></span>

<span data-ttu-id="8aeb6-117">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-117">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="8aeb6-118">**文件**</span><span class="sxs-lookup"><span data-stu-id="8aeb6-118">**File**</span></span>|<span data-ttu-id="8aeb6-119">**函数**</span><span class="sxs-lookup"><span data-stu-id="8aeb6-119">**Function**</span></span>|<span data-ttu-id="8aeb6-120">**备注**</span><span class="sxs-lookup"><span data-stu-id="8aeb6-120">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8aeb6-121">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="8aeb6-121">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="8aeb6-122">CMyMAPIFormViewer:: GetSession</span><span class="sxs-lookup"><span data-stu-id="8aeb6-122">CMyMAPIFormViewer::GetSession</span></span>  <br/> |<span data-ttu-id="8aeb6-123">MFCMAPI 使用**IMAPIMessageSite:: GetSession**方法返回当前缓存的会话指针 (如果可用)。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-123">MFCMAPI uses the **IMAPIMessageSite::GetSession** method to return the currently cached session pointer, if it is available.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8aeb6-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8aeb6-124">See also</span></span>



[<span data-ttu-id="8aeb6-125">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8aeb6-125">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="8aeb6-126">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="8aeb6-126">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

