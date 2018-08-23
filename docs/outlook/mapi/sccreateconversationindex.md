---
title: ScCreateConversationIndex
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCreateConversationIndex
api_type:
- COM
ms.assetid: 3ccfc15d-f3c6-4c7b-b1cc-855af66036de
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5ae0c9f123ade599ca9bc1d3bdea3e9c89cfbc16
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594149"
---
# <a name="sccreateconversationindex"></a><span data-ttu-id="9d31e-103">ScCreateConversationIndex</span><span class="sxs-lookup"><span data-stu-id="9d31e-103">ScCreateConversationIndex</span></span>

  
  
<span data-ttu-id="9d31e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9d31e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9d31e-105">指示邮件线程中的消息所属的位置。</span><span class="sxs-lookup"><span data-stu-id="9d31e-105">Indicates where in a message thread a message belongs.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9d31e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="9d31e-106">Header file:</span></span>  <br/> |<span data-ttu-id="9d31e-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="9d31e-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="9d31e-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="9d31e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="9d31e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="9d31e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="9d31e-110">调用：</span><span class="sxs-lookup"><span data-stu-id="9d31e-110">Called by:</span></span>  <br/> |<span data-ttu-id="9d31e-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="9d31e-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCreateConversationIndex(
  ULONG cbParent,
  LPBYTE lpbParent,
  ULONG FAR* lpcbIndex,
  LPBYTE FAR * lppbIndex
);
```

## <a name="parameters"></a><span data-ttu-id="9d31e-112">参数</span><span class="sxs-lookup"><span data-stu-id="9d31e-112">Parameters</span></span>

 <span data-ttu-id="9d31e-113">_cbParent_</span><span class="sxs-lookup"><span data-stu-id="9d31e-113">_cbParent_</span></span>
  
> <span data-ttu-id="9d31e-114">[in]父对话索引中的字节数。</span><span class="sxs-lookup"><span data-stu-id="9d31e-114">[in] Count of bytes in the parent conversation index.</span></span>
    
 <span data-ttu-id="9d31e-115">_lpbParent_</span><span class="sxs-lookup"><span data-stu-id="9d31e-115">_lpbParent_</span></span>
  
> <span data-ttu-id="9d31e-116">[in]指向父对话索引中的字节的指针。</span><span class="sxs-lookup"><span data-stu-id="9d31e-116">[in] Pointer to bytes in the parent conversation index.</span></span> <span data-ttu-id="9d31e-117">如果_cbParent_为零，这可能是 NULL。</span><span class="sxs-lookup"><span data-stu-id="9d31e-117">This may be NULL if  _cbParent_ is zero.</span></span> 
    
 <span data-ttu-id="9d31e-118">_lpcbIndex_</span><span class="sxs-lookup"><span data-stu-id="9d31e-118">_lpcbIndex_</span></span>
  
> <span data-ttu-id="9d31e-119">[输出]为新的调用返回的对话索引中的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="9d31e-119">[out] Pointer to the count of bytes in the new conversation index returned by the call.</span></span> 
    
 <span data-ttu-id="9d31e-120">_lppbIndex_</span><span class="sxs-lookup"><span data-stu-id="9d31e-120">_lppbIndex_</span></span>
  
> <span data-ttu-id="9d31e-121">[输出]为新的对话索引的调用返回指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9d31e-121">[out] Pointer to a pointer to the new conversation index returned by the call.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9d31e-122">返回值</span><span class="sxs-lookup"><span data-stu-id="9d31e-122">Return value</span></span>

<span data-ttu-id="9d31e-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d31e-123">S_OK</span></span> 
  
> <span data-ttu-id="9d31e-124">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="9d31e-124">The call succeeded and has returned the expected value or values.</span></span>
    

