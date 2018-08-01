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
ms.openlocfilehash: ea95ea4efbbf50e5551a27eb81fe5d5ab3b73948
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775448"
---
# <a name="imapimessagesitegetfolder"></a><span data-ttu-id="cd822-103">IMAPIMessageSite::GetFolder</span><span class="sxs-lookup"><span data-stu-id="cd822-103">IMAPIMessageSite::GetFolder</span></span>

  
  
<span data-ttu-id="cd822-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cd822-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cd822-105">如果存在此类的文件夹，则返回已创建或打开，当前邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd822-105">Returns the folder in which the current message was created or opened, if such a folder exists.</span></span> <span data-ttu-id="cd822-106">此方法中嵌入的邮件，不直接在文件夹中存储的_ppFolder_参数返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="cd822-106">This method returns NULL in the  _ppFolder_ parameter for embedded messages, which are not stored directly in a folder.</span></span> 
  
```cpp
HRESULT GetFolder(
  LPMAPIFOLDER FAR * ppFolder
);
```

## <a name="parameters"></a><span data-ttu-id="cd822-107">参数</span><span class="sxs-lookup"><span data-stu-id="cd822-107">Parameters</span></span>

 <span data-ttu-id="cd822-108">_ppFolder_</span><span class="sxs-lookup"><span data-stu-id="cd822-108">_ppFolder_</span></span>
  
> <span data-ttu-id="cd822-109">[输出]指向返回文件夹指向的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="cd822-109">[out] A pointer to a pointer to the returned folder.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cd822-110">返回值</span><span class="sxs-lookup"><span data-stu-id="cd822-110">Return value</span></span>

<span data-ttu-id="cd822-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd822-111">S_OK</span></span> 
  
> <span data-ttu-id="cd822-112">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="cd822-112">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="cd822-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="cd822-113">S_FALSE</span></span> 
  
> <span data-ttu-id="cd822-114">不存在文件夹的邮件。</span><span class="sxs-lookup"><span data-stu-id="cd822-114">No folder exists for the message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cd822-115">说明</span><span class="sxs-lookup"><span data-stu-id="cd822-115">Remarks</span></span>

<span data-ttu-id="cd822-116">向窗体服务器相关的接口的列表，请参阅[MAPI 表单接口](mapi-form-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="cd822-116">For a list of interfaces that are related to form servers, see [MAPI Form Interfaces](mapi-form-interfaces.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="cd822-117">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="cd822-117">MFCMAPI reference</span></span>

<span data-ttu-id="cd822-118">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="cd822-118">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="cd822-119">**文件**</span><span class="sxs-lookup"><span data-stu-id="cd822-119">**File**</span></span>|<span data-ttu-id="cd822-120">**函数**</span><span class="sxs-lookup"><span data-stu-id="cd822-120">**Function**</span></span>|<span data-ttu-id="cd822-121">**Comment**</span><span class="sxs-lookup"><span data-stu-id="cd822-121">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cd822-122">MyMAPIFormViewer.cpp</span><span class="sxs-lookup"><span data-stu-id="cd822-122">MyMAPIFormViewer.cpp</span></span>  <br/> |<span data-ttu-id="cd822-123">CMyMAPIFormViewer::GetFolder</span><span class="sxs-lookup"><span data-stu-id="cd822-123">CMyMAPIFormViewer::GetFolder</span></span>  <br/> |<span data-ttu-id="cd822-124">MFCMAPI 使用**IMAPIMessageSite::GetFolder**方法将当前缓存的指针返回到指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd822-124">MFCMAPI uses the **IMAPIMessageSite::GetFolder** method to return the currently cached pointer to the specified folder.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cd822-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd822-125">See also</span></span>



[<span data-ttu-id="cd822-126">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="cd822-126">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)


[<span data-ttu-id="cd822-127">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="cd822-127">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="cd822-128">MAPI 表单接口</span><span class="sxs-lookup"><span data-stu-id="cd822-128">MAPI Form Interfaces</span></span>](mapi-form-interfaces.md)

