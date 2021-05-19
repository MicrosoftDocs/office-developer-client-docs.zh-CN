---
title: HrComposeMsgID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrComposeMsgID
api_type:
- COM
ms.assetid: bb76b147-6552-4cc4-920f-699170aea17f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c035780d3d790d94551860a418401e63da1c2151
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424061"
---
# <a name="hrcomposemsgid"></a><span data-ttu-id="7a03d-103">HrComposeMsgID</span><span class="sxs-lookup"><span data-stu-id="7a03d-103">HrComposeMsgID</span></span>

  
  
<span data-ttu-id="7a03d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7a03d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7a03d-105">创建一个 ASCII 字符串，该字符串代表对象（通常是邮件存储中的邮件）的复合条目标识符。</span><span class="sxs-lookup"><span data-stu-id="7a03d-105">Creates an ASCII string representing a compound entry identifier for an object, usually a message in a message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7a03d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7a03d-106">Header file:</span></span>  <br/> |<span data-ttu-id="7a03d-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="7a03d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="7a03d-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="7a03d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="7a03d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="7a03d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="7a03d-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="7a03d-110">Called by:</span></span>  <br/> |<span data-ttu-id="7a03d-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="7a03d-111">Client applications</span></span>  <br/> |
   
```cpp
HrComposeMsgID(
  LPMAPISESSION psession,
  ULONG cbStoreRecordKey,
  LPBYTE pStoreRecordKey,
  ULONG cbMsgEID,
  LPENTRYID pMsgEID,
  LPSTR FAR * pszMsgID
);
```

## <a name="parameters"></a><span data-ttu-id="7a03d-112">参数</span><span class="sxs-lookup"><span data-stu-id="7a03d-112">Parameters</span></span>

 <span data-ttu-id="7a03d-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="7a03d-113">_psession_</span></span>
  
> <span data-ttu-id="7a03d-114">[in]指向客户端应用程序使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="7a03d-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="7a03d-115">_cbStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="7a03d-115">_cbStoreRecordKey_</span></span>
  
> <span data-ttu-id="7a03d-116">[in]包含邮件或其他对象的邮件存储的记录键的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7a03d-116">[in] Size, in bytes, of the record key of the message store that contains the message or other object.</span></span> <span data-ttu-id="7a03d-117">如果在  _cbStoreRecordKey_ 参数中传递零，  _则 pszMsgID_ 参数指向转换为文本的条目标识符的副本。</span><span class="sxs-lookup"><span data-stu-id="7a03d-117">If zero is passed in the  _cbStoreRecordKey_ parameter, the  _pszMsgID_ parameter points to a copy of the entry identifier converted to text.</span></span> 
    
 <span data-ttu-id="7a03d-118">_pStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="7a03d-118">_pStoreRecordKey_</span></span>
  
> <span data-ttu-id="7a03d-119">[in]指向包含邮件或其他对象的邮件存储的记录键的指针。</span><span class="sxs-lookup"><span data-stu-id="7a03d-119">[in] Pointer to the record key of the message store that contains the message or other object.</span></span> 
    
 <span data-ttu-id="7a03d-120">_cbMsgEID_</span><span class="sxs-lookup"><span data-stu-id="7a03d-120">_cbMsgEID_</span></span>
  
> <span data-ttu-id="7a03d-121">[in]邮件或其他对象的条目标识符的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7a03d-121">[in] Size, in bytes, of the entry identifier of the message or other object.</span></span> 
    
 <span data-ttu-id="7a03d-122">_pMsgEID_</span><span class="sxs-lookup"><span data-stu-id="7a03d-122">_pMsgEID_</span></span>
  
> <span data-ttu-id="7a03d-123">[in]指向对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="7a03d-123">[in] Pointer to the entry identifier of the object.</span></span> 
    
 <span data-ttu-id="7a03d-124">_pszMsgID_</span><span class="sxs-lookup"><span data-stu-id="7a03d-124">_pszMsgID_</span></span>
  
> <span data-ttu-id="7a03d-125">[out]指向返回的 ASCII 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="7a03d-125">[out] Pointer to the returned ASCII string.</span></span> <span data-ttu-id="7a03d-126">如果  _cbStoreRecordKey_ 参数大于零，则  _pszMsgID_ 参数指向转换为文本的复合条目标识符。</span><span class="sxs-lookup"><span data-stu-id="7a03d-126">If the  _cbStoreRecordKey_ parameter is greater than zero, the  _pszMsgID_ parameter points to a compound entry identifier converted to text.</span></span> <span data-ttu-id="7a03d-127">如果  _cbStoreRecordKey_ 为零，  _则 pszMsgID_ 指向转换为文本的非编译项标识符。</span><span class="sxs-lookup"><span data-stu-id="7a03d-127">If  _cbStoreRecordKey_ is zero,  _pszMsgID_ points to a noncompound entry identifier converted to text.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="7a03d-128">返回值</span><span class="sxs-lookup"><span data-stu-id="7a03d-128">Return value</span></span>

<span data-ttu-id="7a03d-129">无。</span><span class="sxs-lookup"><span data-stu-id="7a03d-129">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7a03d-130">说明</span><span class="sxs-lookup"><span data-stu-id="7a03d-130">Remarks</span></span>

<span data-ttu-id="7a03d-131">如果要创建复合条目标识符的邮件或其他对象驻留在邮件存储中，则从对象的条目标识符和存储的记录密钥创建标识符字符串。</span><span class="sxs-lookup"><span data-stu-id="7a03d-131">If the message or other object for which the compound entry identifier is being created resides in a message store, the identifier string is created from the object's entry identifier and the store's record key.</span></span> <span data-ttu-id="7a03d-132">如果对象不在存储区中，即，如果在  _cbStoreRecordKey_ 参数中传递的存储记录密钥的字节计数为零，则对象的条目标识符只是复制并转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="7a03d-132">If the object is not in a store, that is, if the byte count for the store record key passed in the  _cbStoreRecordKey_ parameter is zero, the object's entry identifier is simply copied and converted into a string.</span></span> 
  
<span data-ttu-id="7a03d-133">调用 **HrComposeMsgID** 函数等效于调用 [HrComposeEID](hrcomposeeid.md) 函数，然后调用 [HrSzFromEntryID](hrszfromentryid.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="7a03d-133">Calling the **HrComposeMsgID** function is equivalent to calling the [HrComposeEID](hrcomposeeid.md) function and then the [HrSzFromEntryID](hrszfromentryid.md) function.</span></span> 
  
 <span data-ttu-id="7a03d-134">**HrComposeMsgID** 允许客户端应用程序通过复合条目标识符处理多个存储中的对象。</span><span class="sxs-lookup"><span data-stu-id="7a03d-134">**HrComposeMsgID** enables client applications to work with objects in multiple stores through the use of compound entry identifiers.</span></span> <span data-ttu-id="7a03d-135">应用程序可以调用 [HrDecomposeMsgID](hrdecomposemsgid.md) 函数将复合条目标识符拆分为原始组成部分。</span><span class="sxs-lookup"><span data-stu-id="7a03d-135">An application can call the [HrDecomposeMsgID](hrdecomposemsgid.md) function to split the compound entry identifier into its original constituents.</span></span> 
  

