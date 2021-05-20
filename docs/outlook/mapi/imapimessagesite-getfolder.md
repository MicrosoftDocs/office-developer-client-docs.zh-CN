---
title: IMAPIMessageSiteGetFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.GetFolder
api_type:
- COM
ms.assetid: 9f4b4147-ed98-47cb-a799-ddf028f8e826
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 24461099877af683109c8627eacd22a657d6e156
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430565"
---
# <a name="imapimessagesitegetfolder"></a><span data-ttu-id="6c7c8-103">IMAPIMessageSite::GetFolder</span><span class="sxs-lookup"><span data-stu-id="6c7c8-103">IMAPIMessageSite::GetFolder</span></span>

  
  
<span data-ttu-id="6c7c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c7c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c7c8-105">返回创建或打开当前邮件的文件夹（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="6c7c8-105">Returns the folder in which the current message was created or opened, if such a folder exists.</span></span> <span data-ttu-id="6c7c8-106">此方法在  _ppFolder_ 参数中返回嵌入邮件的 NULL，这些邮件不会直接存储在文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6c7c8-106">This method returns NULL in the  _ppFolder_ parameter for embedded messages, which are not stored directly in a folder.</span></span> 
  
```cpp
HRESULT GetFolder(
  LPMAPIFOLDER FAR * ppFolder
);
```

## <a name="parameters"></a><span data-ttu-id="6c7c8-107">参数</span><span class="sxs-lookup"><span data-stu-id="6c7c8-107">Parameters</span></span>

 <span data-ttu-id="6c7c8-108">_ppFolder_</span><span class="sxs-lookup"><span data-stu-id="6c7c8-108">_ppFolder_</span></span>
  
> <span data-ttu-id="6c7c8-109">[out]指向返回文件夹的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6c7c8-109">[out] A pointer to a pointer to the returned folder.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6c7c8-110">返回值</span><span class="sxs-lookup"><span data-stu-id="6c7c8-110">Return value</span></span>

<span data-ttu-id="6c7c8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c7c8-111">S_OK</span></span> 
  
> <span data-ttu-id="6c7c8-112">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="6c7c8-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="6c7c8-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6c7c8-113">S_FALSE</span></span> 
  
> <span data-ttu-id="6c7c8-114">邮件没有文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c7c8-114">No folder exists for the message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6c7c8-115">备注</span><span class="sxs-lookup"><span data-stu-id="6c7c8-115">Remarks</span></span>

<span data-ttu-id="6c7c8-116">有关与表单服务器相关的接口列表，请参阅 [MAPI Form Interfaces](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="6c7c8-116">For a list of interfaces that are related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6c7c8-117">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="6c7c8-117">MFCMAPI reference</span></span>

<span data-ttu-id="6c7c8-118">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6c7c8-118">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6c7c8-119">**文件**</span><span class="sxs-lookup"><span data-stu-id="6c7c8-119">**File**</span></span>|<span data-ttu-id="6c7c8-120">**函数**</span><span class="sxs-lookup"><span data-stu-id="6c7c8-120">**Function**</span></span>|<span data-ttu-id="6c7c8-121">**备注**</span><span class="sxs-lookup"><span data-stu-id="6c7c8-121">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c7c8-122">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="6c7c8-122">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="6c7c8-123">CMyMAPIFormViewer：：GetFolder</span><span class="sxs-lookup"><span data-stu-id="6c7c8-123">CMyMAPIFormViewer::GetFolder</span></span>  <br/> |<span data-ttu-id="6c7c8-124">MFCMAPI 使用 **IMAPIMessageSite：：GetFolder** 方法将当前缓存的指针返回到指定文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c7c8-124">MFCMAPI uses the **IMAPIMessageSite::GetFolder** method to return the currently cached pointer to the specified folder.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6c7c8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c7c8-125">See also</span></span>



[<span data-ttu-id="6c7c8-126">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6c7c8-126">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="6c7c8-127">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6c7c8-127">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="6c7c8-128">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="6c7c8-128">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

