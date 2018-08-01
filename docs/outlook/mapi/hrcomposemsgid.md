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
ms.openlocfilehash: 418ffdd19412dcf948d36a5e7df33f7978d0df3c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775145"
---
# <a name="hrcomposemsgid"></a><span data-ttu-id="deb95-103">HrComposeMsgID</span><span class="sxs-lookup"><span data-stu-id="deb95-103">HrComposeMsgID</span></span>

  
  
<span data-ttu-id="deb95-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="deb95-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="deb95-105">创建表示一个对象，通常一条消息的消息存储的复合条目标识符 ASCII 字符串。</span><span class="sxs-lookup"><span data-stu-id="deb95-105">Creates an ASCII string representing a compound entry identifier for an object, usually a message in a message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="deb95-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="deb95-106">Header file:</span></span>  <br/> |<span data-ttu-id="deb95-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="deb95-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="deb95-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="deb95-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="deb95-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="deb95-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="deb95-110">调用：</span><span class="sxs-lookup"><span data-stu-id="deb95-110">Called by:</span></span>  <br/> |<span data-ttu-id="deb95-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="deb95-111">Client applications</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="deb95-112">参数</span><span class="sxs-lookup"><span data-stu-id="deb95-112">Parameters</span></span>

 <span data-ttu-id="deb95-113">_psession_</span><span class="sxs-lookup"><span data-stu-id="deb95-113">_psession_</span></span>
  
> <span data-ttu-id="deb95-114">[in]加入会话，使用客户端应用程序的指针。</span><span class="sxs-lookup"><span data-stu-id="deb95-114">[in] Pointer to the session in use by the client application.</span></span> 
    
 <span data-ttu-id="deb95-115">_cbStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="deb95-115">_cbStoreRecordKey_</span></span>
  
> <span data-ttu-id="deb95-116">[in]大小 （以字节为单位，消息存储库包含邮件或其他对象的记录项）。</span><span class="sxs-lookup"><span data-stu-id="deb95-116">[in] Size, in bytes, of the record key of the message store that contains the message or other object.</span></span> <span data-ttu-id="deb95-117">如果_cbStoreRecordKey_参数中传递零，则该_pszMsgID_参数指向副本的项标识符的转换为文本。</span><span class="sxs-lookup"><span data-stu-id="deb95-117">If zero is passed in the  _cbStoreRecordKey_ parameter, the  _pszMsgID_ parameter points to a copy of the entry identifier converted to text.</span></span> 
    
 <span data-ttu-id="deb95-118">_pStoreRecordKey_</span><span class="sxs-lookup"><span data-stu-id="deb95-118">_pStoreRecordKey_</span></span>
  
> <span data-ttu-id="deb95-119">[in]向记录项的消息存储库包含邮件或其他对象的指针。</span><span class="sxs-lookup"><span data-stu-id="deb95-119">[in] Pointer to the record key of the message store that contains the message or other object.</span></span> 
    
 <span data-ttu-id="deb95-120">_cbMsgEID_</span><span class="sxs-lookup"><span data-stu-id="deb95-120">_cbMsgEID_</span></span>
  
> <span data-ttu-id="deb95-121">[in]大小，以字节为单位的项标识符的邮件或其他对象。</span><span class="sxs-lookup"><span data-stu-id="deb95-121">[in] Size, in bytes, of the entry identifier of the message or other object.</span></span> 
    
 <span data-ttu-id="deb95-122">_pMsgEID_</span><span class="sxs-lookup"><span data-stu-id="deb95-122">_pMsgEID_</span></span>
  
> <span data-ttu-id="deb95-123">[in]指向对象的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="deb95-123">[in] Pointer to the entry identifier of the object.</span></span> 
    
 <span data-ttu-id="deb95-124">_pszMsgID_</span><span class="sxs-lookup"><span data-stu-id="deb95-124">_pszMsgID_</span></span>
  
> <span data-ttu-id="deb95-125">[输出]指向返回 ASCII 字符串。</span><span class="sxs-lookup"><span data-stu-id="deb95-125">[out] Pointer to the returned ASCII string.</span></span> <span data-ttu-id="deb95-126">如果_cbStoreRecordKey_参数大于零，为复合项标识符的_pszMsgID_参数点转换为文本。</span><span class="sxs-lookup"><span data-stu-id="deb95-126">If the  _cbStoreRecordKey_ parameter is greater than zero, the  _pszMsgID_ parameter points to a compound entry identifier converted to text.</span></span> <span data-ttu-id="deb95-127">如果_cbStoreRecordKey_为零，为非复合条目标识符_pszMsgID_磅转换为文本。</span><span class="sxs-lookup"><span data-stu-id="deb95-127">If  _cbStoreRecordKey_ is zero,  _pszMsgID_ points to a noncompound entry identifier converted to text.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="deb95-128">返回值</span><span class="sxs-lookup"><span data-stu-id="deb95-128">Return value</span></span>

<span data-ttu-id="deb95-129">无。</span><span class="sxs-lookup"><span data-stu-id="deb95-129">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="deb95-130">说明</span><span class="sxs-lookup"><span data-stu-id="deb95-130">Remarks</span></span>

<span data-ttu-id="deb95-131">如果邮件或其他对象为其创建的复合条目标识符位于的消息存储，标识符字符串创建从对象的项标识符的存储记录的键。</span><span class="sxs-lookup"><span data-stu-id="deb95-131">If the message or other object for which the compound entry identifier is being created resides in a message store, the identifier string is created from the object's entry identifier and the store's record key.</span></span> <span data-ttu-id="deb95-132">如果对象不是存储区中，即，如果_cbStoreRecordKey_参数中传递的存储记录密钥的字节数为零，对象的项标识符只需复制并转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="deb95-132">If the object is not in a store, that is, if the byte count for the store record key passed in the  _cbStoreRecordKey_ parameter is zero, the object's entry identifier is simply copied and converted into a string.</span></span> 
  
<span data-ttu-id="deb95-133">调用**HrComposeMsgID**函数等效于调用[HrComposeEID](hrcomposeeid.md)函数，然后选择[HrSzFromEntryID](hrszfromentryid.md)函数。</span><span class="sxs-lookup"><span data-stu-id="deb95-133">Calling the **HrComposeMsgID** function is equivalent to calling the [HrComposeEID](hrcomposeeid.md) function and then the [HrSzFromEntryID](hrszfromentryid.md) function.</span></span> 
  
 <span data-ttu-id="deb95-134">**HrComposeMsgID**使客户端应用程序以使用复合条目标识符使用的多个存储区中的对象。</span><span class="sxs-lookup"><span data-stu-id="deb95-134">**HrComposeMsgID** enables client applications to work with objects in multiple stores through the use of compound entry identifiers.</span></span> <span data-ttu-id="deb95-135">应用程序可以调用[HrDecomposeMsgID](hrdecomposemsgid.md)函数拆分到其原始构成的复合条目标识符。</span><span class="sxs-lookup"><span data-stu-id="deb95-135">An application can call the [HrDecomposeMsgID](hrdecomposemsgid.md) function to split the compound entry identifier into its original constituents.</span></span> 
  

