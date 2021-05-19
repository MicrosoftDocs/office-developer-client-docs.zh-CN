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
ms.openlocfilehash: 385660889c40e5f59dfc015ad92ce6a1398ab0cd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415654"
---
# <a name="sccreateconversationindex"></a><span data-ttu-id="9fd91-103">ScCreateConversationIndex</span><span class="sxs-lookup"><span data-stu-id="9fd91-103">ScCreateConversationIndex</span></span>

  
  
<span data-ttu-id="9fd91-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9fd91-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9fd91-105">指示邮件在消息线程中属于何处。</span><span class="sxs-lookup"><span data-stu-id="9fd91-105">Indicates where in a message thread a message belongs.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9fd91-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="9fd91-106">Header file:</span></span>  <br/> |<span data-ttu-id="9fd91-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="9fd91-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="9fd91-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="9fd91-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="9fd91-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="9fd91-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="9fd91-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="9fd91-110">Called by:</span></span>  <br/> |<span data-ttu-id="9fd91-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="9fd91-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE ScCreateConversationIndex(
  ULONG cbParent,
  LPBYTE lpbParent,
  ULONG FAR* lpcbIndex,
  LPBYTE FAR * lppbIndex
);
```

## <a name="parameters"></a><span data-ttu-id="9fd91-112">参数</span><span class="sxs-lookup"><span data-stu-id="9fd91-112">Parameters</span></span>

 <span data-ttu-id="9fd91-113">_cbParent_</span><span class="sxs-lookup"><span data-stu-id="9fd91-113">_cbParent_</span></span>
  
> <span data-ttu-id="9fd91-114">[in]父对话索引中的字节数。</span><span class="sxs-lookup"><span data-stu-id="9fd91-114">[in] Count of bytes in the parent conversation index.</span></span>
    
 <span data-ttu-id="9fd91-115">_lpbParent_</span><span class="sxs-lookup"><span data-stu-id="9fd91-115">_lpbParent_</span></span>
  
> <span data-ttu-id="9fd91-116">[in]指向父对话索引中的字节的指针。</span><span class="sxs-lookup"><span data-stu-id="9fd91-116">[in] Pointer to bytes in the parent conversation index.</span></span> <span data-ttu-id="9fd91-117">如果  _cbParent 为零，则此_ 参数可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9fd91-117">This may be NULL if  _cbParent_ is zero.</span></span> 
    
 <span data-ttu-id="9fd91-118">_lpcbIndex_</span><span class="sxs-lookup"><span data-stu-id="9fd91-118">_lpcbIndex_</span></span>
  
> <span data-ttu-id="9fd91-119">[out]指向调用返回的新对话索引中的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="9fd91-119">[out] Pointer to the count of bytes in the new conversation index returned by the call.</span></span> 
    
 <span data-ttu-id="9fd91-120">_lppbIndex_</span><span class="sxs-lookup"><span data-stu-id="9fd91-120">_lppbIndex_</span></span>
  
> <span data-ttu-id="9fd91-121">[out]指向指向调用返回的新对话索引的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9fd91-121">[out] Pointer to a pointer to the new conversation index returned by the call.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9fd91-122">返回值</span><span class="sxs-lookup"><span data-stu-id="9fd91-122">Return value</span></span>

<span data-ttu-id="9fd91-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="9fd91-123">S_OK</span></span> 
  
> <span data-ttu-id="9fd91-124">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="9fd91-124">The call succeeded and has returned the expected value or values.</span></span>
    

