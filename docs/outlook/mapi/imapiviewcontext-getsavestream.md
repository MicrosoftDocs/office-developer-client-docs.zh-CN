---
title: IMAPIViewContextGetSaveStream
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.GetSaveStream
api_type:
- COM
ms.assetid: 8316bfa1-3077-401f-aa1e-e9492aca12a8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 68eb74f53d6cee4661c98604ec2ea37609e20ab5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351119"
---
# <a name="imapiviewcontextgetsavestream"></a><span data-ttu-id="a8ace-103">IMAPIViewContext::GetSaveStream</span><span class="sxs-lookup"><span data-stu-id="a8ace-103">IMAPIViewContext::GetSaveStream</span></span>

  
  
<span data-ttu-id="a8ace-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a8ace-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a8ace-105">检索用于保存当前邮件的流。</span><span class="sxs-lookup"><span data-stu-id="a8ace-105">Retrieves a stream to be used for saving the current message.</span></span>
  
```cpp
HRESULT GetSaveStream(
ULONG FAR * pulFlags,
ULONG FAR * pulFormat,
LPSTREAM FAR * ppstm
);
```

## <a name="parameters"></a><span data-ttu-id="a8ace-106">参数</span><span class="sxs-lookup"><span data-stu-id="a8ace-106">Parameters</span></span>

 <span data-ttu-id="a8ace-107">_pulFlags_</span><span class="sxs-lookup"><span data-stu-id="a8ace-107">_pulFlags_</span></span>
  
> <span data-ttu-id="a8ace-108">排除指向控制应如何保存邮件文本的标志的位掩码的指针。</span><span class="sxs-lookup"><span data-stu-id="a8ace-108">[out] Pointer to a bitmask of flags that controls how the message text should be saved.</span></span> <span data-ttu-id="a8ace-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a8ace-109">The following flag can be set:</span></span>
    
<span data-ttu-id="a8ace-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a8ace-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a8ace-111">邮件文本以 Unicode 格式保存。</span><span class="sxs-lookup"><span data-stu-id="a8ace-111">The message text is saved in Unicode format.</span></span> <span data-ttu-id="a8ace-112">如果未设置 MAPI_UNICODE 标志, 则文本将保存为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a8ace-112">If the MAPI_UNICODE flag is not set, the text is saved in ANSI format.</span></span>
    
 <span data-ttu-id="a8ace-113">_pulFormat_</span><span class="sxs-lookup"><span data-stu-id="a8ace-113">_pulFormat_</span></span>
  
> <span data-ttu-id="a8ace-114">排除指向控制保存的文本的格式的标志位掩码的指针。</span><span class="sxs-lookup"><span data-stu-id="a8ace-114">[out] Pointer to a bitmask of flags that controls the format of the saved text.</span></span> <span data-ttu-id="a8ace-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a8ace-115">The following flags can be set:</span></span>
    
<span data-ttu-id="a8ace-116">SAVE_FORMAT_RICHTEXT</span><span class="sxs-lookup"><span data-stu-id="a8ace-116">SAVE_FORMAT_RICHTEXT</span></span> 
  
> <span data-ttu-id="a8ace-117">邮件文本将保存为 rtf 格式的格式文本。</span><span class="sxs-lookup"><span data-stu-id="a8ace-117">The message text is to be saved as formatted text in the Rich Text Format (RTF).</span></span> 
    
<span data-ttu-id="a8ace-118">SAVE_FORMAT_TEXT</span><span class="sxs-lookup"><span data-stu-id="a8ace-118">SAVE_FORMAT_TEXT</span></span> 
  
> <span data-ttu-id="a8ace-119">邮件文本将保存为纯文本格式。</span><span class="sxs-lookup"><span data-stu-id="a8ace-119">The message text is to be saved as plain text.</span></span> 
    
 <span data-ttu-id="a8ace-120">_ppstm_</span><span class="sxs-lookup"><span data-stu-id="a8ace-120">_ppstm_</span></span>
  
> <span data-ttu-id="a8ace-121">排除指向指向将包含已保存邮件的流的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a8ace-121">[out] Pointer to a pointer to the stream that will contain the saved message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a8ace-122">返回值</span><span class="sxs-lookup"><span data-stu-id="a8ace-122">Return value</span></span>

<span data-ttu-id="a8ace-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8ace-123">S_OK</span></span> 
  
> <span data-ttu-id="a8ace-124">已成功检索流。</span><span class="sxs-lookup"><span data-stu-id="a8ace-124">The stream was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a8ace-125">注解</span><span class="sxs-lookup"><span data-stu-id="a8ace-125">Remarks</span></span>

<span data-ttu-id="a8ace-126">表单对象调用**IMAPIViewContext:: GetSaveStream**方法以检索 stream 一个对象, 该对象实现**IStream**接口, 以支持在表单查看器中处理 "另存为" 谓词。</span><span class="sxs-lookup"><span data-stu-id="a8ace-126">Form objects call the **IMAPIViewContext::GetSaveStream** method to retrieve a stream an object that implements the **IStream** interface to support the handling of the Save As verb in the form viewer.</span></span> <span data-ttu-id="a8ace-127">[IMAPIForm::D overb](imapiform-doverb.md)方法, 该方法在表单服务器中实现并由表单查看器调用以调用谓词, 在邮件完全转换为相应的文本格式并置于相应的流中之前, 不应返回。</span><span class="sxs-lookup"><span data-stu-id="a8ace-127">The [IMAPIForm::DoVerb](imapiform-doverb.md) method, which is implemented in the form server and called by the form viewer to invoke a verb, should not return until the message is fully converted into the appropriate text format and placed into the appropriate stream.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="a8ace-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a8ace-128">Notes to callers</span></span>

<span data-ttu-id="a8ace-129">在调用**GetSaveStream**之前, 请勿写入_ppstm_指向的流。</span><span class="sxs-lookup"><span data-stu-id="a8ace-129">Do not write to the stream pointed to by  _ppstm_ before calling **GetSaveStream**.</span></span> <span data-ttu-id="a8ace-130">当**GetSaveStream**返回时, 请勿重置查找指针的位置。</span><span class="sxs-lookup"><span data-stu-id="a8ace-130">When **GetSaveStream** returns, do not reset the position of the seek pointer.</span></span> <span data-ttu-id="a8ace-131">此指针必须保留在保存的邮件文本的末尾。</span><span class="sxs-lookup"><span data-stu-id="a8ace-131">This pointer must remain at the end of the saved message text.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a8ace-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8ace-132">See also</span></span>



[<span data-ttu-id="a8ace-133">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a8ace-133">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)

