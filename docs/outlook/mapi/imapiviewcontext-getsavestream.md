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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7981dc8550485aa22859c4a8dc25541bedf1217c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775748"
---
# <a name="imapiviewcontextgetsavestream"></a><span data-ttu-id="9f868-103">IMAPIViewContext::GetSaveStream</span><span class="sxs-lookup"><span data-stu-id="9f868-103">IMAPIViewContext::GetSaveStream</span></span>

  
  
<span data-ttu-id="9f868-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9f868-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9f868-105">检索用于保存当前消息流。</span><span class="sxs-lookup"><span data-stu-id="9f868-105">Retrieves a stream to be used for saving the current message.</span></span>
  
```cpp
HRESULT GetSaveStream(
ULONG FAR * pulFlags,
ULONG FAR * pulFormat,
LPSTREAM FAR * ppstm
);
```

## <a name="parameters"></a><span data-ttu-id="9f868-106">参数</span><span class="sxs-lookup"><span data-stu-id="9f868-106">Parameters</span></span>

 <span data-ttu-id="9f868-107">_pulFlags_</span><span class="sxs-lookup"><span data-stu-id="9f868-107">_pulFlags_</span></span>
  
> <span data-ttu-id="9f868-108">[输出]指向控制应如何保存消息文本的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="9f868-108">[out] Pointer to a bitmask of flags that controls how the message text should be saved.</span></span> <span data-ttu-id="9f868-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="9f868-109">The following flag can be set:</span></span>
    
<span data-ttu-id="9f868-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="9f868-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="9f868-111">Unicode 格式保存的消息文本。</span><span class="sxs-lookup"><span data-stu-id="9f868-111">The message text is saved in Unicode format.</span></span> <span data-ttu-id="9f868-112">如果未设置 MAPI_UNICODE 标志，文本将保存在 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="9f868-112">If the MAPI_UNICODE flag is not set, the text is saved in ANSI format.</span></span>
    
 <span data-ttu-id="9f868-113">_pulFormat_</span><span class="sxs-lookup"><span data-stu-id="9f868-113">_pulFormat_</span></span>
  
> <span data-ttu-id="9f868-114">[输出]指向控制的已保存的文本的格式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="9f868-114">[out] Pointer to a bitmask of flags that controls the format of the saved text.</span></span> <span data-ttu-id="9f868-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="9f868-115">The following flags can be set:</span></span>
    
<span data-ttu-id="9f868-116">SAVE_FORMAT_RICHTEXT</span><span class="sxs-lookup"><span data-stu-id="9f868-116">SAVE_FORMAT_RICHTEXT</span></span> 
  
> <span data-ttu-id="9f868-117">消息文本是保存为带格式文本中富文本格式 (RTF)。</span><span class="sxs-lookup"><span data-stu-id="9f868-117">The message text is to be saved as formatted text in the Rich Text Format (RTF).</span></span> 
    
<span data-ttu-id="9f868-118">SAVE_FORMAT_TEXT</span><span class="sxs-lookup"><span data-stu-id="9f868-118">SAVE_FORMAT_TEXT</span></span> 
  
> <span data-ttu-id="9f868-119">消息文本是保存为纯文本。</span><span class="sxs-lookup"><span data-stu-id="9f868-119">The message text is to be saved as plain text.</span></span> 
    
 <span data-ttu-id="9f868-120">_ppstm_</span><span class="sxs-lookup"><span data-stu-id="9f868-120">_ppstm_</span></span>
  
> <span data-ttu-id="9f868-121">[输出]为将包含已保存的邮件流指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9f868-121">[out] Pointer to a pointer to the stream that will contain the saved message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9f868-122">返回值</span><span class="sxs-lookup"><span data-stu-id="9f868-122">Return value</span></span>

<span data-ttu-id="9f868-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f868-123">S_OK</span></span> 
  
> <span data-ttu-id="9f868-124">成功检索的流。</span><span class="sxs-lookup"><span data-stu-id="9f868-124">The stream was successfully retrieved.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9f868-125">说明</span><span class="sxs-lookup"><span data-stu-id="9f868-125">Remarks</span></span>

<span data-ttu-id="9f868-126">表单对象调用**IMAPIViewContext::GetSaveStream**方法检索流实现表单查看器中支持的另存为谓词处理的**IStream**接口的对象。</span><span class="sxs-lookup"><span data-stu-id="9f868-126">Form objects call the **IMAPIViewContext::GetSaveStream** method to retrieve a stream an object that implements the **IStream** interface to support the handling of the Save As verb in the form viewer.</span></span> <span data-ttu-id="9f868-127">[IMAPIForm::DoVerb](imapiform-doverb.md)方法，这是在窗体服务器中实现，并调用表单查看器调用一个谓词，不应该返回直到邮件是完全转换为相应的文本格式，并放入适当的流。</span><span class="sxs-lookup"><span data-stu-id="9f868-127">The [IMAPIForm::DoVerb](imapiform-doverb.md) method, which is implemented in the form server and called by the form viewer to invoke a verb, should not return until the message is fully converted into the appropriate text format and placed into the appropriate stream.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9f868-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9f868-128">Notes to callers</span></span>

<span data-ttu-id="9f868-129">不写入由指向_ppstm_调用**GetSaveStream**之前的流。</span><span class="sxs-lookup"><span data-stu-id="9f868-129">Do not write to the stream pointed to by  _ppstm_ before calling **GetSaveStream**.</span></span> <span data-ttu-id="9f868-130">**GetSaveStream**返回时，不要重置 seek 指针的位置。</span><span class="sxs-lookup"><span data-stu-id="9f868-130">When **GetSaveStream** returns, do not reset the position of the seek pointer.</span></span> <span data-ttu-id="9f868-131">此指针必须保持已保存的消息文本的结尾处。</span><span class="sxs-lookup"><span data-stu-id="9f868-131">This pointer must remain at the end of the saved message text.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9f868-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f868-132">See also</span></span>



[<span data-ttu-id="9f868-133">IMAPIViewContext : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9f868-133">IMAPIViewContext : IUnknown</span></span>](imapiviewcontextiunknown.md)

