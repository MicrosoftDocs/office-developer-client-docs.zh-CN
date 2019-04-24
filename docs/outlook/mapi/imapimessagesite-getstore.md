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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321432"
---
# <a name="imapimessagesitegetstore"></a><span data-ttu-id="33428-103">IMAPIMessageSite::GetStore</span><span class="sxs-lookup"><span data-stu-id="33428-103">IMAPIMessageSite::GetStore</span></span>

  
  
<span data-ttu-id="33428-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="33428-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="33428-105">如果存在这样的存储区, 则返回包含当前邮件的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="33428-105">Returns the message store that contains the current message, if such a store exists.</span></span> <span data-ttu-id="33428-106">此方法将在_ppStore_参数中为嵌入的邮件 (而不是直接在邮件存储区中存储) 返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="33428-106">This method will return NULL in the  _ppStore_ parameter for embedded messages, which are stored in another message instead of directly in a message store.</span></span> 
  
```cpp
HRESULT GetStore(
  LPMDB FAR * ppStore
);
```

## <a name="parameters"></a><span data-ttu-id="33428-107">参数</span><span class="sxs-lookup"><span data-stu-id="33428-107">Parameters</span></span>

 <span data-ttu-id="33428-108">_ppStore_</span><span class="sxs-lookup"><span data-stu-id="33428-108">_ppStore_</span></span>
  
> <span data-ttu-id="33428-109">排除指向邮件存储区的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="33428-109">[out] A pointer to a pointer to the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="33428-110">返回值</span><span class="sxs-lookup"><span data-stu-id="33428-110">Return value</span></span>

<span data-ttu-id="33428-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="33428-111">S_OK</span></span> 
  
> <span data-ttu-id="33428-112">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="33428-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="33428-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="33428-113">S_FALSE</span></span> 
  
> <span data-ttu-id="33428-114">没有包含该邮件的存储区。</span><span class="sxs-lookup"><span data-stu-id="33428-114">There is no store that contains the message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="33428-115">注解</span><span class="sxs-lookup"><span data-stu-id="33428-115">Remarks</span></span>

<span data-ttu-id="33428-116">有关与表单服务器相关的接口的列表, 请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="33428-116">For a list of interfaces related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="33428-117">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="33428-117">MFCMAPI reference</span></span>

<span data-ttu-id="33428-118">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="33428-118">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="33428-119">**文件**</span><span class="sxs-lookup"><span data-stu-id="33428-119">**File**</span></span>|<span data-ttu-id="33428-120">**函数**</span><span class="sxs-lookup"><span data-stu-id="33428-120">**Function**</span></span>|<span data-ttu-id="33428-121">**备注**</span><span class="sxs-lookup"><span data-stu-id="33428-121">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="33428-122">MyMAPIFormViewer</span><span class="sxs-lookup"><span data-stu-id="33428-122">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="33428-123">CMyMAPIFormViewer:: GetStore</span><span class="sxs-lookup"><span data-stu-id="33428-123">CMyMAPIFormViewer::GetStore</span></span>  <br/> |<span data-ttu-id="33428-124">MFCMAPI 使用**IMAPIMessageSite:: GetStore**方法将当前缓存的指针获取到指定的存储区 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="33428-124">MFCMAPI uses the **IMAPIMessageSite::GetStore** method to get the currently cached pointer to the specified store, if it is available.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="33428-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33428-125">See also</span></span>



[<span data-ttu-id="33428-126">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="33428-126">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="33428-127">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="33428-127">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="33428-128">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="33428-128">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

