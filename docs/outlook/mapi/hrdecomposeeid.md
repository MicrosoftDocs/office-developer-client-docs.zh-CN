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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348067"
---
# <a name="hrdecomposeeid"></a><span data-ttu-id="aff0d-103">HrDecomposeEID</span><span class="sxs-lookup"><span data-stu-id="aff0d-103">HrDecomposeEID</span></span>

  
  
<span data-ttu-id="aff0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aff0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aff0d-105">将对象的复合条目标识符 (通常是邮件存储区中的邮件) 分隔到存储区中该对象的条目标识符和存储的条目标识符中。</span><span class="sxs-lookup"><span data-stu-id="aff0d-105">Separates the compound entry identifier of an object, usually a message in a message store, into the entry identifier of that object in the store and the store's entry identifier.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="aff0d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="aff0d-106">Header file:</span></span>  <br/> |<span data-ttu-id="aff0d-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="aff0d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="aff0d-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="aff0d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="aff0d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="aff0d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="aff0d-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="aff0d-110">Called by:</span></span>  <br/> |<span data-ttu-id="aff0d-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="aff0d-111">Client applications</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="aff0d-112">参数</span><span class="sxs-lookup"><span data-stu-id="aff0d-112">Parameters</span></span>

 <span data-ttu-id="aff0d-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="aff0d-113">_psession_</span></span>
  
> <span data-ttu-id="aff0d-114">实时指向客户端应用程序正在使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="aff0d-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="aff0d-115">_cbEID_</span><span class="sxs-lookup"><span data-stu-id="aff0d-115">_cbEID_</span></span>
  
> <span data-ttu-id="aff0d-116">实时要分隔的复合条目标识符的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="aff0d-116">[in] Size, in bytes, of the compound entry identifier to be separated.</span></span> 
    
 <span data-ttu-id="aff0d-117">_pEID_</span><span class="sxs-lookup"><span data-stu-id="aff0d-117">_pEID_</span></span>
  
> <span data-ttu-id="aff0d-118">实时指向要分隔的复合条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="aff0d-118">[in] Pointer to the compound entry identifier to be separated.</span></span> 
    
 <span data-ttu-id="aff0d-119">_pcbStoreEID_</span><span class="sxs-lookup"><span data-stu-id="aff0d-119">_pcbStoreEID_</span></span>
  
> <span data-ttu-id="aff0d-120">排除指向包含该对象的邮件存储区的条目标识符的返回大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="aff0d-120">[out] Pointer to the returned size, in bytes, of the entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="aff0d-121">如果_pEID_参数指向 noncompound 条目标识符, 则_pcbStoreEID_参数将指向值0。</span><span class="sxs-lookup"><span data-stu-id="aff0d-121">If the  _pEID_ parameter points to a noncompound entry identifier, then the  _pcbStoreEID_ parameter points to a value of zero.</span></span> 
    
 <span data-ttu-id="aff0d-122">_ppStoreEID_</span><span class="sxs-lookup"><span data-stu-id="aff0d-122">_ppStoreEID_</span></span>
  
> <span data-ttu-id="aff0d-123">排除指向指向包含该对象的邮件存储区的返回项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="aff0d-123">[out] Pointer to a pointer to the returned entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="aff0d-124">如果_pEID_参数指向 noncompound 条目标识符, 则在_ppStoreEID_参数中返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="aff0d-124">If the  _pEID_ parameter points to a noncompound entry identifier, NULL is returned in the  _ppStoreEID_ parameter.</span></span> 
    
 <span data-ttu-id="aff0d-125">_pcbMsgEID_</span><span class="sxs-lookup"><span data-stu-id="aff0d-125">_pcbMsgEID_</span></span>
  
> <span data-ttu-id="aff0d-126">排除指向对象的条目标识符的返回大小 (以字节为单位) 的指针。</span><span class="sxs-lookup"><span data-stu-id="aff0d-126">[out] Pointer to the returned size, in bytes, of the entry identifier of the object.</span></span> <span data-ttu-id="aff0d-127">如果_pEID_参数指向 noncompound 条目标识符, 则_pcbMsgEID_参数等于_cbEID_参数的值。</span><span class="sxs-lookup"><span data-stu-id="aff0d-127">If the  _pEID_ parameter points to a noncompound entry identifier, then the  _pcbMsgEID_ parameter is equal to the value of the  _cbEID_ parameter.</span></span> 
    
 <span data-ttu-id="aff0d-128">_ppMsgEID_</span><span class="sxs-lookup"><span data-stu-id="aff0d-128">_ppMsgEID_</span></span>
  
> <span data-ttu-id="aff0d-129">排除指向指向对象的返回项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="aff0d-129">[out] Pointer to a pointer to the returned entry identifier of the object.</span></span> <span data-ttu-id="aff0d-130">如果_pEID_参数指向 noncompound 条目标识符, 则_ppMsgEID_会指向指向 noncompound 条目标识符副本的指针。</span><span class="sxs-lookup"><span data-stu-id="aff0d-130">If the  _pEID_ parameter points to a noncompound entry identifier,  _ppMsgEID_ points to a pointer to a copy of the noncompound entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="aff0d-131">返回值</span><span class="sxs-lookup"><span data-stu-id="aff0d-131">Return value</span></span>

<span data-ttu-id="aff0d-132">无。</span><span class="sxs-lookup"><span data-stu-id="aff0d-132">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="aff0d-133">注解</span><span class="sxs-lookup"><span data-stu-id="aff0d-133">Remarks</span></span>

<span data-ttu-id="aff0d-134">如果_pEID_参数指定的标识符是复合的, 则会将其拆分为其邮件存储区中的对象的条目标识符和存储的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="aff0d-134">If the identifier specified by the  _pEID_ parameter is compound, it is split into the entry identifier of the object within its message store and the store's entry identifier.</span></span> <span data-ttu-id="aff0d-135">Noncompound 条目标识符字符串只是复制的。</span><span class="sxs-lookup"><span data-stu-id="aff0d-135">Noncompound entry identifier strings are simply copied.</span></span> <span data-ttu-id="aff0d-136">要分隔的复合标识符通常是由[HrComposeEID](hrcomposeeid.md)函数创建的。</span><span class="sxs-lookup"><span data-stu-id="aff0d-136">The compound identifier to be separated is usually one created by the [HrComposeEID](hrcomposeeid.md) function.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="aff0d-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="aff0d-137">Notes to callers</span></span>

<span data-ttu-id="aff0d-138">在成功完成此函数后, 将释放保留_pEID_参数的内存。</span><span class="sxs-lookup"><span data-stu-id="aff0d-138">The memory that holds the  _pEID_ parameter is released upon successful completion of this function.</span></span> <span data-ttu-id="aff0d-139">调用实现负责为输出参数释放内存。</span><span class="sxs-lookup"><span data-stu-id="aff0d-139">The calling implementation is responsible for freeing memory for the output parameters.</span></span> 
  

