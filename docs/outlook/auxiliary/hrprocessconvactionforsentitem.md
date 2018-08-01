---
title: HrProcessConvActionForSentItem
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 08121e33-7820-4a31-b6da-06a4a54ec43f
description: 根据其 pidtagconversationid 对应邮件项目上执行后发送分类。
ms.openlocfilehash: efecfc2d0d865428cb958fc15a858bbc7807c5d1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774200"
---
# <a name="hrprocessconvactionforsentitem"></a><span data-ttu-id="2dc2f-103">HrProcessConvActionForSentItem</span><span class="sxs-lookup"><span data-stu-id="2dc2f-103">HrProcessConvActionForSentItem</span></span>

<span data-ttu-id="2dc2f-104">根据其[pidtagconversationid 对应](http://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx)邮件项目上执行后发送分类。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-104">Performs post-send categorization on a mail item based on its [PidTagConversationId](http://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="2dc2f-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="2dc2f-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2dc2f-106">导出：</span><span class="sxs-lookup"><span data-stu-id="2dc2f-106">Exported by:</span></span>  <br/> |<span data-ttu-id="2dc2f-107">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="2dc2f-107">Outlook.exe</span></span>  <br/> |
|<span data-ttu-id="2dc2f-108">调用：</span><span class="sxs-lookup"><span data-stu-id="2dc2f-108">Called by:</span></span>  <br/> |<span data-ttu-id="2dc2f-109">客户端</span><span class="sxs-lookup"><span data-stu-id="2dc2f-109">Client</span></span>  <br/> |
|<span data-ttu-id="2dc2f-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="2dc2f-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="2dc2f-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="2dc2f-111">Outlook</span></span>  <br/> |
   
```cpp
HRESULT WINAPI HrProcessConvActionForSentItem( 
    SBinary const *pmbinStoreEid, 
    SBinary const *pmbinMsgEid, 
    SBinary const *pmbinConvID, 
    DWORD dwFlags)
```

## <a name="parameters"></a><span data-ttu-id="2dc2f-112">参数</span><span class="sxs-lookup"><span data-stu-id="2dc2f-112">Parameters</span></span>

<span data-ttu-id="2dc2f-113">_pmbinStoreEid_</span><span class="sxs-lookup"><span data-stu-id="2dc2f-113">_pmbinStoreEid_</span></span>
  
> <span data-ttu-id="2dc2f-114">[in]存储区或邮件项目的[PidTagStoreEntryId](http://msdn.microsoft.com/library/0d705667-19f4-4eda-a068-e65ea8f00d9b%28Office.15%29.aspx) [PidTagEntryId](http://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-114">[in] The [PidTagEntryId](http://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) of the store, or the [PidTagStoreEntryId](http://msdn.microsoft.com/library/0d705667-19f4-4eda-a068-e65ea8f00d9b%28Office.15%29.aspx) of the mail item.</span></span> <span data-ttu-id="2dc2f-115">不能为 NULL 或无效。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-115">Cannot be NULL or invalid.</span></span> 
    
<span data-ttu-id="2dc2f-116">_pmbinMsgEid_</span><span class="sxs-lookup"><span data-stu-id="2dc2f-116">_pmbinMsgEid_</span></span>
  
> <span data-ttu-id="2dc2f-117">[in]邮件项目[PidTagEntryId](http://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-117">[in] The [PidTagEntryId](http://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) of the mail item.</span></span> <span data-ttu-id="2dc2f-118">不能为 NULL 或无效。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-118">Cannot be NULL or invalid.</span></span> 
    
<span data-ttu-id="2dc2f-119">_pmbinConvID_</span><span class="sxs-lookup"><span data-stu-id="2dc2f-119">_pmbinConvID_</span></span>
  
> <span data-ttu-id="2dc2f-120">[in]邮件项目[pidtagconversationid 对应](http://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-120">[in] The [PidTagConversationId](http://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx) of the mail item.</span></span> <span data-ttu-id="2dc2f-121">不能为 NULL 或无效。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-121">Cannot be NULL or invalid.</span></span> 
    
<span data-ttu-id="2dc2f-122">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="2dc2f-122">_dwFlags_</span></span>
  
> <span data-ttu-id="2dc2f-123">[in]一个位掩码，指定有关方法调用的其他信息。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-123">[in] A bitmask that specifies additional information about the method call.</span></span>
    
   - <span data-ttu-id="2dc2f-124">0 — 在此方法调用中未使用任何其他选项。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-124">0—No additional options are used in this method call.</span></span> <span data-ttu-id="2dc2f-125">这是建议的值。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-125">This is the recommended value.</span></span> 
    
   - <span data-ttu-id="2dc2f-126">**PCAFSIF_MSGEID_IS_SEARCH_KEY**— _pmbinMsgEid_是实际[PidTagSearchKey](http://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx)的邮件。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-126">**PCAFSIF_MSGEID_IS_SEARCH_KEY**— _pmbinMsgEid_ is actually the [PidTagSearchKey](http://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) of the message.</span></span> <span data-ttu-id="2dc2f-127">使用**PidTagSearchKey**占用资源，并应避免使用[PidTagEntryId](http://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx)是否可用。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-127">Using a **PidTagSearchKey** is resource intensive, and should be avoided if a [PidTagEntryId](http://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) is available.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="2dc2f-128">返回值</span><span class="sxs-lookup"><span data-stu-id="2dc2f-128">Return values</span></span>

|<span data-ttu-id="2dc2f-129">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="2dc2f-129">**HRESULT**</span></span>|<span data-ttu-id="2dc2f-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="2dc2f-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2dc2f-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="2dc2f-131">S_OK</span></span>  <br/> |<span data-ttu-id="2dc2f-132">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-132">The call was successful.</span></span>  <br/> |
|<span data-ttu-id="2dc2f-133">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2dc2f-133">E_INVALIDARG</span></span>  <br/> | <span data-ttu-id="2dc2f-134">_dwFlags_包含未知的标志。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-134">_dwFlags_ contains an unknown flag.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2dc2f-135">说明</span><span class="sxs-lookup"><span data-stu-id="2dc2f-135">Remarks</span></span>

<span data-ttu-id="2dc2f-136">类别被视为个人信息并不应之外的用户的邮箱传输。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-136">Categories are considered personal information and should not be transmitted outside the mailbox of the user.</span></span> <span data-ttu-id="2dc2f-137">因此，不要未发送的邮件项目上调用**HrProcessConvActionForSentItem** 。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-137">Therefore, do not call **HrProcessConvActionForSentItem** on an unsent mail item.</span></span> <span data-ttu-id="2dc2f-138">相反，将项目，发送，然后在存档的副本上调用**HrProcessConvActionForSentItem** 。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-138">Instead, send the item, and then call **HrProcessConvActionForSentItem** on the archived copy.</span></span> <span data-ttu-id="2dc2f-139">可能会在已发送邮件文件夹中或等效位置存储存档的副本。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-139">The archived copy may be stored in the Sent Items folder, or an equivalent location.</span></span> 
  
<span data-ttu-id="2dc2f-140">您的应用程序必须在过程与 Outlook.exe，例如从 COM 加载项，若要调用**HrProcessConvActionForSentItem**。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-140">Your application must be in-process with Outlook.exe, such as from a COM add-in, to call **HrProcessConvActionForSentItem**.</span></span> <span data-ttu-id="2dc2f-141">如果尝试调用**HrProcessConvActionForSentItem**进程外， **HrProcessConvActionForSentItem**将引发异常访问冲突。</span><span class="sxs-lookup"><span data-stu-id="2dc2f-141">If you attempt to call **HrProcessConvActionForSentItem** out-of-process, **HrProcessConvActionForSentItem** will throw an access-violation exception.</span></span> 
  

