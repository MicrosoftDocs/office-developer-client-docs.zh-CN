---
title: HrOpenABEntryWithSupport
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: eaa988ea-aee1-4066-8c78-2b6c28def5e0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 58a6249295810e32c0a0f845e4830b8f393885ba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579380"
---
# <a name="hropenabentrywithsupport"></a><span data-ttu-id="cc8f8-103">HrOpenABEntryWithSupport</span><span class="sxs-lookup"><span data-stu-id="cc8f8-103">HrOpenABEntryWithSupport</span></span>

  
  
<span data-ttu-id="cc8f8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc8f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc8f8-105">不要使用此函数。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-105">Do not use this function.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cc8f8-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="cc8f8-106">Header file:</span></span>  <br/> |<span data-ttu-id="cc8f8-107">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="cc8f8-107">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="cc8f8-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="cc8f8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="cc8f8-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="cc8f8-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="cc8f8-110">调用：</span><span class="sxs-lookup"><span data-stu-id="cc8f8-110">Called by:</span></span>  <br/> |<span data-ttu-id="cc8f8-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="cc8f8-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithSupport(
  LPMAPISUP lpSup,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID  lpInterface,
  ULONG  ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="cc8f8-112">参数</span><span class="sxs-lookup"><span data-stu-id="cc8f8-112">Parameters</span></span>

 <span data-ttu-id="cc8f8-113">_lpSup_</span><span class="sxs-lookup"><span data-stu-id="cc8f8-113">_lpSup_</span></span>
  
> 
    
 <span data-ttu-id="cc8f8-114">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="cc8f8-114">_cbEntryID_</span></span>
  
> <span data-ttu-id="cc8f8-115">[in]_LpEntryID_参数指定的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-115">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="cc8f8-116">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="cc8f8-116">_lpEntryID_</span></span>
  
> <span data-ttu-id="cc8f8-117">[in]一个指向代表打开的通讯簿条目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-117">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span>
    
 <span data-ttu-id="cc8f8-118">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="cc8f8-118">_lpInterface_</span></span>
  
>  <span data-ttu-id="cc8f8-119">[in]指向要用于访问打开条目的接口的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-119">[in] A pointer to the interface identifier (IID) of the interface to be used to access the open entry.</span></span> <span data-ttu-id="cc8f8-120">传递 NULL 将返回标准接口的对象。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-120">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="cc8f8-121">对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-121">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="cc8f8-122">对于通讯组列表，它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)，而容器，则为： [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-122">For distribution lists, it is [IDistList : IMAPIContainer](idistlistimapicontainer.md), and for containers, it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="cc8f8-123">呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-123">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="cc8f8-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cc8f8-124">_ulFlags_</span></span>
  
> <span data-ttu-id="cc8f8-125">[in]位掩码的标志的控制_lpszButtonText_参数的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-125">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="cc8f8-126">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="cc8f8-126">The following flags can be set:</span></span> 
    
<span data-ttu-id="cc8f8-127">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="cc8f8-127">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="cc8f8-128">指示详细信息返回 TRUE 是否进行了更改实际的地址;否则，详细信息将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-128">Indicates that Details returns TRUE if changes are actually made to the address; otherwise, Details returns FALSE.</span></span>
    
<span data-ttu-id="cc8f8-129">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="cc8f8-129">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="cc8f8-130">显示模式版本的通用的地址对话框。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-130">Displays the modal version of the common address dialog box.</span></span> <span data-ttu-id="cc8f8-131">此标志是与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-131">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="cc8f8-132">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="cc8f8-132">DIALOG_SDI</span></span>
  
> <span data-ttu-id="cc8f8-133">显示通用的地址对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-133">Displays the modeless version of the common address dialog box.</span></span> <span data-ttu-id="cc8f8-134">此标志是与 DIALOG_MODAL 互斥。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-134">This flag is mutually exclusive with DIALOG_MODAL.</span></span>
    
<span data-ttu-id="cc8f8-135">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cc8f8-135">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="cc8f8-136">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-136">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="cc8f8-137">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-137">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="cc8f8-138">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="cc8f8-138">_lpulObjType_</span></span>
  
> <span data-ttu-id="cc8f8-139">[输出]一个指向打开条目的类型。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-139">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="cc8f8-140">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="cc8f8-140">_lppUnk_</span></span>
  
> <span data-ttu-id="cc8f8-141">[输出]指向打开的条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="cc8f8-141">[out] A pointer to a pointer of the opened entry.</span></span>
    

