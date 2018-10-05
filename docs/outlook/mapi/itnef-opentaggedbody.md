---
title: ITnefOpenTaggedBody
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.OpenTaggedBody
api_type:
- COM
ms.assetid: 70d5b34c-85b3-4d1f-860e-2838947ba428
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 154d6e4a4e333f3a6165c3875bdcd57957ebf70c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383739"
---
# <a name="itnefopentaggedbody"></a><span data-ttu-id="e05e7-103">ITnef::OpenTaggedBody</span><span class="sxs-lookup"><span data-stu-id="e05e7-103">ITnef::OpenTaggedBody</span></span>

  
  
<span data-ttu-id="e05e7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e05e7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e05e7-105">打开上封装的消息的文本的流接口。</span><span class="sxs-lookup"><span data-stu-id="e05e7-105">Opens a stream interface on the text of an encapsulated message.</span></span>
  
```cpp
HRESULT OpenTaggedBody(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a><span data-ttu-id="e05e7-106">参数</span><span class="sxs-lookup"><span data-stu-id="e05e7-106">Parameters</span></span>

 <span data-ttu-id="e05e7-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="e05e7-107">_lpMessage_</span></span>
  
> <span data-ttu-id="e05e7-108">[in]指向与 stream 所关联的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="e05e7-108">[in] A pointer to the message with which the stream is associated.</span></span> <span data-ttu-id="e05e7-109">此消息不需要为相同的邮件传递对[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的调用中。</span><span class="sxs-lookup"><span data-stu-id="e05e7-109">This message is not required to be the same message that is passed in the call to the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
 <span data-ttu-id="e05e7-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e05e7-110">_ulFlags_</span></span>
  
> <span data-ttu-id="e05e7-111">[in]位掩码的标志，控制如何打开的 stream 接口。</span><span class="sxs-lookup"><span data-stu-id="e05e7-111">[in] A bitmask of flags that controls how the stream interface is opened.</span></span> <span data-ttu-id="e05e7-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="e05e7-112">The following flags can be set:</span></span>
    
<span data-ttu-id="e05e7-113">MAPI_CREATE</span><span class="sxs-lookup"><span data-stu-id="e05e7-113">MAPI_CREATE</span></span> 
  
> <span data-ttu-id="e05e7-114">如果属性不存在当前消息中，应创建它。</span><span class="sxs-lookup"><span data-stu-id="e05e7-114">If a property does not exist in the current message, it should be created.</span></span> <span data-ttu-id="e05e7-115">如果该属性不存在，应使用传输中性封装格式 (TNEF) 用于将 stream 中的数据更换中属性的当前数据。</span><span class="sxs-lookup"><span data-stu-id="e05e7-115">If the property does exist, the current data in the property should be replaced with the data from the Transport-Neutral Encapsulation Format (TNEF) stream.</span></span> <span data-ttu-id="e05e7-116">当实现设置 MAPI_CREATE 标志时，它也应设置 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="e05e7-116">When an implementation sets the MAPI_CREATE flag, it should also set the MAPI_MODIFY flag.</span></span>
    
<span data-ttu-id="e05e7-117">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="e05e7-117">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="e05e7-118">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="e05e7-118">Requests read/write permission.</span></span> <span data-ttu-id="e05e7-119">默认接口是只读的。</span><span class="sxs-lookup"><span data-stu-id="e05e7-119">The default interface is read-only.</span></span> <span data-ttu-id="e05e7-120">必须设置 MAPI_MODIFY，只要 MAPI_CREATE 设置。</span><span class="sxs-lookup"><span data-stu-id="e05e7-120">MAPI_MODIFY must be set whenever MAPI_CREATE is set.</span></span>
    
 <span data-ttu-id="e05e7-121">_lppStream_</span><span class="sxs-lookup"><span data-stu-id="e05e7-121">_lppStream_</span></span>
  
> <span data-ttu-id="e05e7-122">[输出]指向到包含传入的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中的文本 stream 对象的指针的指针封装消息和支持[IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream)接口的。</span><span class="sxs-lookup"><span data-stu-id="e05e7-122">[out] A pointer to a pointer to a stream object that contains the text from the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property of the passed-in encapsulated message and that supports the [IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream) interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="e05e7-123">返回值</span><span class="sxs-lookup"><span data-stu-id="e05e7-123">Return value</span></span>

<span data-ttu-id="e05e7-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="e05e7-124">S_OK</span></span> 
  
> <span data-ttu-id="e05e7-125">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="e05e7-125">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e05e7-126">说明</span><span class="sxs-lookup"><span data-stu-id="e05e7-126">Remarks</span></span>

<span data-ttu-id="e05e7-127">传输提供程序、 消息存储提供程序，和网关调用**ITnef::OpenTaggedBody**方法打开上封装的消息的文本的流接口 （即上 TNEF, 对象中）。</span><span class="sxs-lookup"><span data-stu-id="e05e7-127">Transport providers, message store providers, and gateways call the **ITnef::OpenTaggedBody** method to open a stream interface on the text of an encapsulated message (that is, on a TNEF object).</span></span> 
  
<span data-ttu-id="e05e7-128">作为其处理的一部分， **OpenTaggedBody**插入或分析附件标记指示消息文本中的任何附件或 OLE 对象的位置。</span><span class="sxs-lookup"><span data-stu-id="e05e7-128">As part of its processing, **OpenTaggedBody** either inserts or parses attachment tags that indicate the position of any attachments or OLE objects in the message text.</span></span> <span data-ttu-id="e05e7-129">附件标记是采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="e05e7-129">The attachment tags are in the following format:</span></span> 
  
 <span data-ttu-id="e05e7-130">**[[** **_附件名称_ **:** _n_ _附件容器名称_** **]]**</span><span class="sxs-lookup"><span data-stu-id="e05e7-130">**[[** _attachment name_ **:** _n_ **in** _attachment container name_ **]]**</span></span>
  
 <span data-ttu-id="e05e7-131">_附件名称_介绍 attachment 对象中; _n_是从[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数; 的_lpKey_参数中传递的值递增的数字标识的序列的一部分附件和_附件容器名称_介绍 attachment 对象所在的物理组件。</span><span class="sxs-lookup"><span data-stu-id="e05e7-131">_attachment name_ describes the attachment object;  _n_ is a number that identifies the attachment that is part of a sequence, incrementing from the value passed in the  _lpKey_ parameter of the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function; and  _attachment container name_ describes the physical component where the attachment object resides.</span></span> 
  
 <span data-ttu-id="e05e7-132">**OpenTaggedBody**读取出消息文本，并应 attachment 对象最初出现在文本中插入某个附件标记。</span><span class="sxs-lookup"><span data-stu-id="e05e7-132">**OpenTaggedBody** reads out message text and inserts an attachment tag wherever an attachment object originally appeared in the text.</span></span> <span data-ttu-id="e05e7-133">原始消息文本不会更改。</span><span class="sxs-lookup"><span data-stu-id="e05e7-133">The original message text is not changed.</span></span> 
  
<span data-ttu-id="e05e7-134">当已标记邮件传递到流时，标记都将去除和流中的标记的位置中重新定位的 attachment 对象。</span><span class="sxs-lookup"><span data-stu-id="e05e7-134">When a message that has tags is passed to a stream, the tags are stripped out and the attachment objects are relocated in the position of the tags in the stream.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e05e7-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e05e7-135">See also</span></span>



[<span data-ttu-id="e05e7-136">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="e05e7-136">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="e05e7-137">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="e05e7-137">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="e05e7-138">PidTagBody 规范属性</span><span class="sxs-lookup"><span data-stu-id="e05e7-138">PidTagBody Canonical Property</span></span>](pidtagbody-canonical-property.md)
  
[<span data-ttu-id="e05e7-139">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e05e7-139">ITnef : IUnknown</span></span>](itnefiunknown.md)

