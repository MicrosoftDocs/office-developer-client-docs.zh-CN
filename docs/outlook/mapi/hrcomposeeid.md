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
ms.openlocfilehash: 7de4fdefee67c79fb15ac28f821b015cdda6708d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429045"
---
# <a name="hrcomposeeid"></a><span data-ttu-id="8c67a-103">HrComposeEID</span><span class="sxs-lookup"><span data-stu-id="8c67a-103">HrComposeEID</span></span>

  
  
<span data-ttu-id="8c67a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8c67a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8c67a-105">为对象 (通常是邮件存储区中的邮件) 创建复合条目标识符。</span><span class="sxs-lookup"><span data-stu-id="8c67a-105">Creates a compound entry identifier for an object, usually a message in a message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8c67a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="8c67a-106">Header file:</span></span>  <br/> |<span data-ttu-id="8c67a-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="8c67a-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="8c67a-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="8c67a-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="8c67a-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="8c67a-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="8c67a-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="8c67a-110">Called by:</span></span>  <br/> |<span data-ttu-id="8c67a-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="8c67a-111">Client applications</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="8c67a-112">参数</span><span class="sxs-lookup"><span data-stu-id="8c67a-112">Parameters</span></span>

 <span data-ttu-id="8c67a-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="8c67a-113">_psession_</span></span>
  
> <span data-ttu-id="8c67a-114">实时指向客户端应用程序正在使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="8c67a-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="8c67a-115">_cbStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="8c67a-115">_cbStoreRecordKey_</span></span>
  
> <span data-ttu-id="8c67a-116">实时包含邮件或其他对象的邮件存储区的记录键的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="8c67a-116">[in] Size, in bytes, of the record key of the message store holding the message or other object.</span></span> <span data-ttu-id="8c67a-117">如果在_cbStoreRecordKey_参数中传递零, 则_ppEID_参数指向对象的条目标识符的副本。</span><span class="sxs-lookup"><span data-stu-id="8c67a-117">If zero is passed in the  _cbStoreRecordKey_ parameter, the  _ppEID_ parameter points to a copy of the object's entry identifier.</span></span> 
    
 <span data-ttu-id="8c67a-118">_pStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="8c67a-118">_pStoreRecordKey_</span></span>
  
> <span data-ttu-id="8c67a-119">实时指向邮件存储区中包含邮件或其他对象的记录键的指针。</span><span class="sxs-lookup"><span data-stu-id="8c67a-119">[in] Pointer to the record key of the message store that contains the message or other object.</span></span> 
    
 <span data-ttu-id="8c67a-120">_cbMsgEID_</span><span class="sxs-lookup"><span data-stu-id="8c67a-120">_cbMsgEID_</span></span>
  
> <span data-ttu-id="8c67a-121">实时邮件或其他对象的条目标识符的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="8c67a-121">[in] Size, in bytes, of the entry identifier of the message or other object.</span></span> 
    
 <span data-ttu-id="8c67a-122">_pMsgEID_</span><span class="sxs-lookup"><span data-stu-id="8c67a-122">_pMsgEID_</span></span>
  
> <span data-ttu-id="8c67a-123">实时指向对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="8c67a-123">[in] Pointer to the entry identifier of the object.</span></span> 
    
 <span data-ttu-id="8c67a-124">_pcbEID_</span><span class="sxs-lookup"><span data-stu-id="8c67a-124">_pcbEID_</span></span>
  
> <span data-ttu-id="8c67a-125">排除指向返回的标识符的大小 (以字节为单位) 的指针。</span><span class="sxs-lookup"><span data-stu-id="8c67a-125">[out] Pointer to the size, in bytes, of the returned identifier.</span></span> 
    
 <span data-ttu-id="8c67a-126">_ppEID_</span><span class="sxs-lookup"><span data-stu-id="8c67a-126">_ppEID_</span></span>
  
> <span data-ttu-id="8c67a-127">排除指向指向返回的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8c67a-127">[out] Pointer to a pointer to the returned entry identifier.</span></span> <span data-ttu-id="8c67a-128">如果_cbStoreRecordKey_参数的值大于零, 则_ppEID_参数指向所创建的复合条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="8c67a-128">If the value of the  _cbStoreRecordKey_ parameter is greater than zero, the  _ppEID_ parameter points to a pointer to the compound entry identifier that is created.</span></span> <span data-ttu-id="8c67a-129">如果_cbStoreRecordKey_为零, 则_ppEID_指向指向对象的条目标识符副本的指针。</span><span class="sxs-lookup"><span data-stu-id="8c67a-129">If  _cbStoreRecordKey_ is zero,  _ppEID_ points to a pointer to a copy of the object's entry identifier.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="8c67a-130">返回值</span><span class="sxs-lookup"><span data-stu-id="8c67a-130">Return value</span></span>

<span data-ttu-id="8c67a-131">无。</span><span class="sxs-lookup"><span data-stu-id="8c67a-131">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8c67a-132">说明</span><span class="sxs-lookup"><span data-stu-id="8c67a-132">Remarks</span></span>

<span data-ttu-id="8c67a-133">如果要为其创建复合条目标识符的邮件或其他对象驻留在邮件存储区中, 则将从该对象的条目标识符和存储的记录密钥创建该标识符。</span><span class="sxs-lookup"><span data-stu-id="8c67a-133">If the message or other object for which the compound entry identifier is being created resides in a message store, the identifier is created from the object's entry identifier and the store's record key.</span></span> <span data-ttu-id="8c67a-134">如果对象不在 store 中 (即, 如果在_cbStoreRecordKey_中传递的存储记录键的字节数为零), 则只会复制该对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="8c67a-134">If the object is not in a store, that is, if the byte count for the store record key passed in  _cbStoreRecordKey_ is zero, the object's entry identifier is simply copied.</span></span> 
  
<span data-ttu-id="8c67a-135">**HrComposeEID**函数使应用程序能够通过使用复合条目标识符来处理多个存储中的对象。</span><span class="sxs-lookup"><span data-stu-id="8c67a-135">The **HrComposeEID** function enables applications to work with objects in multiple stores through the use of compound entry identifiers.</span></span> <span data-ttu-id="8c67a-136">应用程序可以调用[HrDecomposeEID](hrdecomposeeid.md)函数, 以将复合条目标识符拆分为其原始要素。</span><span class="sxs-lookup"><span data-stu-id="8c67a-136">An application can call the [HrDecomposeEID](hrdecomposeeid.md) function to split the compound entry identifier into its original constituents.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8c67a-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c67a-137">See also</span></span>



[<span data-ttu-id="8c67a-138">HrComposeMsgID</span><span class="sxs-lookup"><span data-stu-id="8c67a-138">HrComposeMsgID</span></span>](hrcomposemsgid.md)
  
[<span data-ttu-id="8c67a-139">HrDecomposeMsgID</span><span class="sxs-lookup"><span data-stu-id="8c67a-139">HrDecomposeMsgID</span></span>](hrdecomposemsgid.md)

