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
# <a name="itnefopentaggedbody"></a><span data-ttu-id="229b0-103">ITnef::OpenTaggedBody</span><span class="sxs-lookup"><span data-stu-id="229b0-103">ITnef::OpenTaggedBody</span></span>

  
  
<span data-ttu-id="229b0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="229b0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="229b0-105">打开封装的邮件的文本上的流接口。</span><span class="sxs-lookup"><span data-stu-id="229b0-105">Opens a stream interface on the text of an encapsulated message.</span></span>
  
```cpp
HRESULT OpenTaggedBody(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a><span data-ttu-id="229b0-106">参数</span><span class="sxs-lookup"><span data-stu-id="229b0-106">Parameters</span></span>

 <span data-ttu-id="229b0-107">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="229b0-107">_lpMessage_</span></span>
  
> <span data-ttu-id="229b0-108">实时指向与流关联的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="229b0-108">[in] A pointer to the message with which the stream is associated.</span></span> <span data-ttu-id="229b0-109">此消息不需要与在对[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的调用中传递的邮件相同。</span><span class="sxs-lookup"><span data-stu-id="229b0-109">This message is not required to be the same message that is passed in the call to the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
 <span data-ttu-id="229b0-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="229b0-110">_ulFlags_</span></span>
  
> <span data-ttu-id="229b0-111">实时控制流接口打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="229b0-111">[in] A bitmask of flags that controls how the stream interface is opened.</span></span> <span data-ttu-id="229b0-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="229b0-112">The following flags can be set:</span></span>
    
<span data-ttu-id="229b0-113">MAPI_CREATE</span><span class="sxs-lookup"><span data-stu-id="229b0-113">MAPI_CREATE</span></span> 
  
> <span data-ttu-id="229b0-114">如果某一属性不存在于当前邮件中, 则应创建该属性。</span><span class="sxs-lookup"><span data-stu-id="229b0-114">If a property does not exist in the current message, it should be created.</span></span> <span data-ttu-id="229b0-115">如果该属性存在, 则应将属性中的当前数据替换为来自非特定于传输的封装格式 (TNEF) 流中的数据。</span><span class="sxs-lookup"><span data-stu-id="229b0-115">If the property does exist, the current data in the property should be replaced with the data from the Transport-Neutral Encapsulation Format (TNEF) stream.</span></span> <span data-ttu-id="229b0-116">当某个实现设置 MAPI_CREATE 标志时, 它还应设置 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="229b0-116">When an implementation sets the MAPI_CREATE flag, it should also set the MAPI_MODIFY flag.</span></span>
    
<span data-ttu-id="229b0-117">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="229b0-117">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="229b0-118">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="229b0-118">Requests read/write permission.</span></span> <span data-ttu-id="229b0-119">默认接口是只读的。</span><span class="sxs-lookup"><span data-stu-id="229b0-119">The default interface is read-only.</span></span> <span data-ttu-id="229b0-120">只要设置了 MAPI_CREATE, 就必须设置 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="229b0-120">MAPI_MODIFY must be set whenever MAPI_CREATE is set.</span></span>
    
 <span data-ttu-id="229b0-121">_lppStream_</span><span class="sxs-lookup"><span data-stu-id="229b0-121">_lppStream_</span></span>
  
> <span data-ttu-id="229b0-122">排除指向 stream 对象的指针, 该对象包含已传递的封装邮件的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中的文本, 并支持[IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream)接口。</span><span class="sxs-lookup"><span data-stu-id="229b0-122">[out] A pointer to a pointer to a stream object that contains the text from the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property of the passed-in encapsulated message and that supports the [IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream) interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="229b0-123">返回值</span><span class="sxs-lookup"><span data-stu-id="229b0-123">Return value</span></span>

<span data-ttu-id="229b0-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="229b0-124">S_OK</span></span> 
  
> <span data-ttu-id="229b0-125">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="229b0-125">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="229b0-126">注解</span><span class="sxs-lookup"><span data-stu-id="229b0-126">Remarks</span></span>

<span data-ttu-id="229b0-127">传输提供程序、邮件存储提供程序和网关调用**ITnef:: OpenTaggedBody**方法, 打开封装邮件的文本 (即 TNEF 对象) 上的流接口。</span><span class="sxs-lookup"><span data-stu-id="229b0-127">Transport providers, message store providers, and gateways call the **ITnef::OpenTaggedBody** method to open a stream interface on the text of an encapsulated message (that is, on a TNEF object).</span></span> 
  
<span data-ttu-id="229b0-128">在处理过程中, **OpenTaggedBody**会插入或分析附件标记, 以指示邮件文本中任何附件或 OLE 对象的位置。</span><span class="sxs-lookup"><span data-stu-id="229b0-128">As part of its processing, **OpenTaggedBody** either inserts or parses attachment tags that indicate the position of any attachments or OLE objects in the message text.</span></span> <span data-ttu-id="229b0-129">附件标记采用以下格式:</span><span class="sxs-lookup"><span data-stu-id="229b0-129">The attachment tags are in the following format:</span></span> 
  
 <span data-ttu-id="229b0-130">**[[** 附件_名称_ **:** _附件容器名称_**中的** _n_ **]]**</span><span class="sxs-lookup"><span data-stu-id="229b0-130">**[[** _attachment name_ **:** _n_ **in** _attachment container name_ **]]**</span></span>
  
 <span data-ttu-id="229b0-131">_附件名称_描述了附件对象; _n_是一个数字, 用于标识作为序列一部分的附件, 从[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的_lpKey_参数中传递的值增加;和_附件容器名称_描述了附件对象所在的物理组件。</span><span class="sxs-lookup"><span data-stu-id="229b0-131">_attachment name_ describes the attachment object;  _n_ is a number that identifies the attachment that is part of a sequence, incrementing from the value passed in the  _lpKey_ parameter of the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function; and  _attachment container name_ describes the physical component where the attachment object resides.</span></span> 
  
 <span data-ttu-id="229b0-132">**OpenTaggedBody**读取邮件文本, 并在附件对象最初显示在文本中的任何位置插入附件标记。</span><span class="sxs-lookup"><span data-stu-id="229b0-132">**OpenTaggedBody** reads out message text and inserts an attachment tag wherever an attachment object originally appeared in the text.</span></span> <span data-ttu-id="229b0-133">原始邮件文本不会更改。</span><span class="sxs-lookup"><span data-stu-id="229b0-133">The original message text is not changed.</span></span> 
  
<span data-ttu-id="229b0-134">将带有标记的邮件传递给流时, 将去除这些标记, 并在流中标记的位置重新定位附件对象。</span><span class="sxs-lookup"><span data-stu-id="229b0-134">When a message that has tags is passed to a stream, the tags are stripped out and the attachment objects are relocated in the position of the tags in the stream.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="229b0-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="229b0-135">See also</span></span>



[<span data-ttu-id="229b0-136">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="229b0-136">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="229b0-137">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="229b0-137">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="229b0-138">PidTagBody 规范属性</span><span class="sxs-lookup"><span data-stu-id="229b0-138">PidTagBody Canonical Property</span></span>](pidtagbody-canonical-property.md)
  
[<span data-ttu-id="229b0-139">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="229b0-139">ITnef : IUnknown</span></span>](itnefiunknown.md)

