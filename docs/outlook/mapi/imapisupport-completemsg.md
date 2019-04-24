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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e8c52d71ee47966be09c6c0806eceafae0c5ff5b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331505"
---
# <a name="imapisupportcompletemsg"></a><span data-ttu-id="7c2af-103">IMAPISupport::CompleteMsg</span><span class="sxs-lookup"><span data-stu-id="7c2af-103">IMAPISupport::CompleteMsg</span></span>

  
  
<span data-ttu-id="7c2af-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7c2af-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7c2af-105">对邮件执行后处理。</span><span class="sxs-lookup"><span data-stu-id="7c2af-105">Performs postprocessing on a message.</span></span> 
  
```cpp
HRESULT CompleteMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="7c2af-106">参数</span><span class="sxs-lookup"><span data-stu-id="7c2af-106">Parameters</span></span>

 <span data-ttu-id="7c2af-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7c2af-107">_ulFlags_</span></span>
  
> <span data-ttu-id="7c2af-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="7c2af-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="7c2af-109">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="7c2af-109">_cbEntryID_</span></span>
  
> <span data-ttu-id="7c2af-110">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="7c2af-110">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="7c2af-111">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="7c2af-111">_lpEntryID_</span></span>
  
> <span data-ttu-id="7c2af-112">实时指向要处理的邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="7c2af-112">[in] A pointer to the entry identifier of the message to process.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7c2af-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7c2af-113">Return value</span></span>

<span data-ttu-id="7c2af-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c2af-114">S_OK</span></span> 
  
> <span data-ttu-id="7c2af-115">后处理成功。</span><span class="sxs-lookup"><span data-stu-id="7c2af-115">The postprocessing was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7c2af-116">注解</span><span class="sxs-lookup"><span data-stu-id="7c2af-116">Remarks</span></span>

<span data-ttu-id="7c2af-117">为邮件存储提供程序支持对象实现了**IMAPISupport:: CompleteMsg**方法, 并且只能由与传输提供程序紧密结合的邮件存储提供程序调用。</span><span class="sxs-lookup"><span data-stu-id="7c2af-117">The **IMAPISupport::CompleteMsg** method is implemented for message store provider support objects and is called only by message store providers that are tightly coupled with transport providers.</span></span> <span data-ttu-id="7c2af-118">紧密耦合的存储提供程序调用**IMAPISupport:: CompleteMsg**以指示 MAPI 后台处理程序后置处理邮件。</span><span class="sxs-lookup"><span data-stu-id="7c2af-118">Tightly coupled store providers call **IMAPISupport::CompleteMsg** to instruct the MAPI spooler to postprocess a message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="7c2af-119">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7c2af-119">Notes to callers</span></span>

<span data-ttu-id="7c2af-120">仅限呼叫**CompleteMsg**在与传输提供程序紧密结合时, 可以处理邮件的所有收件人, 并且存在以下情况之一:</span><span class="sxs-lookup"><span data-stu-id="7c2af-120">Call **CompleteMsg** only when you are tightly coupled with a transport provider, you can handle all of the message's recipients, and one of the following conditions exists:</span></span> 
  
- <span data-ttu-id="7c2af-121">已对邮件进行预处理。</span><span class="sxs-lookup"><span data-stu-id="7c2af-121">The message was preprocessed.</span></span>
    
- <span data-ttu-id="7c2af-122">邮件需要 MAPI 后台处理程序进行后处理。</span><span class="sxs-lookup"><span data-stu-id="7c2af-122">The message requires postprocessing by the MAPI spooler.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7c2af-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c2af-123">See also</span></span>



[<span data-ttu-id="7c2af-124">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7c2af-124">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

