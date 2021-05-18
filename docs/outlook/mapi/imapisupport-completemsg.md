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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411188"
---
# <a name="imapisupportcompletemsg"></a><span data-ttu-id="2cae3-103">IMAPISupport::CompleteMsg</span><span class="sxs-lookup"><span data-stu-id="2cae3-103">IMAPISupport::CompleteMsg</span></span>

  
  
<span data-ttu-id="2cae3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2cae3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2cae3-105">对邮件执行后置处理。</span><span class="sxs-lookup"><span data-stu-id="2cae3-105">Performs postprocessing on a message.</span></span> 
  
```cpp
HRESULT CompleteMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="2cae3-106">参数</span><span class="sxs-lookup"><span data-stu-id="2cae3-106">Parameters</span></span>

 <span data-ttu-id="2cae3-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2cae3-107">_ulFlags_</span></span>
  
> <span data-ttu-id="2cae3-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="2cae3-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="2cae3-109">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="2cae3-109">_cbEntryID_</span></span>
  
> <span data-ttu-id="2cae3-110">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="2cae3-110">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="2cae3-111">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="2cae3-111">_lpEntryID_</span></span>
  
> <span data-ttu-id="2cae3-112">[in]指向要处理的邮件的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="2cae3-112">[in] A pointer to the entry identifier of the message to process.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2cae3-113">返回值</span><span class="sxs-lookup"><span data-stu-id="2cae3-113">Return value</span></span>

<span data-ttu-id="2cae3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2cae3-114">S_OK</span></span> 
  
> <span data-ttu-id="2cae3-115">后置处理成功。</span><span class="sxs-lookup"><span data-stu-id="2cae3-115">The postprocessing was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2cae3-116">备注</span><span class="sxs-lookup"><span data-stu-id="2cae3-116">Remarks</span></span>

<span data-ttu-id="2cae3-117">**IMAPISupport：：CompleteMsg** 方法针对邮件存储提供程序支持对象实现，并且仅由与传输提供程序紧密耦合的邮件存储提供程序调用。</span><span class="sxs-lookup"><span data-stu-id="2cae3-117">The **IMAPISupport::CompleteMsg** method is implemented for message store provider support objects and is called only by message store providers that are tightly coupled with transport providers.</span></span> <span data-ttu-id="2cae3-118">紧密耦合存储提供程序调用 **IMAPISupport：：CompleteMsg** 以指示 MAPI 后台处理程序对消息进行后处理。</span><span class="sxs-lookup"><span data-stu-id="2cae3-118">Tightly coupled store providers call **IMAPISupport::CompleteMsg** to instruct the MAPI spooler to postprocess a message.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="2cae3-119">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2cae3-119">Notes to callers</span></span>

<span data-ttu-id="2cae3-120">只有在与传输提供程序紧密结合时，才能调用 **CompleteMsg，** 才能处理邮件的所有收件人，并且存在下列条件之一：</span><span class="sxs-lookup"><span data-stu-id="2cae3-120">Call **CompleteMsg** only when you are tightly coupled with a transport provider, you can handle all of the message's recipients, and one of the following conditions exists:</span></span> 
  
- <span data-ttu-id="2cae3-121">邮件已预处理。</span><span class="sxs-lookup"><span data-stu-id="2cae3-121">The message was preprocessed.</span></span>
    
- <span data-ttu-id="2cae3-122">邮件需要 MAPI 后台处理程序进行后处理。</span><span class="sxs-lookup"><span data-stu-id="2cae3-122">The message requires postprocessing by the MAPI spooler.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2cae3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cae3-123">See also</span></span>



[<span data-ttu-id="2cae3-124">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2cae3-124">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

