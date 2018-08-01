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
ms.openlocfilehash: e66d48b6caefe0fee67f41ea829db3201751cf27
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775160"
---
# <a name="hrdecomposeeid"></a><span data-ttu-id="0c229-103">HrDecomposeEID</span><span class="sxs-lookup"><span data-stu-id="0c229-103">HrDecomposeEID</span></span>

  
  
<span data-ttu-id="0c229-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0c229-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0c229-105">将一个对象，通常一条消息的消息存储的复合条目标识符分为存储区中对象的项标识符和存储的项标识符。</span><span class="sxs-lookup"><span data-stu-id="0c229-105">Separates the compound entry identifier of an object, usually a message in a message store, into the entry identifier of that object in the store and the store's entry identifier.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0c229-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="0c229-106">Header file:</span></span>  <br/> |<span data-ttu-id="0c229-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="0c229-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="0c229-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="0c229-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="0c229-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="0c229-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="0c229-110">调用：</span><span class="sxs-lookup"><span data-stu-id="0c229-110">Called by:</span></span>  <br/> |<span data-ttu-id="0c229-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="0c229-111">Client applications</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="0c229-112">参数</span><span class="sxs-lookup"><span data-stu-id="0c229-112">Parameters</span></span>

 <span data-ttu-id="0c229-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="0c229-113">_psession_</span></span>
  
> <span data-ttu-id="0c229-114">[in]加入会话，使用客户端应用程序的指针。</span><span class="sxs-lookup"><span data-stu-id="0c229-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="0c229-115">_cbEID_</span><span class="sxs-lookup"><span data-stu-id="0c229-115">_cbEID_</span></span>
  
> <span data-ttu-id="0c229-116">[in]大小 （以字节为单位的复合条目标识符来分隔）。</span><span class="sxs-lookup"><span data-stu-id="0c229-116">[in] Size, in bytes, of the compound entry identifier to be separated.</span></span> 
    
 <span data-ttu-id="0c229-117">_pEID_</span><span class="sxs-lookup"><span data-stu-id="0c229-117">_pEID_</span></span>
  
> <span data-ttu-id="0c229-118">[in]指向要分隔的复合项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="0c229-118">[in] Pointer to the compound entry identifier to be separated.</span></span> 
    
 <span data-ttu-id="0c229-119">_pcbStoreEID_</span><span class="sxs-lookup"><span data-stu-id="0c229-119">_pcbStoreEID_</span></span>
  
> <span data-ttu-id="0c229-120">[输出]指向返回的大小，以字节为单位的项标识符的消息存储库包含对象的指针。</span><span class="sxs-lookup"><span data-stu-id="0c229-120">[out] Pointer to the returned size, in bytes, of the entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="0c229-121">如果_pEID_参数指向的非复合条目标识符， _pcbStoreEID_参数指向值为零。</span><span class="sxs-lookup"><span data-stu-id="0c229-121">If the  _pEID_ parameter points to a noncompound entry identifier, then the  _pcbStoreEID_ parameter points to a value of zero.</span></span> 
    
 <span data-ttu-id="0c229-122">_ppStoreEID_</span><span class="sxs-lookup"><span data-stu-id="0c229-122">_ppStoreEID_</span></span>
  
> <span data-ttu-id="0c229-123">[输出]为返回的项标识符的消息存储库包含对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="0c229-123">[out] Pointer to a pointer to the returned entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="0c229-124">如果_pEID_参数指向的非复合条目标识符，则_ppStoreEID_参数中返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="0c229-124">If the  _pEID_ parameter points to a noncompound entry identifier, NULL is returned in the  _ppStoreEID_ parameter.</span></span> 
    
 <span data-ttu-id="0c229-125">_pcbMsgEID_</span><span class="sxs-lookup"><span data-stu-id="0c229-125">_pcbMsgEID_</span></span>
  
> <span data-ttu-id="0c229-126">[输出]指向返回的大小，以字节为单位的对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="0c229-126">[out] Pointer to the returned size, in bytes, of the entry identifier of the object.</span></span> <span data-ttu-id="0c229-127">如果_pEID_参数指向的非复合条目标识符， _pcbMsgEID_参数等于_cbEID_参数的值。</span><span class="sxs-lookup"><span data-stu-id="0c229-127">If the  _pEID_ parameter points to a noncompound entry identifier, then the  _pcbMsgEID_ parameter is equal to the value of the  _cbEID_ parameter.</span></span> 
    
 <span data-ttu-id="0c229-128">_ppMsgEID_</span><span class="sxs-lookup"><span data-stu-id="0c229-128">_ppMsgEID_</span></span>
  
> <span data-ttu-id="0c229-129">[输出]指向与返回的项标识符的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="0c229-129">[out] Pointer to a pointer to the returned entry identifier of the object.</span></span> <span data-ttu-id="0c229-130">如果_pEID_参数指向的非复合条目标识符， _ppMsgEID_指向到非复合项标识符的副本的指针。</span><span class="sxs-lookup"><span data-stu-id="0c229-130">If the  _pEID_ parameter points to a noncompound entry identifier,  _ppMsgEID_ points to a pointer to a copy of the noncompound entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0c229-131">返回值</span><span class="sxs-lookup"><span data-stu-id="0c229-131">Return value</span></span>

<span data-ttu-id="0c229-132">无。</span><span class="sxs-lookup"><span data-stu-id="0c229-132">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0c229-133">说明</span><span class="sxs-lookup"><span data-stu-id="0c229-133">Remarks</span></span>

<span data-ttu-id="0c229-134">如果复合_pEID_参数指定的标识符，它被拆分对象在其消息存储库中的项标识符和存储的项标识符。</span><span class="sxs-lookup"><span data-stu-id="0c229-134">If the identifier specified by the  _pEID_ parameter is compound, it is split into the entry identifier of the object within its message store and the store's entry identifier.</span></span> <span data-ttu-id="0c229-135">非复合条目标识符字符串是简单复制。</span><span class="sxs-lookup"><span data-stu-id="0c229-135">Noncompound entry identifier strings are simply copied.</span></span> <span data-ttu-id="0c229-136">要分隔的复合标识符通常是一个[HrComposeEID](hrcomposeeid.md)函数创建。</span><span class="sxs-lookup"><span data-stu-id="0c229-136">The compound identifier to be separated is usually one created by the [HrComposeEID](hrcomposeeid.md) function.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0c229-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0c229-137">Notes to callers</span></span>

<span data-ttu-id="0c229-138">成功完成此函数时释放保留_pEID_参数的内存。</span><span class="sxs-lookup"><span data-stu-id="0c229-138">The memory that holds the  _pEID_ parameter is released upon successful completion of this function.</span></span> <span data-ttu-id="0c229-139">调用实现负责释放内存输出参数。</span><span class="sxs-lookup"><span data-stu-id="0c229-139">The calling implementation is responsible for freeing memory for the output parameters.</span></span> 
  

