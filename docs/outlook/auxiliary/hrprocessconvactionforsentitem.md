---
title: HrProcessConvActionForSentItem
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 08121e33-7820-4a31-b6da-06a4a54ec43f
description: 基于邮件项的 PidTagConversationId 对邮件项目执行发送后分类。
ms.openlocfilehash: 675f308093eea30084271abc66c1fa66e2ad6828
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318898"
---
# <a name="hrprocessconvactionforsentitem"></a><span data-ttu-id="134c7-103">HrProcessConvActionForSentItem</span><span class="sxs-lookup"><span data-stu-id="134c7-103">HrProcessConvActionForSentItem</span></span>

<span data-ttu-id="134c7-104">基于邮件项目的 [PidTagConversationId 对邮件项目执行发送后分类](https://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="134c7-104">Performs post-send categorization on a mail item based on its [PidTagConversationId](https://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="134c7-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="134c7-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="134c7-106">导出者：</span><span class="sxs-lookup"><span data-stu-id="134c7-106">Exported by:</span></span>  <br/> |<span data-ttu-id="134c7-107">Outlook.exe</span><span class="sxs-lookup"><span data-stu-id="134c7-107">Outlook.exe</span></span>  <br/> |
|<span data-ttu-id="134c7-108">调用者：</span><span class="sxs-lookup"><span data-stu-id="134c7-108">Called by:</span></span>  <br/> |<span data-ttu-id="134c7-109">客户端</span><span class="sxs-lookup"><span data-stu-id="134c7-109">Client</span></span>  <br/> |
|<span data-ttu-id="134c7-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="134c7-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="134c7-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="134c7-111">Outlook</span></span>  <br/> |
   
```cpp
HRESULT WINAPI HrProcessConvActionForSentItem( 
    SBinary const *pmbinStoreEid, 
    SBinary const *pmbinMsgEid, 
    SBinary const *pmbinConvID, 
    DWORD dwFlags)
```

## <a name="parameters"></a><span data-ttu-id="134c7-112">参数</span><span class="sxs-lookup"><span data-stu-id="134c7-112">Parameters</span></span>

<span data-ttu-id="134c7-113">_pmbinStoreEid_</span><span class="sxs-lookup"><span data-stu-id="134c7-113">_pmbinStoreEid_</span></span>
  
> <span data-ttu-id="134c7-114">[in]存储[的 PidTagEntryId](https://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx)或邮件项目的[PidTagStoreEntryId。](https://msdn.microsoft.com/library/0d705667-19f4-4eda-a068-e65ea8f00d9b%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="134c7-114">[in] The [PidTagEntryId](https://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) of the store, or the [PidTagStoreEntryId](https://msdn.microsoft.com/library/0d705667-19f4-4eda-a068-e65ea8f00d9b%28Office.15%29.aspx) of the mail item.</span></span> <span data-ttu-id="134c7-115">不能为 NULL 或无效。</span><span class="sxs-lookup"><span data-stu-id="134c7-115">Cannot be NULL or invalid.</span></span> 
    
<span data-ttu-id="134c7-116">_pmbinMsgEid_</span><span class="sxs-lookup"><span data-stu-id="134c7-116">_pmbinMsgEid_</span></span>
  
> <span data-ttu-id="134c7-117">[in]邮件[项目的 PidTagEntryId。](https://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="134c7-117">[in] The [PidTagEntryId](https://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) of the mail item.</span></span> <span data-ttu-id="134c7-118">不能为 NULL 或无效。</span><span class="sxs-lookup"><span data-stu-id="134c7-118">Cannot be NULL or invalid.</span></span> 
    
<span data-ttu-id="134c7-119">_pmbinConvID_</span><span class="sxs-lookup"><span data-stu-id="134c7-119">_pmbinConvID_</span></span>
  
> <span data-ttu-id="134c7-120">[in]邮件[项目的 PidTagConversationId。](https://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="134c7-120">[in] The [PidTagConversationId](https://msdn.microsoft.com/library/f8e4a5fa-cb73-4eca-b174-72e1fda821a6%28Office.15%29.aspx) of the mail item.</span></span> <span data-ttu-id="134c7-121">不能为 NULL 或无效。</span><span class="sxs-lookup"><span data-stu-id="134c7-121">Cannot be NULL or invalid.</span></span> 
    
<span data-ttu-id="134c7-122">_dwFlags_</span><span class="sxs-lookup"><span data-stu-id="134c7-122">_dwFlags_</span></span>
  
> <span data-ttu-id="134c7-123">[in]一个位掩码，用于指定有关方法调用的其他信息。</span><span class="sxs-lookup"><span data-stu-id="134c7-123">[in] A bitmask that specifies additional information about the method call.</span></span>
    
   - <span data-ttu-id="134c7-124">0 - 此方法调用中未使用任何其他选项。</span><span class="sxs-lookup"><span data-stu-id="134c7-124">0—No additional options are used in this method call.</span></span> <span data-ttu-id="134c7-125">这是建议的值。</span><span class="sxs-lookup"><span data-stu-id="134c7-125">This is the recommended value.</span></span> 
    
   - <span data-ttu-id="134c7-126">**PCAFSIF_MSGEID_IS_SEARCH_KEY** _- pmbinMsgEid_ 实际上是邮件的 [PidTagSearchKey。](https://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="134c7-126">**PCAFSIF_MSGEID_IS_SEARCH_KEY**— _pmbinMsgEid_ is actually the [PidTagSearchKey](https://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) of the message.</span></span> <span data-ttu-id="134c7-127">使用 **PidTagSearchKey** 会消耗大量资源，如果 [PidTagEntryId 可用，应避免使用 PidTagEntryId。](https://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="134c7-127">Using a **PidTagSearchKey** is resource intensive, and should be avoided if a [PidTagEntryId](https://msdn.microsoft.com/library/ca02e873-c2d2-4d58-8df8-c05fbcdc8fba%28Office.15%29.aspx) is available.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="134c7-128">返回值</span><span class="sxs-lookup"><span data-stu-id="134c7-128">Return values</span></span>

|<span data-ttu-id="134c7-129">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="134c7-129">**HRESULT**</span></span>|<span data-ttu-id="134c7-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="134c7-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="134c7-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="134c7-131">S_OK</span></span>  <br/> |<span data-ttu-id="134c7-132">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="134c7-132">The call was successful.</span></span>  <br/> |
|<span data-ttu-id="134c7-133">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="134c7-133">E_INVALIDARG</span></span>  <br/> | <span data-ttu-id="134c7-134">_dwFlags_ 包含未知标志。</span><span class="sxs-lookup"><span data-stu-id="134c7-134">_dwFlags_ contains an unknown flag.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="134c7-135">备注</span><span class="sxs-lookup"><span data-stu-id="134c7-135">Remarks</span></span>

<span data-ttu-id="134c7-136">类别被视为个人信息，不应在用户的邮箱外部传输。</span><span class="sxs-lookup"><span data-stu-id="134c7-136">Categories are considered personal information and should not be transmitted outside the mailbox of the user.</span></span> <span data-ttu-id="134c7-137">因此，不要对未发送的邮件项目调用 **HrProcessConvActionForSentItem。**</span><span class="sxs-lookup"><span data-stu-id="134c7-137">Therefore, do not call **HrProcessConvActionForSentItem** on an unsent mail item.</span></span> <span data-ttu-id="134c7-138">相反，发送该项目，然后在存档副本上 **调用 HrProcessConvActionForSentItem。**</span><span class="sxs-lookup"><span data-stu-id="134c7-138">Instead, send the item, and then call **HrProcessConvActionForSentItem** on the archived copy.</span></span> <span data-ttu-id="134c7-139">存档副本可能存储在"已发送的项目"文件夹中或等效位置。</span><span class="sxs-lookup"><span data-stu-id="134c7-139">The archived copy may be stored in the Sent Items folder, or an equivalent location.</span></span> 
  
<span data-ttu-id="134c7-140">您的应用程序必须在处理过程中Outlook.exe，如从 COM 加载项调用 **HrProcessConvActionForSentItem。**</span><span class="sxs-lookup"><span data-stu-id="134c7-140">Your application must be in-process with Outlook.exe, such as from a COM add-in, to call **HrProcessConvActionForSentItem**.</span></span> <span data-ttu-id="134c7-141">如果尝试在进程外调用 **HrProcessConvActionForSentItem，HrProcessConvActionForSentItem** 将引发访问冲突异常。 </span><span class="sxs-lookup"><span data-stu-id="134c7-141">If you attempt to call **HrProcessConvActionForSentItem** out-of-process, **HrProcessConvActionForSentItem** will throw an access-violation exception.</span></span> 
  

