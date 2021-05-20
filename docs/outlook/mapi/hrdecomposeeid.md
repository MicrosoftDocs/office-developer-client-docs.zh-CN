---
title: HrDecomposeEID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrDecomposeEID
api_type:
- COM
ms.assetid: 4847838a-2ad8-4927-8f78-7fa5c8eb54eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d3ef8b61b6042d9c3e715168d9131a74facef000
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436109"
---
# <a name="hrdecomposeeid"></a><span data-ttu-id="d74db-103">HrDecomposeEID</span><span class="sxs-lookup"><span data-stu-id="d74db-103">HrDecomposeEID</span></span>

  
  
<span data-ttu-id="d74db-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d74db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d74db-105">将对象（通常是邮件存储中的邮件）的复合条目标识符分隔到存储中的该对象的条目标识符和存储区的条目标识符中。</span><span class="sxs-lookup"><span data-stu-id="d74db-105">Separates the compound entry identifier of an object, usually a message in a message store, into the entry identifier of that object in the store and the store's entry identifier.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d74db-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d74db-106">Header file:</span></span>  <br/> |<span data-ttu-id="d74db-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="d74db-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="d74db-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="d74db-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d74db-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d74db-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d74db-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="d74db-110">Called by:</span></span>  <br/> |<span data-ttu-id="d74db-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="d74db-111">Client applications</span></span>  <br/> |
   
```cpp
HrDecomposeEID(
  LPMAPISESSION psession,
  ULONG cbEID,
  LPENTRYID pEID,
  ULONG FAR * pcbStoreEID,
  LPENTRYID FAR * ppStoreEID,
  ULONG FAR * pcbMsgEID,
  LPENTRYID FAR * ppMsgEID
);
```

## <a name="parameters"></a><span data-ttu-id="d74db-112">参数</span><span class="sxs-lookup"><span data-stu-id="d74db-112">Parameters</span></span>

 <span data-ttu-id="d74db-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="d74db-113">_psession_</span></span>
  
> <span data-ttu-id="d74db-114">[in]指向客户端应用程序使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="d74db-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="d74db-115">_cbEID_</span><span class="sxs-lookup"><span data-stu-id="d74db-115">_cbEID_</span></span>
  
> <span data-ttu-id="d74db-116">[in]要分隔的复合条目标识符的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d74db-116">[in] Size, in bytes, of the compound entry identifier to be separated.</span></span> 
    
 <span data-ttu-id="d74db-117">_pEID_</span><span class="sxs-lookup"><span data-stu-id="d74db-117">_pEID_</span></span>
  
> <span data-ttu-id="d74db-118">[in]指向要分隔的复合条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="d74db-118">[in] Pointer to the compound entry identifier to be separated.</span></span> 
    
 <span data-ttu-id="d74db-119">_分列存储 ID_</span><span class="sxs-lookup"><span data-stu-id="d74db-119">_pcbStoreEID_</span></span>
  
> <span data-ttu-id="d74db-120">[out]指向包含对象的邮件存储的条目标识符的返回大小（以字节为单位）的指针。</span><span class="sxs-lookup"><span data-stu-id="d74db-120">[out] Pointer to the returned size, in bytes, of the entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="d74db-121">如果  _pEID_ 参数指向一个非编译项标识符，则这些  _pEID_ 参数指向一个零值。</span><span class="sxs-lookup"><span data-stu-id="d74db-121">If the  _pEID_ parameter points to a noncompound entry identifier, then the  _pcbStoreEID_ parameter points to a value of zero.</span></span> 
    
 <span data-ttu-id="d74db-122">_ppStoreEID_</span><span class="sxs-lookup"><span data-stu-id="d74db-122">_ppStoreEID_</span></span>
  
> <span data-ttu-id="d74db-123">[out]指向指向包含对象的邮件存储的返回条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="d74db-123">[out] Pointer to a pointer to the returned entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="d74db-124">如果  _pEID_ 参数指向非编译项标识符，则  _ppStoreEID_ 参数中返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="d74db-124">If the  _pEID_ parameter points to a noncompound entry identifier, NULL is returned in the  _ppStoreEID_ parameter.</span></span> 
    
 <span data-ttu-id="d74db-125">_atmMsgEID_</span><span class="sxs-lookup"><span data-stu-id="d74db-125">_pcbMsgEID_</span></span>
  
> <span data-ttu-id="d74db-126">[out]指向对象条目标识符的返回大小（以字节为单位）的指针。</span><span class="sxs-lookup"><span data-stu-id="d74db-126">[out] Pointer to the returned size, in bytes, of the entry identifier of the object.</span></span> <span data-ttu-id="d74db-127">如果  _pEID_ 参数指向一个非编译项标识符，则该  _pMsgEID_ 参数等于  _cbEID 参数_ 的值。</span><span class="sxs-lookup"><span data-stu-id="d74db-127">If the  _pEID_ parameter points to a noncompound entry identifier, then the  _pcbMsgEID_ parameter is equal to the value of the  _cbEID_ parameter.</span></span> 
    
 <span data-ttu-id="d74db-128">_ppMsgEID_</span><span class="sxs-lookup"><span data-stu-id="d74db-128">_ppMsgEID_</span></span>
  
> <span data-ttu-id="d74db-129">[out]指向对象的返回条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d74db-129">[out] Pointer to a pointer to the returned entry identifier of the object.</span></span> <span data-ttu-id="d74db-130">如果  _pEID_ 参数指向非编译项标识符，  _则 ppMsgEID_ 指向指向非编译项标识符副本的指针。</span><span class="sxs-lookup"><span data-stu-id="d74db-130">If the  _pEID_ parameter points to a noncompound entry identifier,  _ppMsgEID_ points to a pointer to a copy of the noncompound entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d74db-131">返回值</span><span class="sxs-lookup"><span data-stu-id="d74db-131">Return value</span></span>

<span data-ttu-id="d74db-132">无。</span><span class="sxs-lookup"><span data-stu-id="d74db-132">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d74db-133">说明</span><span class="sxs-lookup"><span data-stu-id="d74db-133">Remarks</span></span>

<span data-ttu-id="d74db-134">如果  _pEID_ 参数指定的标识符是复合标识符，则它将拆分为对象在其邮件存储中的条目标识符和存储的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d74db-134">If the identifier specified by the  _pEID_ parameter is compound, it is split into the entry identifier of the object within its message store and the store's entry identifier.</span></span> <span data-ttu-id="d74db-135">仅复制未编译的条目标识符字符串。</span><span class="sxs-lookup"><span data-stu-id="d74db-135">Noncompound entry identifier strings are simply copied.</span></span> <span data-ttu-id="d74db-136">要分隔的复合标识符通常由 [HrComposeEID](hrcomposeeid.md) 函数创建。</span><span class="sxs-lookup"><span data-stu-id="d74db-136">The compound identifier to be separated is usually one created by the [HrComposeEID](hrcomposeeid.md) function.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d74db-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d74db-137">Notes to callers</span></span>

<span data-ttu-id="d74db-138">保留  _pEID_ 参数的内存在成功完成此函数后释放。</span><span class="sxs-lookup"><span data-stu-id="d74db-138">The memory that holds the  _pEID_ parameter is released upon successful completion of this function.</span></span> <span data-ttu-id="d74db-139">调用实现负责为输出参数释放内存。</span><span class="sxs-lookup"><span data-stu-id="d74db-139">The calling implementation is responsible for freeing memory for the output parameters.</span></span> 
  

