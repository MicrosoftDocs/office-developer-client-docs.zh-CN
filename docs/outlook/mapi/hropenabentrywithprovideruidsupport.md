---
title: HrOpenABEntryWithProviderUIDSupport
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1fafc810-7cf3-4c8c-bf21-055ae34da690
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da40e240b60fa42c48185600b74c6162a966e6f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409543"
---
# <a name="hropenabentrywithprovideruidsupport"></a><span data-ttu-id="19ba4-103">HrOpenABEntryWithProviderUIDSupport</span><span class="sxs-lookup"><span data-stu-id="19ba4-103">HrOpenABEntryWithProviderUIDSupport</span></span>

  
  
<span data-ttu-id="19ba4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="19ba4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="19ba4-105">除了**HrOpenABEntryWithProviderUIDSupport**函数使用给定的支持对象 (而不是使用会话和通讯簿) 打开条目之外, 还执行与[HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md)函数相同的函数。</span><span class="sxs-lookup"><span data-stu-id="19ba4-105">Performs the same function as the [HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md) function except that the **HrOpenABEntryWithProviderUIDSupport** function opens the entry using the given support object instead of using the session and the address book.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="19ba4-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="19ba4-106">Header file:</span></span>  <br/> |<span data-ttu-id="19ba4-107">abhelp</span><span class="sxs-lookup"><span data-stu-id="19ba4-107">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="19ba4-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="19ba4-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="19ba4-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="19ba4-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="19ba4-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="19ba4-110">Called by:</span></span>  <br/> |<span data-ttu-id="19ba4-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="19ba4-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithProviderUIDSupport(
  const MAPIUID *pEmsabpUID,
  LPMAPISUP lpSup,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="19ba4-112">参数</span><span class="sxs-lookup"><span data-stu-id="19ba4-112">Parameters</span></span>

 <span data-ttu-id="19ba4-113">_pEmsabpUID_</span><span class="sxs-lookup"><span data-stu-id="19ba4-113">_pEmsabpUID_</span></span>
  
> <span data-ttu-id="19ba4-114">实时一个指向_emsabpUID_参数的指针, 该参数标识此函数应使用的 Exchange 通讯簿提供程序, 以显示有关条目标识符的详细信息。</span><span class="sxs-lookup"><span data-stu-id="19ba4-114">[in] A pointer to an  _emsabpUID_ parameter that identifies the Exchange address book provider that this function should use to display details on the entry identifier.</span></span> <span data-ttu-id="19ba4-115">如果传入条目标识符不是 Exchange 通讯簿提供程序条目标识符, 则此参数将被忽略, 并且函数调用的行为完全像[IAddrBook::D etails](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="19ba4-115">If the incoming entry identifier is not an Exchange address book provider entry identifier, this parameter is ignored and the function call acts exactly like [IAddrBook::Details](iaddrbook-details.md).</span></span> <span data-ttu-id="19ba4-116">如果此参数为 NULL 或零 MAPIUID, 则此函数也相当于[IAddrBook::D etails](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="19ba4-116">If this parameter is NULL or a zero MAPIUID, this function also acts exactly like [IAddrBook::Details](iaddrbook-details.md).</span></span>
    
 <span data-ttu-id="19ba4-117">_lpSup_</span><span class="sxs-lookup"><span data-stu-id="19ba4-117">_lpSup_</span></span>
  
> 
    
 <span data-ttu-id="19ba4-118">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="19ba4-118">_cbEntryID_</span></span>
  
> <span data-ttu-id="19ba4-119">实时由_lpEntryID_参数指定的条目标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="19ba4-119">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="19ba4-120">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="19ba4-120">_lpEntryID_</span></span>
  
> <span data-ttu-id="19ba4-121">实时指向表示要打开的通讯簿条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="19ba4-121">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span>
    
 <span data-ttu-id="19ba4-122">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="19ba4-122">_lpInterface_</span></span>
  
> <span data-ttu-id="19ba4-123">实时指向接口标识符 (IID) 的指针, 该接口用于访问打开的条目。</span><span class="sxs-lookup"><span data-stu-id="19ba4-123">[in] A pointer to the interface identifier (IID) of the interface to be used to access the open entry.</span></span> <span data-ttu-id="19ba4-124">传递 NULL 将返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="19ba4-124">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="19ba4-125">对于邮件用户, 标准接口为[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="19ba4-125">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="19ba4-126">对于通讯组列表, 它是[IDistList: IMAPIContainer](idistlistimapicontainer.md), 而对于容器, 它是[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="19ba4-126">For distribution lists it is [IDistList : IMAPIContainer](idistlistimapicontainer.md), and for containers it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="19ba4-127">呼叫者可将_lpInterface_设置为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="19ba4-127">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="19ba4-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="19ba4-128">_ulFlags_</span></span>
  
> <span data-ttu-id="19ba4-129">实时用于控制_lpszButtonText_参数文本类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="19ba4-129">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="19ba4-130">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="19ba4-130">The following flags can be set:</span></span> 
    
<span data-ttu-id="19ba4-131">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="19ba4-131">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="19ba4-132">指示如果实际对地址进行了更改, 则详细信息返回 TRUE; 否则返回 false。否则, 详细信息将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="19ba4-132">Indicates that Details returns TRUE if changes are actually made to the address; otherwise, Details returns FALSE.</span></span>
    
<span data-ttu-id="19ba4-133">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="19ba4-133">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="19ba4-134">显示 "常用地址" 对话框的模式版本。</span><span class="sxs-lookup"><span data-stu-id="19ba4-134">Displays the modal version of the common address dialog box.</span></span> <span data-ttu-id="19ba4-135">此标志与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="19ba4-135">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="19ba4-136">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="19ba4-136">DIALOG_SDI</span></span>
  
> <span data-ttu-id="19ba4-137">显示 "常用地址" 对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="19ba4-137">Displays the modeless version of the common address dialog box.</span></span> <span data-ttu-id="19ba4-138">此标志与 DIALOG_MODAL 互斥。</span><span class="sxs-lookup"><span data-stu-id="19ba4-138">This flag is mutually exclusive with DIALOG_MODAL.</span></span>
    
<span data-ttu-id="19ba4-139">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="19ba4-139">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="19ba4-140">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="19ba4-140">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="19ba4-141">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="19ba4-141">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="19ba4-142">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="19ba4-142">_lpulObjType_</span></span>
  
> <span data-ttu-id="19ba4-143">排除指向已打开条目的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="19ba4-143">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="19ba4-144">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="19ba4-144">_lppUnk_</span></span>
  
> <span data-ttu-id="19ba4-145">排除指向已打开条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="19ba4-145">[out] A pointer to a pointer of the opened entry.</span></span>
    

