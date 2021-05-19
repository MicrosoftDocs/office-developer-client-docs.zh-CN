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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 154d6e4a4e333f3a6165c3875bdcd57957ebf70c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348732"
---
# <a name="itnefopentaggedbody"></a><span data-ttu-id="b9f07-103">ITnef::OpenTaggedBody</span><span class="sxs-lookup"><span data-stu-id="b9f07-103">ITnef::OpenTaggedBody</span></span>

  
  
<span data-ttu-id="b9f07-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9f07-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9f07-105">打开封装邮件的文本上的流接口。</span><span class="sxs-lookup"><span data-stu-id="b9f07-105">Opens a stream interface on the text of an encapsulated message.</span></span>
  
```cpp
HRESULT OpenTaggedBody(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a><span data-ttu-id="b9f07-106">参数</span><span class="sxs-lookup"><span data-stu-id="b9f07-106">Parameters</span></span>

 <span data-ttu-id="b9f07-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="b9f07-107">_lpMessage_</span></span>
  
> <span data-ttu-id="b9f07-108">[in]指向与流关联的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="b9f07-108">[in] A pointer to the message with which the stream is associated.</span></span> <span data-ttu-id="b9f07-109">此消息不需要与调用[OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md)函数时传递的消息[](opentnefstreamex.md)相同。</span><span class="sxs-lookup"><span data-stu-id="b9f07-109">This message is not required to be the same message that is passed in the call to the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
 <span data-ttu-id="b9f07-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b9f07-110">_ulFlags_</span></span>
  
> <span data-ttu-id="b9f07-111">[in]控制流接口打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b9f07-111">[in] A bitmask of flags that controls how the stream interface is opened.</span></span> <span data-ttu-id="b9f07-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="b9f07-112">The following flags can be set:</span></span>
    
<span data-ttu-id="b9f07-113">MAPI_CREATE</span><span class="sxs-lookup"><span data-stu-id="b9f07-113">MAPI_CREATE</span></span> 
  
> <span data-ttu-id="b9f07-114">如果当前邮件中不存在属性，应创建该属性。</span><span class="sxs-lookup"><span data-stu-id="b9f07-114">If a property does not exist in the current message, it should be created.</span></span> <span data-ttu-id="b9f07-115">如果该属性存在，则属性中的当前数据应替换为 TNEF Transport-Neutral封装格式 (数据) 数据。</span><span class="sxs-lookup"><span data-stu-id="b9f07-115">If the property does exist, the current data in the property should be replaced with the data from the Transport-Neutral Encapsulation Format (TNEF) stream.</span></span> <span data-ttu-id="b9f07-116">当实现设置MAPI_CREATE标志时，它还应设置MAPI_MODIFY标志。</span><span class="sxs-lookup"><span data-stu-id="b9f07-116">When an implementation sets the MAPI_CREATE flag, it should also set the MAPI_MODIFY flag.</span></span>
    
<span data-ttu-id="b9f07-117">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="b9f07-117">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="b9f07-118">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="b9f07-118">Requests read/write permission.</span></span> <span data-ttu-id="b9f07-119">默认接口是只读的。</span><span class="sxs-lookup"><span data-stu-id="b9f07-119">The default interface is read-only.</span></span> <span data-ttu-id="b9f07-120">MAPI_MODIFY设置时必须MAPI_CREATE设置。</span><span class="sxs-lookup"><span data-stu-id="b9f07-120">MAPI_MODIFY must be set whenever MAPI_CREATE is set.</span></span>
    
 <span data-ttu-id="b9f07-121">_lppStream_</span><span class="sxs-lookup"><span data-stu-id="b9f07-121">_lppStream_</span></span>
  
> <span data-ttu-id="b9f07-122">[out]指向流对象的指针，该对象包含传入 **封装** 邮件的 PR_BODY ([PidTagBody](pidtagbody-canonical-property.md)) 属性并支持 [IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream) 接口的文本。</span><span class="sxs-lookup"><span data-stu-id="b9f07-122">[out] A pointer to a pointer to a stream object that contains the text from the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property of the passed-in encapsulated message and that supports the [IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream) interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b9f07-123">返回值</span><span class="sxs-lookup"><span data-stu-id="b9f07-123">Return value</span></span>

<span data-ttu-id="b9f07-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9f07-124">S_OK</span></span> 
  
> <span data-ttu-id="b9f07-125">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="b9f07-125">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b9f07-126">备注</span><span class="sxs-lookup"><span data-stu-id="b9f07-126">Remarks</span></span>

<span data-ttu-id="b9f07-127">传输提供程序、邮件存储提供程序和网关调用 **ITnef：：OpenTaggedBody** 方法来打开封装邮件的文本上的流接口 (即 TNEF 对象) 。</span><span class="sxs-lookup"><span data-stu-id="b9f07-127">Transport providers, message store providers, and gateways call the **ITnef::OpenTaggedBody** method to open a stream interface on the text of an encapsulated message (that is, on a TNEF object).</span></span> 
  
<span data-ttu-id="b9f07-128">在处理过程中 **，OpenTaggedBody** 插入或分析指示任何附件或 OLE 对象在邮件文本中的位置的附件标记。</span><span class="sxs-lookup"><span data-stu-id="b9f07-128">As part of its processing, **OpenTaggedBody** either inserts or parses attachment tags that indicate the position of any attachments or OLE objects in the message text.</span></span> <span data-ttu-id="b9f07-129">附件标记的格式如下：</span><span class="sxs-lookup"><span data-stu-id="b9f07-129">The attachment tags are in the following format:</span></span> 
  
 <span data-ttu-id="b9f07-130">**[[**_附件名称_ **：** _n_ **in** attachment container _name_ **]]**</span><span class="sxs-lookup"><span data-stu-id="b9f07-130">**[[** _attachment name_ **:** _n_ **in** _attachment container name_ **]]**</span></span>
  
 <span data-ttu-id="b9f07-131">_附件名称_ 描述附件对象; _n_ 是一个数字，标识序列的一部分的附件，从 [OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md)函数的 _lpKey_ 参数中传递的值递增; [](opentnefstreamex.md)和 _附件容器名称_ 描述附件对象所在的物理组件。</span><span class="sxs-lookup"><span data-stu-id="b9f07-131">_attachment name_ describes the attachment object;  _n_ is a number that identifies the attachment that is part of a sequence, incrementing from the value passed in the  _lpKey_ parameter of the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function; and  _attachment container name_ describes the physical component where the attachment object resides.</span></span> 
  
 <span data-ttu-id="b9f07-132">**OpenTaggedBody** 会读出邮件文本，并插入附件标记，只要附件对象最初出现在文本中。</span><span class="sxs-lookup"><span data-stu-id="b9f07-132">**OpenTaggedBody** reads out message text and inserts an attachment tag wherever an attachment object originally appeared in the text.</span></span> <span data-ttu-id="b9f07-133">原始邮件文本未更改。</span><span class="sxs-lookup"><span data-stu-id="b9f07-133">The original message text is not changed.</span></span> 
  
<span data-ttu-id="b9f07-134">当包含标记的邮件传递到流时，标记将去除，附件对象将重定位在流中标记的位置。</span><span class="sxs-lookup"><span data-stu-id="b9f07-134">When a message that has tags is passed to a stream, the tags are stripped out and the attachment objects are relocated in the position of the tags in the stream.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9f07-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9f07-135">See also</span></span>



[<span data-ttu-id="b9f07-136">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="b9f07-136">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="b9f07-137">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="b9f07-137">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="b9f07-138">PidTagBody 规范属性</span><span class="sxs-lookup"><span data-stu-id="b9f07-138">PidTagBody Canonical Property</span></span>](pidtagbody-canonical-property.md)
  
[<span data-ttu-id="b9f07-139">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b9f07-139">ITnef : IUnknown</span></span>](itnefiunknown.md)

