---
title: HrDecomposeMsgID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrDecomposeMsgID
api_type:
- COM
ms.assetid: 5e6a9f3e-79be-4ffd-9d42-3a14cabb1435
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 828d7ebcbceead02441165e3af92ec7b47d9f001
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564624"
---
# <a name="hrdecomposemsgid"></a><span data-ttu-id="3dc32-103">HrDecomposeMsgID</span><span class="sxs-lookup"><span data-stu-id="3dc32-103">HrDecomposeMsgID</span></span>

  
  
<span data-ttu-id="3dc32-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3dc32-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3dc32-105">用于分隔 ASCII 标识符的表示形式复合条目的对象，通常一条消息的消息存储，该对象存储区中的项标识符和存储的项标识符。</span><span class="sxs-lookup"><span data-stu-id="3dc32-105">Separates the ASCII representation of the compound entry identifier of an object, usually a message in a message store, into the entry identifier of that object in the store and the store's entry identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3dc32-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="3dc32-106">Header file:</span></span>  <br/> |<span data-ttu-id="3dc32-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="3dc32-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="3dc32-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="3dc32-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="3dc32-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="3dc32-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="3dc32-110">调用：</span><span class="sxs-lookup"><span data-stu-id="3dc32-110">Called by:</span></span>  <br/> |<span data-ttu-id="3dc32-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="3dc32-111">Client applications</span></span>  <br/> |
   
```cpp
HrDecomposeMsgID(
  LPMAPISESSION psession,
  LPSTR szMsgID,
  ULONG FAR * pcbStoreEID,
  LPENTRYID FAR * ppStoreEID,
  ULONG FAR * pcbMsgEID,
  LPENTRYID FAR * ppMsgEID
);
```

## <a name="parameters"></a><span data-ttu-id="3dc32-112">参数</span><span class="sxs-lookup"><span data-stu-id="3dc32-112">Parameters</span></span>

 <span data-ttu-id="3dc32-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="3dc32-113">_psession_</span></span>
  
> <span data-ttu-id="3dc32-114">[in]加入会话，使用客户端应用程序的指针。</span><span class="sxs-lookup"><span data-stu-id="3dc32-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="3dc32-115">_szMsgID_</span><span class="sxs-lookup"><span data-stu-id="3dc32-115">_szMsgID_</span></span>
  
> <span data-ttu-id="3dc32-116">[in]表示对象的项标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="3dc32-116">[in] The string representing the entry identifier of the object.</span></span> 
    
 <span data-ttu-id="3dc32-117">_pcbStoreEID_</span><span class="sxs-lookup"><span data-stu-id="3dc32-117">_pcbStoreEID_</span></span>
  
> <span data-ttu-id="3dc32-118">[输出]指向返回的大小，以字节为单位的项标识符的消息存储库包含对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3dc32-118">[out] Pointer to the returned size, in bytes, of the entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="3dc32-119">如果_szMsgID_参数指向的非复合条目标识符字符串，然后为零的_pcbStoreEID_参数点。</span><span class="sxs-lookup"><span data-stu-id="3dc32-119">If the  _szMsgID_ parameter points to a noncompound entry identifier string, then the  _pcbStoreEID_ parameter points to zero.</span></span> 
    
 <span data-ttu-id="3dc32-120">_ppStoreEID_</span><span class="sxs-lookup"><span data-stu-id="3dc32-120">_ppStoreEID_</span></span>
  
> <span data-ttu-id="3dc32-121">[输出]为返回的项标识符的消息存储库包含对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3dc32-121">[out] Pointer to a pointer to the returned entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="3dc32-122">如果_szMsgID_参数指向的非复合条目标识符，则_ppStoreEID_参数中返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="3dc32-122">If the  _szMsgID_ parameter points to a noncompound entry identifier, NULL is returned in the  _ppStoreEID_ parameter.</span></span> 
    
 <span data-ttu-id="3dc32-123">_pcbMsgEID_</span><span class="sxs-lookup"><span data-stu-id="3dc32-123">_pcbMsgEID_</span></span>
  
> <span data-ttu-id="3dc32-124">[输出]对返回的大小，以字节为单位，该对象在其存储区中的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="3dc32-124">[out] Pointer to the returned size, in bytes, of the entry identifier of the object within its store.</span></span> <span data-ttu-id="3dc32-125">如果_szMsgID_参数指向非复合条目标识符字符串， _pcbMsgEID_参数等于_cbEID_参数的值。</span><span class="sxs-lookup"><span data-stu-id="3dc32-125">If the  _szMsgID_ parameter points to a noncompound entry identifier string, then the  _pcbMsgEID_ parameter is equal to the value of the  _cbEID_ parameter.</span></span> 
    
 <span data-ttu-id="3dc32-126">_ppMsgEID_</span><span class="sxs-lookup"><span data-stu-id="3dc32-126">_ppMsgEID_</span></span>
  
> <span data-ttu-id="3dc32-127">[输出]为其存储中的对象的返回的项标识符字符串指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3dc32-127">[out] Pointer to a pointer to the returned entry identifier string of the object within its store.</span></span> <span data-ttu-id="3dc32-128">如果_szMsgID_参数指向的非复合条目标识符， _ppMsgEID_指向到非复合项标识符的转换后副本的指针。</span><span class="sxs-lookup"><span data-stu-id="3dc32-128">If the  _szMsgID_ parameter points to a noncompound entry identifier,  _ppMsgEID_ points to a pointer to a converted copy of the noncompound entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3dc32-129">返回值</span><span class="sxs-lookup"><span data-stu-id="3dc32-129">Return value</span></span>

<span data-ttu-id="3dc32-130">无。</span><span class="sxs-lookup"><span data-stu-id="3dc32-130">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3dc32-131">注解</span><span class="sxs-lookup"><span data-stu-id="3dc32-131">Remarks</span></span>

<span data-ttu-id="3dc32-132">如果复合_szMsgID_参数指定的标识符，它是从 ASCII 转换，拆分成对象在其消息存储库中的项标识符和存储的项标识符。</span><span class="sxs-lookup"><span data-stu-id="3dc32-132">If the identifier specified by the  _szMsgID_ parameter is compound, it is converted from ASCII and split into the entry identifier of the object within its message store and the store's entry identifier.</span></span> <span data-ttu-id="3dc32-133">只需转换并复制将非复合条目标识符字符串。</span><span class="sxs-lookup"><span data-stu-id="3dc32-133">Noncompound entry identifier strings are simply converted and copied.</span></span> <span data-ttu-id="3dc32-134">要分隔的复合标识符字符串通常是一个[HrComposeMsgID](hrcomposemsgid.md)函数创建。</span><span class="sxs-lookup"><span data-stu-id="3dc32-134">The compound identifier string to be separated is usually one created by the [HrComposeMsgID](hrcomposemsgid.md) function.</span></span> 
  
<span data-ttu-id="3dc32-135">调用**HrDecomposeMsgID**函数等效于调用[HrEntryIDFromSz](hrentryidfromsz.md)函数，然后选择[HrDecomposeEID](hrdecomposeeid.md)函数。</span><span class="sxs-lookup"><span data-stu-id="3dc32-135">Calling the **HrDecomposeMsgID** function is equivalent to calling the [HrEntryIDFromSz](hrentryidfromsz.md) function and then the [HrDecomposeEID](hrdecomposeeid.md) function.</span></span> 
  

