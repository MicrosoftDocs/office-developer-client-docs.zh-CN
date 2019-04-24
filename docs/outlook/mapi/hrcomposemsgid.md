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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348046"
---
# <a name="hrcomposemsgid"></a><span data-ttu-id="82780-103">HrComposeMsgID</span><span class="sxs-lookup"><span data-stu-id="82780-103">HrComposeMsgID</span></span>

  
  
<span data-ttu-id="82780-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82780-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82780-105">创建一个 ASCII 字符串, 该字符串表示对象的复合条目标识符, 通常是邮件存储区中的邮件。</span><span class="sxs-lookup"><span data-stu-id="82780-105">Creates an ASCII string representing a compound entry identifier for an object, usually a message in a message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="82780-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="82780-106">Header file:</span></span>  <br/> |<span data-ttu-id="82780-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="82780-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="82780-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="82780-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="82780-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="82780-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="82780-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="82780-110">Called by:</span></span>  <br/> |<span data-ttu-id="82780-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="82780-111">Client applications</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="82780-112">参数</span><span class="sxs-lookup"><span data-stu-id="82780-112">Parameters</span></span>

 <span data-ttu-id="82780-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="82780-113">_psession_</span></span>
  
> <span data-ttu-id="82780-114">实时指向客户端应用程序正在使用的会话的指针。</span><span class="sxs-lookup"><span data-stu-id="82780-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="82780-115">_cbStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="82780-115">_cbStoreRecordKey_</span></span>
  
> <span data-ttu-id="82780-116">实时包含邮件或其他对象的邮件存储区的记录键的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="82780-116">[in] Size, in bytes, of the record key of the message store that contains the message or other object.</span></span> <span data-ttu-id="82780-117">如果在_cbStoreRecordKey_参数中传递零, 则_pszMsgID_参数指向已转换为 text 的条目标识符的副本。</span><span class="sxs-lookup"><span data-stu-id="82780-117">If zero is passed in the  _cbStoreRecordKey_ parameter, the  _pszMsgID_ parameter points to a copy of the entry identifier converted to text.</span></span> 
    
 <span data-ttu-id="82780-118">_pStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="82780-118">_pStoreRecordKey_</span></span>
  
> <span data-ttu-id="82780-119">实时指向邮件存储区中包含邮件或其他对象的记录键的指针。</span><span class="sxs-lookup"><span data-stu-id="82780-119">[in] Pointer to the record key of the message store that contains the message or other object.</span></span> 
    
 <span data-ttu-id="82780-120">_cbMsgEID_</span><span class="sxs-lookup"><span data-stu-id="82780-120">_cbMsgEID_</span></span>
  
> <span data-ttu-id="82780-121">实时邮件或其他对象的条目标识符的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="82780-121">[in] Size, in bytes, of the entry identifier of the message or other object.</span></span> 
    
 <span data-ttu-id="82780-122">_pMsgEID_</span><span class="sxs-lookup"><span data-stu-id="82780-122">_pMsgEID_</span></span>
  
> <span data-ttu-id="82780-123">实时指向对象的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="82780-123">[in] Pointer to the entry identifier of the object.</span></span> 
    
 <span data-ttu-id="82780-124">_pszMsgID_</span><span class="sxs-lookup"><span data-stu-id="82780-124">_pszMsgID_</span></span>
  
> <span data-ttu-id="82780-125">排除指向返回的 ASCII 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="82780-125">[out] Pointer to the returned ASCII string.</span></span> <span data-ttu-id="82780-126">如果_cbStoreRecordKey_参数大于零, 则_pszMsgID_参数指向转换为 text 的复合条目标识符。</span><span class="sxs-lookup"><span data-stu-id="82780-126">If the  _cbStoreRecordKey_ parameter is greater than zero, the  _pszMsgID_ parameter points to a compound entry identifier converted to text.</span></span> <span data-ttu-id="82780-127">如果_cbStoreRecordKey_为零, 则_pszMsgID_指向已转换为 text 的 noncompound 条目标识符。</span><span class="sxs-lookup"><span data-stu-id="82780-127">If  _cbStoreRecordKey_ is zero,  _pszMsgID_ points to a noncompound entry identifier converted to text.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="82780-128">返回值</span><span class="sxs-lookup"><span data-stu-id="82780-128">Return value</span></span>

<span data-ttu-id="82780-129">无。</span><span class="sxs-lookup"><span data-stu-id="82780-129">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="82780-130">注解</span><span class="sxs-lookup"><span data-stu-id="82780-130">Remarks</span></span>

<span data-ttu-id="82780-131">如果要为其创建复合条目标识符的邮件或其他对象驻留在邮件存储区中, 则将从该对象的条目标识符和存储的记录密钥创建标识符字符串。</span><span class="sxs-lookup"><span data-stu-id="82780-131">If the message or other object for which the compound entry identifier is being created resides in a message store, the identifier string is created from the object's entry identifier and the store's record key.</span></span> <span data-ttu-id="82780-132">如果对象不在 store 中 (即, 如果在_cbStoreRecordKey_参数中传递的 store 记录关键字的字节数为零), 则只会复制对象的条目标识符, 并将其转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="82780-132">If the object is not in a store, that is, if the byte count for the store record key passed in the  _cbStoreRecordKey_ parameter is zero, the object's entry identifier is simply copied and converted into a string.</span></span> 
  
<span data-ttu-id="82780-133">调用**HrComposeMsgID**函数等效于调用[HrComposeEID](hrcomposeeid.md)函数, 然后调用[HrSzFromEntryID](hrszfromentryid.md)函数。</span><span class="sxs-lookup"><span data-stu-id="82780-133">Calling the **HrComposeMsgID** function is equivalent to calling the [HrComposeEID](hrcomposeeid.md) function and then the [HrSzFromEntryID](hrszfromentryid.md) function.</span></span> 
  
 <span data-ttu-id="82780-134">**HrComposeMsgID**使客户端应用程序能够通过使用复合条目标识符来处理多个存储中的对象。</span><span class="sxs-lookup"><span data-stu-id="82780-134">**HrComposeMsgID** enables client applications to work with objects in multiple stores through the use of compound entry identifiers.</span></span> <span data-ttu-id="82780-135">应用程序可以调用[HrDecomposeMsgID](hrdecomposemsgid.md)函数, 以将复合条目标识符拆分为其原始要素。</span><span class="sxs-lookup"><span data-stu-id="82780-135">An application can call the [HrDecomposeMsgID](hrdecomposemsgid.md) function to split the compound entry identifier into its original constituents.</span></span> 
  

