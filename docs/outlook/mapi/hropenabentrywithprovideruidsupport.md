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
ms.openlocfilehash: bd42fcd34042c2f9579497f164c4a67f6ba97e35
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775207"
---
# <a name="hropenabentrywithprovideruidsupport"></a><span data-ttu-id="39fce-103">HrOpenABEntryWithProviderUIDSupport</span><span class="sxs-lookup"><span data-stu-id="39fce-103">HrOpenABEntryWithProviderUIDSupport</span></span>

  
  
<span data-ttu-id="39fce-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="39fce-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="39fce-105">在于**HrOpenABEntryWithProviderUIDSupport**函数打开而不使用会话和通讯簿使用给定的支持对象的条目，请执行[HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md)函数相同的功能。</span><span class="sxs-lookup"><span data-stu-id="39fce-105">Performs the same function as the [HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md) function except that the **HrOpenABEntryWithProviderUIDSupport** function opens the entry using the given support object instead of using the session and the address book.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="39fce-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="39fce-106">Header file:</span></span>  <br/> |<span data-ttu-id="39fce-107">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="39fce-107">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="39fce-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="39fce-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="39fce-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="39fce-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="39fce-110">调用：</span><span class="sxs-lookup"><span data-stu-id="39fce-110">Called by:</span></span>  <br/> |<span data-ttu-id="39fce-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="39fce-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="39fce-112">参数</span><span class="sxs-lookup"><span data-stu-id="39fce-112">Parameters</span></span>

 <span data-ttu-id="39fce-113">_pEmsabpUID_</span><span class="sxs-lookup"><span data-stu-id="39fce-113">_pEmsabpUID_</span></span>
  
> <span data-ttu-id="39fce-114">[in]标识此函数应使用要显示的项标识符的详细信息 Exchange 通讯簿提供程序_emsabpUID_参数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="39fce-114">[in] A pointer to an  _emsabpUID_ parameter that identifies the Exchange address book provider that this function should use to display details on the entry identifier.</span></span> <span data-ttu-id="39fce-115">如果传入的项标识符不是 Exchange 通讯簿提供程序条目标识符，则忽略此参数和函数调用并且与[IAddrBook::Details](iaddrbook-details.md)完全一样。</span><span class="sxs-lookup"><span data-stu-id="39fce-115">If the incoming entry identifier is not an Exchange address book provider entry identifier, this parameter is ignored and the function call acts exactly like [IAddrBook::Details](iaddrbook-details.md).</span></span> <span data-ttu-id="39fce-116">如果此参数为 NULL 或零 MAPIUID，此函数的还行为与[IAddrBook::Details](iaddrbook-details.md)完全相同。</span><span class="sxs-lookup"><span data-stu-id="39fce-116">If this parameter is NULL or a zero MAPIUID, this function also acts exactly like [IAddrBook::Details](iaddrbook-details.md).</span></span>
    
 <span data-ttu-id="39fce-117">_lpSup_</span><span class="sxs-lookup"><span data-stu-id="39fce-117">_lpSup_</span></span>
  
> 
    
 <span data-ttu-id="39fce-118">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="39fce-118">_cbEntryID_</span></span>
  
> <span data-ttu-id="39fce-119">[in]_LpEntryID_参数指定的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="39fce-119">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="39fce-120">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="39fce-120">_lpEntryID_</span></span>
  
> <span data-ttu-id="39fce-121">[in]一个指向代表打开的通讯簿条目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="39fce-121">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span>
    
 <span data-ttu-id="39fce-122">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="39fce-122">_lpInterface_</span></span>
  
> <span data-ttu-id="39fce-123">[in]指向要用于访问打开条目的接口的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="39fce-123">[in] A pointer to the interface identifier (IID) of the interface to be used to access the open entry.</span></span> <span data-ttu-id="39fce-124">传递 NULL 将返回标准接口的对象。</span><span class="sxs-lookup"><span data-stu-id="39fce-124">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="39fce-125">对于邮件用户，标准接口是[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="39fce-125">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="39fce-126">对于通讯组列表它是[IDistList: IMAPIContainer](idistlistimapicontainer.md)，以及是的容器[IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="39fce-126">For distribution lists it is [IDistList : IMAPIContainer](idistlistimapicontainer.md), and for containers it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="39fce-127">呼叫者可以设置_lpInterface_为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="39fce-127">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="39fce-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="39fce-128">_ulFlags_</span></span>
  
> <span data-ttu-id="39fce-129">[in]位掩码的标志的控制_lpszButtonText_参数的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="39fce-129">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="39fce-130">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="39fce-130">The following flags can be set:</span></span> 
    
<span data-ttu-id="39fce-131">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="39fce-131">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="39fce-132">指示详细信息返回 TRUE 是否进行了更改实际的地址;否则，详细信息将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="39fce-132">Indicates that Details returns TRUE if changes are actually made to the address; otherwise, Details returns FALSE.</span></span>
    
<span data-ttu-id="39fce-133">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="39fce-133">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="39fce-134">显示模式版本的通用的地址对话框。</span><span class="sxs-lookup"><span data-stu-id="39fce-134">Displays the modal version of the common address dialog box.</span></span> <span data-ttu-id="39fce-135">此标志是与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="39fce-135">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="39fce-136">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="39fce-136">DIALOG_SDI</span></span>
  
> <span data-ttu-id="39fce-137">显示通用的地址对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="39fce-137">Displays the modeless version of the common address dialog box.</span></span> <span data-ttu-id="39fce-138">此标志是与 DIALOG_MODAL 互斥。</span><span class="sxs-lookup"><span data-stu-id="39fce-138">This flag is mutually exclusive with DIALOG_MODAL.</span></span>
    
<span data-ttu-id="39fce-139">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="39fce-139">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="39fce-140">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="39fce-140">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="39fce-141">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="39fce-141">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="39fce-142">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="39fce-142">_lpulObjType_</span></span>
  
> <span data-ttu-id="39fce-143">[输出]一个指向打开条目的类型。</span><span class="sxs-lookup"><span data-stu-id="39fce-143">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="39fce-144">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="39fce-144">_lppUnk_</span></span>
  
> <span data-ttu-id="39fce-145">[输出]指向打开的条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="39fce-145">[out] A pointer to a pointer of the opened entry.</span></span>
    

