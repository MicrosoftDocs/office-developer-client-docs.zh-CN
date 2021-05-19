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
# <a name="hropenabentrywithprovideruidsupport"></a><span data-ttu-id="3c067-103">HrOpenABEntryWithProviderUIDSupport</span><span class="sxs-lookup"><span data-stu-id="3c067-103">HrOpenABEntryWithProviderUIDSupport</span></span>

  
  
<span data-ttu-id="3c067-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3c067-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3c067-105">执行与 [HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md) 函数相同的函数，只不过 **HrOpenABEntryWithProviderUIDSupport** 函数使用给定的支持对象（而不是使用会话和通讯簿）打开条目。</span><span class="sxs-lookup"><span data-stu-id="3c067-105">Performs the same function as the [HrOpenABEntryWithProviderUID](hropenabentrywithprovideruid.md) function except that the **HrOpenABEntryWithProviderUIDSupport** function opens the entry using the given support object instead of using the session and the address book.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3c067-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3c067-106">Header file:</span></span>  <br/> |<span data-ttu-id="3c067-107">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="3c067-107">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="3c067-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="3c067-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="3c067-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="3c067-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="3c067-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="3c067-110">Called by:</span></span>  <br/> |<span data-ttu-id="3c067-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="3c067-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="3c067-112">参数</span><span class="sxs-lookup"><span data-stu-id="3c067-112">Parameters</span></span>

 <span data-ttu-id="3c067-113">_pEmsabpUID_</span><span class="sxs-lookup"><span data-stu-id="3c067-113">_pEmsabpUID_</span></span>
  
> <span data-ttu-id="3c067-114">[in]指向 _emsabpUID_ 参数的指针，该参数标识Exchange用于显示条目标识符详细信息的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="3c067-114">[in] A pointer to an  _emsabpUID_ parameter that identifies the Exchange address book provider that this function should use to display details on the entry identifier.</span></span> <span data-ttu-id="3c067-115">如果传入条目标识符不是通讯簿Exchange标识符，则忽略此参数，并且函数调用的作用与[IAddrBook：:D etails 完全相同](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="3c067-115">If the incoming entry identifier is not an Exchange address book provider entry identifier, this parameter is ignored and the function call acts exactly like [IAddrBook::Details](iaddrbook-details.md).</span></span> <span data-ttu-id="3c067-116">如果此参数为 NULL 或零 MAPIUID，则此函数也与 [IAddrBook：:D etails 完全相同](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="3c067-116">If this parameter is NULL or a zero MAPIUID, this function also acts exactly like [IAddrBook::Details](iaddrbook-details.md).</span></span>
    
 <span data-ttu-id="3c067-117">_lpSup_</span><span class="sxs-lookup"><span data-stu-id="3c067-117">_lpSup_</span></span>
  
> 
    
 <span data-ttu-id="3c067-118">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="3c067-118">_cbEntryID_</span></span>
  
> <span data-ttu-id="3c067-119">[in]  _lpEntryID_ 参数指定的条目标识符的字节计数。</span><span class="sxs-lookup"><span data-stu-id="3c067-119">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="3c067-120">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="3c067-120">_lpEntryID_</span></span>
  
> <span data-ttu-id="3c067-121">[in]指向表示要打开的通讯簿条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="3c067-121">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span>
    
 <span data-ttu-id="3c067-122">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="3c067-122">_lpInterface_</span></span>
  
> <span data-ttu-id="3c067-123">[in]指向接口标识符 (IID) 用于访问打开条目的接口的 IID 标识符。</span><span class="sxs-lookup"><span data-stu-id="3c067-123">[in] A pointer to the interface identifier (IID) of the interface to be used to access the open entry.</span></span> <span data-ttu-id="3c067-124">传递 NULL 将返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="3c067-124">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="3c067-125">对于邮件用户，标准接口是 [IMailUser ： IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="3c067-125">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="3c067-126">对于通讯组列表，它是 [IDistList ： IMAPIContainer](idistlistimapicontainer.md)，对于容器，它是 [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="3c067-126">For distribution lists it is [IDistList : IMAPIContainer](idistlistimapicontainer.md), and for containers it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="3c067-127">调用方可以将  _lpInterface_ 设置为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="3c067-127">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="3c067-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3c067-128">_ulFlags_</span></span>
  
> <span data-ttu-id="3c067-129">[in]控制  _lpszButtonText_ 参数的文本类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="3c067-129">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="3c067-130">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="3c067-130">The following flags can be set:</span></span> 
    
<span data-ttu-id="3c067-131">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="3c067-131">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="3c067-132">指示如果实际对地址进行了更改，Details 将返回 TRUE;否则，Details 将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="3c067-132">Indicates that Details returns TRUE if changes are actually made to the address; otherwise, Details returns FALSE.</span></span>
    
<span data-ttu-id="3c067-133">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="3c067-133">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="3c067-134">显示常用地址对话框的模式版本。</span><span class="sxs-lookup"><span data-stu-id="3c067-134">Displays the modal version of the common address dialog box.</span></span> <span data-ttu-id="3c067-135">此标志与 DIALOG_SDI。</span><span class="sxs-lookup"><span data-stu-id="3c067-135">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="3c067-136">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="3c067-136">DIALOG_SDI</span></span>
  
> <span data-ttu-id="3c067-137">显示公用地址对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="3c067-137">Displays the modeless version of the common address dialog box.</span></span> <span data-ttu-id="3c067-138">此标志与 DIALOG_MODAL。</span><span class="sxs-lookup"><span data-stu-id="3c067-138">This flag is mutually exclusive with DIALOG_MODAL.</span></span>
    
<span data-ttu-id="3c067-139">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3c067-139">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="3c067-140">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="3c067-140">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="3c067-141">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="3c067-141">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="3c067-142">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="3c067-142">_lpulObjType_</span></span>
  
> <span data-ttu-id="3c067-143">[out]指向打开的条目类型的指针。</span><span class="sxs-lookup"><span data-stu-id="3c067-143">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="3c067-144">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="3c067-144">_lppUnk_</span></span>
  
> <span data-ttu-id="3c067-145">[out]指向已打开条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3c067-145">[out] A pointer to a pointer of the opened entry.</span></span>
    

