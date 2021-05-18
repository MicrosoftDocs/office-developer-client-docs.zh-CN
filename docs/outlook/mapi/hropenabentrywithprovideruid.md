---
title: HrOpenABEntryWithProviderUID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 83821a86-abff-460c-bb8e-9fd9d232dc6b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 20344185ffcbd90017fa3c3493218bd9b3ddfd74
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408892"
---
# <a name="hropenabentrywithprovideruid"></a><span data-ttu-id="2c65f-103">HrOpenABEntryWithProviderUID</span><span class="sxs-lookup"><span data-stu-id="2c65f-103">HrOpenABEntryWithProviderUID</span></span>

  
  
<span data-ttu-id="2c65f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2c65f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2c65f-105">使用 _pEmsabpUID_ 标识Exchange通讯簿打开 entryID。</span><span class="sxs-lookup"><span data-stu-id="2c65f-105">Opens the **entryID** using the Exchange Address Book identified by  _pEmsabpUID_.</span></span> <span data-ttu-id="2c65f-106">此函数的工作方式与[IAddrBook：：OpenEntry](iaddrbook-openentry.md)类似，只是使用此函数可确保使用预期的通讯簿提供程序打开[IAddrBook：：OpenEntry](iaddrbook-openentry.md) Exchange打开。</span><span class="sxs-lookup"><span data-stu-id="2c65f-106">This function works similarly to [IAddrBook::OpenEntry](iaddrbook-openentry.md) except that using this function ensures that [IAddrBook::OpenEntry](iaddrbook-openentry.md) is opened by using the expected Exchange Address Book provider.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2c65f-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2c65f-107">Header file:</span></span>  <br/> |<span data-ttu-id="2c65f-108">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="2c65f-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="2c65f-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="2c65f-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="2c65f-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="2c65f-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="2c65f-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="2c65f-111">Called by:</span></span>  <br/> |<span data-ttu-id="2c65f-112">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="2c65f-112">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithProviderUID(
  const MAPIUID *pEmsabpUID,
  LPADRBOOK pAddrBook,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="2c65f-113">参数</span><span class="sxs-lookup"><span data-stu-id="2c65f-113">Parameters</span></span>

 <span data-ttu-id="2c65f-114">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="2c65f-114">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="2c65f-115">[in]指向 **emsmdbUID** 的指针，标识包含 Exchange 通讯簿提供程序的 Exchange Service，此函数应该使用该提供程序在条目标识符上显示详细信息。</span><span class="sxs-lookup"><span data-stu-id="2c65f-115">[in] A pointer to an **emsmdbUID** that identifies the Exchange Service that contains the Exchange Address Book Provider that this function should use to display details on the entry identifier.</span></span> <span data-ttu-id="2c65f-116">如果传入条目标识符不是通讯簿Exchange标识符，则忽略此参数，并且函数调用的行为类似于[IAddrBook：:D etails](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="2c65f-116">If the incoming entry identifier is not an Exchange Address Book Provider entry identifier, this parameter is ignored and the function call behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span> <span data-ttu-id="2c65f-117">如果此参数为 NULL 或零 MAPIUID，则此函数的行为类似于 [IAddrBook：:D etails](iaddrbook-details.md)。</span><span class="sxs-lookup"><span data-stu-id="2c65f-117">If this parameter is NULL or a zero MAPIUID, this function behaves like [IAddrBook::Details](iaddrbook-details.md).</span></span>
    
 <span data-ttu-id="2c65f-118">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="2c65f-118">_pAddrBook_</span></span>
  
> <span data-ttu-id="2c65f-119">[in]用于打开条目标识符的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="2c65f-119">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="2c65f-120">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2c65f-120">It cannot be NULL.</span></span>
    
 <span data-ttu-id="2c65f-121">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="2c65f-121">_cbEntryID_</span></span>
  
> <span data-ttu-id="2c65f-122">[in]  _lpEntryID_ 参数指定的条目标识符的字节计数。</span><span class="sxs-lookup"><span data-stu-id="2c65f-122">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="2c65f-123">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="2c65f-123">_lpEntryID_</span></span>
  
>  <span data-ttu-id="2c65f-124">[in]指向表示要打开的通讯簿条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="2c65f-124">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span> 
    
 <span data-ttu-id="2c65f-125">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="2c65f-125">_lpInterface_</span></span>
  
> <span data-ttu-id="2c65f-126">[in]指向用于访问打开 (的) 接口的 IID 标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="2c65f-126">[in] A pointer to the interface identifier (IID) of the interface that is used to access the open entry.</span></span> <span data-ttu-id="2c65f-127">传递 NULL 将返回对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="2c65f-127">Passing NULL returns the standard interface of the object.</span></span> <span data-ttu-id="2c65f-128">对于邮件用户，标准接口是 [IMailUser ： IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="2c65f-128">For messaging users, the standard interface is [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span> <span data-ttu-id="2c65f-129">对于通讯组列表，它是 [IDistList ： IMAPIContainer，](idistlistimapicontainer.md)对于容器，它是 [IABContainer ： IMAPIContainer](iabcontainerimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="2c65f-129">For distribution lists, it is [IDistList : IMAPIContainer](idistlistimapicontainer.md)and for containers, it is [IABContainer : IMAPIContainer](iabcontainerimapicontainer.md).</span></span> <span data-ttu-id="2c65f-130">调用方可以将  _lpInterface_ 设置为相应的标准接口或继承层次结构中的接口。</span><span class="sxs-lookup"><span data-stu-id="2c65f-130">Callers can set  _lpInterface_ to the appropriate standard interface or an interface in the inheritance hierarchy.</span></span> 
    
 <span data-ttu-id="2c65f-131">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2c65f-131">_ulFlags_</span></span>
  
> <span data-ttu-id="2c65f-132">[in]控制条目打开方式的标志的位掩码，可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="2c65f-132">[in] A bitmask of flags that controls the how the entry is opened, The following flags can be set:</span></span>
    
<span data-ttu-id="2c65f-133">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="2c65f-133">MAPI_BEST_ACCESS</span></span>
  
> <span data-ttu-id="2c65f-134">请求以允许的最大网络和客户端权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="2c65f-134">Requests that the entry be opened with the maximum allowed network and client permissions.</span></span> <span data-ttu-id="2c65f-135">例如，如果客户端具有读取和写入权限，通讯簿提供程序将尝试打开具有读取和写入权限的条目。</span><span class="sxs-lookup"><span data-stu-id="2c65f-135">For example, if the client has read and write permission, the address book provider attempts to open the entry with read and write permission.</span></span> <span data-ttu-id="2c65f-136">客户端可以检索通过调用打开条目的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法并检索 PR_ACCESS_LEVEL (PidTagAccessLevel) 属性授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="2c65f-136">The client can retrieve the access level that was granted by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method of the open entry and retrieving the PR_ACCESS_LEVEL (PidTagAccessLevel) property.</span></span> 
    
<span data-ttu-id="2c65f-137">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="2c65f-137">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="2c65f-138">仅使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="2c65f-138">Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="2c65f-139">例如，您可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL) ，并访问缓存中的该通讯簿中的条目，而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="2c65f-139">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="2c65f-140">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="2c65f-140">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="2c65f-141">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="2c65f-141">MAPI_DEFERRED_ERRORS</span></span>
  
> <span data-ttu-id="2c65f-142">允许在条目完全打开且可用之前成功调用，这意味着对条目的后续调用可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="2c65f-142">Allows the call to succeed, potentially before the entry is fully open and available, implying that subsequent calls to the entry might return an error.</span></span>
    
<span data-ttu-id="2c65f-143">MAPI_GAL_ONLY</span><span class="sxs-lookup"><span data-stu-id="2c65f-143">MAPI_GAL_ONLY</span></span>
  
> <span data-ttu-id="2c65f-144">仅使用 GAL 执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="2c65f-144">Use only the GAL to perform name resolution.</span></span> <span data-ttu-id="2c65f-145">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="2c65f-145">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
<span data-ttu-id="2c65f-146">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="2c65f-146">MAPI_MODIFY</span></span>
  
> <span data-ttu-id="2c65f-147">请求使用读取和写入权限打开条目。</span><span class="sxs-lookup"><span data-stu-id="2c65f-147">Requests that the entry be opened with read and write permission.</span></span> <span data-ttu-id="2c65f-148">由于默认情况下使用只读访问权限打开条目，因此客户端不应假定已授予读取和写入权限，MAPI_MODIFY权限。</span><span class="sxs-lookup"><span data-stu-id="2c65f-148">Because entries are opened with read-only access by default, clients should not assume that read and write permission was granted regardless of whether MAPI_MODIFY is set.</span></span>
    
<span data-ttu-id="2c65f-149">MAPI_NO_CACHE</span><span class="sxs-lookup"><span data-stu-id="2c65f-149">MAPI_NO_CACHE</span></span>
  
> <span data-ttu-id="2c65f-150">请勿使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="2c65f-150">Do not use the offline address book to perform name resolution.</span></span> <span data-ttu-id="2c65f-151">此标志仅受通讯簿Exchange支持。</span><span class="sxs-lookup"><span data-stu-id="2c65f-151">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
 <span data-ttu-id="2c65f-152">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="2c65f-152">_lpulObjType_</span></span>
  
> <span data-ttu-id="2c65f-153">[out]指向打开的条目类型的指针。</span><span class="sxs-lookup"><span data-stu-id="2c65f-153">[out] A pointer to the type of the opened entry.</span></span>
    
 <span data-ttu-id="2c65f-154">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="2c65f-154">_lppUnk_</span></span>
  
> <span data-ttu-id="2c65f-155">[out]指向已打开条目的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2c65f-155">[out] A pointer to a pointer of the opened entry.</span></span>
    

