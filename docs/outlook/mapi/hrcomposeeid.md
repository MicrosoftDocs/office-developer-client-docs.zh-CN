---
title: HrComposeEID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrComposeEID
api_type:
- COM
ms.assetid: 8aba90d8-ea1f-4636-af80-17bfeadbdfa0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 335fac38ff3f084195a000ad32a27adcb85c1cc6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564813"
---
# <a name="hrcomposeeid"></a><span data-ttu-id="10695-103">HrComposeEID</span><span class="sxs-lookup"><span data-stu-id="10695-103">HrComposeEID</span></span>

  
  
<span data-ttu-id="10695-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="10695-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="10695-105">创建一个对象，通常一条消息的消息存储的复合条目标识符。</span><span class="sxs-lookup"><span data-stu-id="10695-105">Creates a compound entry identifier for an object, usually a message in a message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="10695-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="10695-106">Header file:</span></span>  <br/> |<span data-ttu-id="10695-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="10695-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="10695-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="10695-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="10695-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="10695-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="10695-110">调用：</span><span class="sxs-lookup"><span data-stu-id="10695-110">Called by:</span></span>  <br/> |<span data-ttu-id="10695-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="10695-111">Client applications</span></span>  <br/> |
   
```cpp
HrComposeEID(
  LPMAPISESSION psession,
  ULONG cbStoreRecordKey,
  LPBYTE pStoreRecordKey,
  ULONG cbMsgEID,
  LPENTRYID pMsgEID,
  ULONG FAR * pcbEID,
  LPENTRYID FAR * ppEID
);
```

## <a name="parameters"></a><span data-ttu-id="10695-112">参数</span><span class="sxs-lookup"><span data-stu-id="10695-112">Parameters</span></span>

 <span data-ttu-id="10695-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="10695-113">_psession_</span></span>
  
> <span data-ttu-id="10695-114">[in]加入会话，使用客户端应用程序的指针。</span><span class="sxs-lookup"><span data-stu-id="10695-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="10695-115">_cbStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="10695-115">_cbStoreRecordKey_</span></span>
  
> <span data-ttu-id="10695-116">[in]大小 （以字节为单位，包含邮件或其他对象的消息存储的记录项）。</span><span class="sxs-lookup"><span data-stu-id="10695-116">[in] Size, in bytes, of the record key of the message store holding the message or other object.</span></span> <span data-ttu-id="10695-117">如果_cbStoreRecordKey_参数中传递零，则_ppEID_参数指向对象的项标识符的副本。</span><span class="sxs-lookup"><span data-stu-id="10695-117">If zero is passed in the  _cbStoreRecordKey_ parameter, the  _ppEID_ parameter points to a copy of the object's entry identifier.</span></span> 
    
 <span data-ttu-id="10695-118">_pStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="10695-118">_pStoreRecordKey_</span></span>
  
> <span data-ttu-id="10695-119">[in]向记录项的消息存储库包含邮件或其他对象的指针。</span><span class="sxs-lookup"><span data-stu-id="10695-119">[in] Pointer to the record key of the message store that contains the message or other object.</span></span> 
    
 <span data-ttu-id="10695-120">_cbMsgEID_</span><span class="sxs-lookup"><span data-stu-id="10695-120">_cbMsgEID_</span></span>
  
> <span data-ttu-id="10695-121">[in]大小，以字节为单位的项标识符的邮件或其他对象。</span><span class="sxs-lookup"><span data-stu-id="10695-121">[in] Size, in bytes, of the entry identifier of the message or other object.</span></span> 
    
 <span data-ttu-id="10695-122">_pMsgEID_</span><span class="sxs-lookup"><span data-stu-id="10695-122">_pMsgEID_</span></span>
  
> <span data-ttu-id="10695-123">[in]指向对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="10695-123">[in] Pointer to the entry identifier of the object.</span></span> 
    
 <span data-ttu-id="10695-124">_pcbEID_</span><span class="sxs-lookup"><span data-stu-id="10695-124">_pcbEID_</span></span>
  
> <span data-ttu-id="10695-125">[输出]指向的大小，以字节为单位返回的标识符。</span><span class="sxs-lookup"><span data-stu-id="10695-125">[out] Pointer to the size, in bytes, of the returned identifier.</span></span> 
    
 <span data-ttu-id="10695-126">_ppEID_</span><span class="sxs-lookup"><span data-stu-id="10695-126">_ppEID_</span></span>
  
> <span data-ttu-id="10695-127">[输出]指向与返回的项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="10695-127">[out] Pointer to a pointer to the returned entry identifier.</span></span> <span data-ttu-id="10695-128">如果_cbStoreRecordKey_参数的值大于零， _ppEID_参数指向创建的复合项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="10695-128">If the value of the  _cbStoreRecordKey_ parameter is greater than zero, the  _ppEID_ parameter points to a pointer to the compound entry identifier that is created.</span></span> <span data-ttu-id="10695-129">如果_cbStoreRecordKey_为零， _ppEID_指向到对象的项标识符的副本的指针。</span><span class="sxs-lookup"><span data-stu-id="10695-129">If  _cbStoreRecordKey_ is zero,  _ppEID_ points to a pointer to a copy of the object's entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="10695-130">返回值</span><span class="sxs-lookup"><span data-stu-id="10695-130">Return value</span></span>

<span data-ttu-id="10695-131">无。</span><span class="sxs-lookup"><span data-stu-id="10695-131">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="10695-132">注解</span><span class="sxs-lookup"><span data-stu-id="10695-132">Remarks</span></span>

<span data-ttu-id="10695-133">如果邮件或其他对象为其创建的复合条目标识符位于邮件存储区，从对象的项标识符的存储记录键创建标识符。</span><span class="sxs-lookup"><span data-stu-id="10695-133">If the message or other object for which the compound entry identifier is being created resides in a message store, the identifier is created from the object's entry identifier and the store's record key.</span></span> <span data-ttu-id="10695-134">如果对象不是存储区中，即，如果_cbStoreRecordKey_中传递的存储记录密钥的字节数为零，对象的项标识符是简单复制。</span><span class="sxs-lookup"><span data-stu-id="10695-134">If the object is not in a store, that is, if the byte count for the store record key passed in  _cbStoreRecordKey_ is zero, the object's entry identifier is simply copied.</span></span> 
  
<span data-ttu-id="10695-135">**HrComposeEID**函数使应用程序以使用复合条目标识符使用的多个存储区中的对象。</span><span class="sxs-lookup"><span data-stu-id="10695-135">The **HrComposeEID** function enables applications to work with objects in multiple stores through the use of compound entry identifiers.</span></span> <span data-ttu-id="10695-136">应用程序可以调用[HrDecomposeEID](hrdecomposeeid.md)函数拆分到其原始构成的复合条目标识符。</span><span class="sxs-lookup"><span data-stu-id="10695-136">An application can call the [HrDecomposeEID](hrdecomposeeid.md) function to split the compound entry identifier into its original constituents.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="10695-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10695-137">See also</span></span>



[<span data-ttu-id="10695-138">HrComposeMsgID</span><span class="sxs-lookup"><span data-stu-id="10695-138">HrComposeMsgID</span></span>](hrcomposemsgid.md)
  
[<span data-ttu-id="10695-139">HrDecomposeMsgID</span><span class="sxs-lookup"><span data-stu-id="10695-139">HrDecomposeMsgID</span></span>](hrdecomposemsgid.md)

