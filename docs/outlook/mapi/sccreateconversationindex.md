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
ms.openlocfilehash: 43765cddb2f06bfbe58e0a4000c7eadfdc5f3347
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778700"
---
# <a name="sccreateconversationindex"></a><span data-ttu-id="88775-103">ScCreateConversationIndex</span><span class="sxs-lookup"><span data-stu-id="88775-103">ScCreateConversationIndex</span></span>

  
  
<span data-ttu-id="88775-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="88775-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="88775-105">指示邮件线程中的消息所属的位置。</span><span class="sxs-lookup"><span data-stu-id="88775-105">Indicates where in a message thread a message belongs.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="88775-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="88775-106">Header file:</span></span>  <br/> |<span data-ttu-id="88775-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="88775-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="88775-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="88775-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="88775-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="88775-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="88775-110">调用：</span><span class="sxs-lookup"><span data-stu-id="88775-110">Called by:</span></span>  <br/> |<span data-ttu-id="88775-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="88775-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCreateConversationIndex(
  ULONG cbParent,
  LPBYTE lpbParent,
  ULONG FAR* lpcbIndex,
  LPBYTE FAR * lppbIndex
);
```

## <a name="parameters"></a><span data-ttu-id="88775-112">参数</span><span class="sxs-lookup"><span data-stu-id="88775-112">Parameters</span></span>

 <span data-ttu-id="88775-113">_cbParent_</span><span class="sxs-lookup"><span data-stu-id="88775-113">_cbParent_</span></span>
  
> <span data-ttu-id="88775-114">[in]父对话索引中的字节数。</span><span class="sxs-lookup"><span data-stu-id="88775-114">[in] Count of bytes in the parent conversation index.</span></span>
    
 <span data-ttu-id="88775-115">_lpbParent_</span><span class="sxs-lookup"><span data-stu-id="88775-115">_lpbParent_</span></span>
  
> <span data-ttu-id="88775-116">[in]指向父对话索引中的字节的指针。</span><span class="sxs-lookup"><span data-stu-id="88775-116">[in] Pointer to bytes in the parent conversation index.</span></span> <span data-ttu-id="88775-117">如果_cbParent_为零，这可能是 NULL。</span><span class="sxs-lookup"><span data-stu-id="88775-117">This may be NULL if  _cbParent_ is zero.</span></span> 
    
 <span data-ttu-id="88775-118">_lpcbIndex_</span><span class="sxs-lookup"><span data-stu-id="88775-118">_lpcbIndex_</span></span>
  
> <span data-ttu-id="88775-119">[输出]为新的调用返回的对话索引中的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="88775-119">[out] Pointer to the count of bytes in the new conversation index returned by the call.</span></span> 
    
 <span data-ttu-id="88775-120">_lppbIndex_</span><span class="sxs-lookup"><span data-stu-id="88775-120">_lppbIndex_</span></span>
  
> <span data-ttu-id="88775-121">[输出]为新的对话索引的调用返回指针的指针。</span><span class="sxs-lookup"><span data-stu-id="88775-121">[out] Pointer to a pointer to the new conversation index returned by the call.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="88775-122">返回值</span><span class="sxs-lookup"><span data-stu-id="88775-122">Return value</span></span>

<span data-ttu-id="88775-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="88775-123">S_OK</span></span> 
  
> <span data-ttu-id="88775-124">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="88775-124">The call succeeded and has returned the expected value or values.</span></span>
    

