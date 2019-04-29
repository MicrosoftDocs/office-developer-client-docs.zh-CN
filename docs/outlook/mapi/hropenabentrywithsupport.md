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
ms.openlocfilehash: b8574264bdb470906cc097cec56b39a943937d11
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417642"
---
# <a name="hropenabentrywithsupport"></a><span data-ttu-id="89a5f-103">HrOpenABEntryWithSupport</span><span class="sxs-lookup"><span data-stu-id="89a5f-103">HrOpenABEntryWithSupport</span></span>

  
  
<span data-ttu-id="89a5f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="89a5f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="89a5f-105">请勿使用此函数。</span><span class="sxs-lookup"><span data-stu-id="89a5f-105">Do not use this function.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="89a5f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="89a5f-106">Header file:</span></span>  <br/> |<span data-ttu-id="89a5f-107">abhelp</span><span class="sxs-lookup"><span data-stu-id="89a5f-107">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="89a5f-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="89a5f-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="89a5f-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="89a5f-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="89a5f-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="89a5f-110">Called by:</span></span>  <br/> |<span data-ttu-id="89a5f-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="89a5f-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="89a5f-112">参数</span><span class="sxs-lookup"><span data-stu-id="89a5f-112">Parameters</span></span>

 <span data-ttu-id="89a5f-113">_lpSup_</span><span class="sxs-lookup"><span data-stu-id="89a5f-113">_lpSup_</span></span>
  
> 
    
 <span data-ttu-id="89a5f-114">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="89a5f-114">_cbEntryID_</span></span>
  
> <span data-ttu-id="89a5f-115">实时由_lpEntryID_参数指定的条目标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="89a5f-115">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="89a5f-116">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="89a5f-116">_lpEntryID_</span></span>
  
> <span data-ttu-id="89a5f-117">实时指向表示要打开的通讯簿条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="89a5f-117">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span>
    
 <span data-ttu-id="89a5f-118">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="89a5f-118">_lpInterface_</span></span>
  
>  <span data-ttu-id="89a5f-119">实时指向接口标识符 (IID) 的指针, 该接口用于访问打开的条目。</span><span class="sxs-lookup"><span data-stu-id="89a5f-119">[in] A pointer to the interface identifier (IID) of the interface to be used to access the open entry.</span></span> <span data-ttu-id="89a5f-120">传递 NULL 将返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="89a5f-120">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="89a5f-121">对于邮件用户, 标准接口为[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="89a5f-121">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="89a5f-122">对于通讯组列表, 它是[IDistList: IMAPIContainer](idistlistimapicontainer.md), 而对于容器, 它是[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="89a5f-122">For distribution lists, it is [IDistList : IMAPIContainer](idistlistimapicontainer.md), and for containers, it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="89a5f-123">呼叫者可将_lpInterface_设置为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="89a5f-123">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="89a5f-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="89a5f-124">_ulFlags_</span></span>
  
> <span data-ttu-id="89a5f-125">实时用于控制_lpszButtonText_参数文本类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="89a5f-125">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="89a5f-126">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="89a5f-126">The following flags can be set:</span></span> 
    
<span data-ttu-id="89a5f-127">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="89a5f-127">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="89a5f-128">指示如果实际对地址进行了更改, 则详细信息返回 TRUE; 否则返回 false。否则, 详细信息将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="89a5f-128">Indicates that Details returns TRUE if changes are actually made to the address; otherwise, Details returns FALSE.</span></span>
    
<span data-ttu-id="89a5f-129">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="89a5f-129">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="89a5f-130">显示 "常用地址" 对话框的模式版本。</span><span class="sxs-lookup"><span data-stu-id="89a5f-130">Displays the modal version of the common address dialog box.</span></span> <span data-ttu-id="89a5f-131">此标志与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="89a5f-131">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="89a5f-132">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="89a5f-132">DIALOG_SDI</span></span>
  
> <span data-ttu-id="89a5f-133">显示 "常用地址" 对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="89a5f-133">Displays the modeless version of the common address dialog box.</span></span> <span data-ttu-id="89a5f-134">此标志与 DIALOG_MODAL 互斥。</span><span class="sxs-lookup"><span data-stu-id="89a5f-134">This flag is mutually exclusive with DIALOG_MODAL.</span></span>
    
<span data-ttu-id="89a5f-135">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="89a5f-135">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="89a5f-136">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="89a5f-136">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="89a5f-137">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="89a5f-137">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="89a5f-138">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="89a5f-138">_lpulObjType_</span></span>
  
> <span data-ttu-id="89a5f-139">排除指向已打开条目的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="89a5f-139">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="89a5f-140">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="89a5f-140">_lppUnk_</span></span>
  
> <span data-ttu-id="89a5f-141">排除指向已打开条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="89a5f-141">[out] A pointer to a pointer of the opened entry.</span></span>
    

