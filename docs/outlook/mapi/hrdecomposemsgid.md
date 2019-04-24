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
ms.openlocfilehash: bff73ee5cf02680a2376106e21e0c743b995d336
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348088"
---
# <a name="hrdecomposemsgid"></a><span data-ttu-id="79694-103">HrDecomposeMsgID</span><span class="sxs-lookup"><span data-stu-id="79694-103">HrDecomposeMsgID</span></span>

  
  
<span data-ttu-id="79694-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79694-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79694-105">将对象的复合条目标识符 (通常是邮件存储区中的邮件) 的 ASCII 表示形式分离到存储区中该对象的条目标识符和存储的条目标识符中。</span><span class="sxs-lookup"><span data-stu-id="79694-105">Separates the ASCII representation of the compound entry identifier of an object, usually a message in a message store, into the entry identifier of that object in the store and the store's entry identifier.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="79694-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="79694-106">Header file:</span></span>  <br/> |<span data-ttu-id="79694-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="79694-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="79694-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="79694-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="79694-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="79694-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="79694-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="79694-110">Called by:</span></span>  <br/> |<span data-ttu-id="79694-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="79694-111">Client applications</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="79694-112">参数</span><span class="sxs-lookup"><span data-stu-id="79694-112">Parameters</span></span>

 <span data-ttu-id="79694-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="79694-113">_psession_</span></span>
  
> <span data-ttu-id="79694-114">实时指向客户端应用程序正在使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="79694-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="79694-115">_szMsgID_</span><span class="sxs-lookup"><span data-stu-id="79694-115">_szMsgID_</span></span>
  
> <span data-ttu-id="79694-116">实时表示对象的条目标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="79694-116">[in] The string representing the entry identifier of the object.</span></span> 
    
 <span data-ttu-id="79694-117">_pcbStoreEID_</span><span class="sxs-lookup"><span data-stu-id="79694-117">_pcbStoreEID_</span></span>
  
> <span data-ttu-id="79694-118">排除指向包含该对象的邮件存储区的条目标识符的返回大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="79694-118">[out] Pointer to the returned size, in bytes, of the entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="79694-119">如果_szMsgID_参数指向 noncompound 条目标识符字符串, 则_pcbStoreEID_参数将指向零。</span><span class="sxs-lookup"><span data-stu-id="79694-119">If the  _szMsgID_ parameter points to a noncompound entry identifier string, then the  _pcbStoreEID_ parameter points to zero.</span></span> 
    
 <span data-ttu-id="79694-120">_ppStoreEID_</span><span class="sxs-lookup"><span data-stu-id="79694-120">_ppStoreEID_</span></span>
  
> <span data-ttu-id="79694-121">排除指向指向包含该对象的邮件存储区的返回项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="79694-121">[out] Pointer to a pointer to the returned entry identifier of the message store that contains the object.</span></span> <span data-ttu-id="79694-122">如果_szMsgID_参数指向 noncompound 条目标识符, 则在_ppStoreEID_参数中返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="79694-122">If the  _szMsgID_ parameter points to a noncompound entry identifier, NULL is returned in the  _ppStoreEID_ parameter.</span></span> 
    
 <span data-ttu-id="79694-123">_pcbMsgEID_</span><span class="sxs-lookup"><span data-stu-id="79694-123">_pcbMsgEID_</span></span>
  
> <span data-ttu-id="79694-124">排除指向其存储中的对象的条目标识符的返回大小 (以字节为单位) 的指针。</span><span class="sxs-lookup"><span data-stu-id="79694-124">[out] Pointer to the returned size, in bytes, of the entry identifier of the object within its store.</span></span> <span data-ttu-id="79694-125">如果_szMsgID_参数指向 noncompound 条目标识符字符串, 则_pcbMsgEID_参数等于_cbEID_参数的值。</span><span class="sxs-lookup"><span data-stu-id="79694-125">If the  _szMsgID_ parameter points to a noncompound entry identifier string, then the  _pcbMsgEID_ parameter is equal to the value of the  _cbEID_ parameter.</span></span> 
    
 <span data-ttu-id="79694-126">_ppMsgEID_</span><span class="sxs-lookup"><span data-stu-id="79694-126">_ppMsgEID_</span></span>
  
> <span data-ttu-id="79694-127">排除指向指向其存储中的对象的返回项标识符字符串的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="79694-127">[out] Pointer to a pointer to the returned entry identifier string of the object within its store.</span></span> <span data-ttu-id="79694-128">如果_szMsgID_参数指向 noncompound 条目标识符, 则_ppMsgEID_指向指向 noncompound 条目标识符的转换副本的指针。</span><span class="sxs-lookup"><span data-stu-id="79694-128">If the  _szMsgID_ parameter points to a noncompound entry identifier,  _ppMsgEID_ points to a pointer to a converted copy of the noncompound entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="79694-129">返回值</span><span class="sxs-lookup"><span data-stu-id="79694-129">Return value</span></span>

<span data-ttu-id="79694-130">无。</span><span class="sxs-lookup"><span data-stu-id="79694-130">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="79694-131">注解</span><span class="sxs-lookup"><span data-stu-id="79694-131">Remarks</span></span>

<span data-ttu-id="79694-132">如果_szMsgID_参数指定的标识符是复合标识符, 则将其从 ASCII 转换为, 并拆分为其邮件存储区中的对象的条目标识符和存储的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="79694-132">If the identifier specified by the  _szMsgID_ parameter is compound, it is converted from ASCII and split into the entry identifier of the object within its message store and the store's entry identifier.</span></span> <span data-ttu-id="79694-133">Noncompound 条目标识符字符串是简单转换和复制的。</span><span class="sxs-lookup"><span data-stu-id="79694-133">Noncompound entry identifier strings are simply converted and copied.</span></span> <span data-ttu-id="79694-134">要分隔的复合标识符字符串通常是由[HrComposeMsgID](hrcomposemsgid.md)函数创建一个。</span><span class="sxs-lookup"><span data-stu-id="79694-134">The compound identifier string to be separated is usually one created by the [HrComposeMsgID](hrcomposemsgid.md) function.</span></span> 
  
<span data-ttu-id="79694-135">调用**HrDecomposeMsgID**函数等效于调用[HrEntryIDFromSz](hrentryidfromsz.md)函数, 然后调用[HrDecomposeEID](hrdecomposeeid.md)函数。</span><span class="sxs-lookup"><span data-stu-id="79694-135">Calling the **HrDecomposeMsgID** function is equivalent to calling the [HrEntryIDFromSz](hrentryidfromsz.md) function and then the [HrDecomposeEID](hrdecomposeeid.md) function.</span></span> 
  

