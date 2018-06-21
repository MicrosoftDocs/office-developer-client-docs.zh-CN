---
title: IMAPISupportCompleteMsg
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CompleteMsg
api_type:
- COM
ms.assetid: e7932433-abe0-4341-95e0-91b37c848145
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: db28d9684f1bb679ce36f99346f4ecc67a1a93e6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19775598"
---
# <a name="imapisupportcompletemsg"></a><span data-ttu-id="20130-103">IMAPISupport::CompleteMsg</span><span class="sxs-lookup"><span data-stu-id="20130-103">IMAPISupport::CompleteMsg</span></span>

  
  
<span data-ttu-id="20130-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="20130-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="20130-105">执行上一条消息后处理。</span><span class="sxs-lookup"><span data-stu-id="20130-105">Performs postprocessing on a message.</span></span> 
  
```cpp
HRESULT CompleteMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="20130-106">参数</span><span class="sxs-lookup"><span data-stu-id="20130-106">Parameters</span></span>

 <span data-ttu-id="20130-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="20130-107">_ulFlags_</span></span>
  
> <span data-ttu-id="20130-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="20130-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="20130-109">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="20130-109">_cbEntryID_</span></span>
  
> <span data-ttu-id="20130-110">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="20130-110">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="20130-111">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="20130-111">_lpEntryID_</span></span>
  
> <span data-ttu-id="20130-112">[in]指向要处理的消息的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="20130-112">[in] A pointer to the entry identifier of the message to process.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="20130-113">返回值</span><span class="sxs-lookup"><span data-stu-id="20130-113">Return value</span></span>

<span data-ttu-id="20130-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="20130-114">S_OK</span></span> 
  
> <span data-ttu-id="20130-115">后处理过程成功。</span><span class="sxs-lookup"><span data-stu-id="20130-115">The postprocessing was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="20130-116">注解</span><span class="sxs-lookup"><span data-stu-id="20130-116">Remarks</span></span>

<span data-ttu-id="20130-117">**IMAPISupport::CompleteMsg**方法实现的消息存储提供程序支持对象和只能由与传输提供程序紧密耦合的消息存储提供程序调用。</span><span class="sxs-lookup"><span data-stu-id="20130-117">The **IMAPISupport::CompleteMsg** method is implemented for message store provider support objects and is called only by message store providers that are tightly coupled with transport providers.</span></span> <span data-ttu-id="20130-118">紧密耦合的存储提供程序调用**IMAPISupport::CompleteMsg**以指示 MAPI 后台处理程序后置处理一条消息。</span><span class="sxs-lookup"><span data-stu-id="20130-118">Tightly coupled store providers call **IMAPISupport::CompleteMsg** to instruct the MAPI spooler to postprocess a message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="20130-119">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="20130-119">Notes to callers</span></span>

<span data-ttu-id="20130-120">仅当紧密结合传输提供程序，您可以处理所有收件人，并且存在以下情况之一时，请调用**CompleteMsg** :</span><span class="sxs-lookup"><span data-stu-id="20130-120">Call **CompleteMsg** only when you are tightly coupled with a transport provider, you can handle all of the message's recipients, and one of the following conditions exists:</span></span> 
  
- <span data-ttu-id="20130-121">邮件已预处理。</span><span class="sxs-lookup"><span data-stu-id="20130-121">The message was preprocessed.</span></span>
    
- <span data-ttu-id="20130-122">邮件需要后处理 MAPI 后台打印程序。</span><span class="sxs-lookup"><span data-stu-id="20130-122">The message requires postprocessing by the MAPI spooler.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="20130-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20130-123">See also</span></span>



[<span data-ttu-id="20130-124">IMAPISupport: IUnknown</span><span class="sxs-lookup"><span data-stu-id="20130-124">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

