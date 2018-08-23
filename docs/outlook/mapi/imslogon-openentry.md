---
title: IMSLogonOpenEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.OpenEntry
api_type:
- COM
ms.assetid: 612cbab7-60cb-48bb-906e-18d9135e7a86
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 619357a608dd160cbe4811cc7db7ae3b392db858
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576888"
---
# <a name="imslogonopenentry"></a><span data-ttu-id="9a657-103">IMSLogon::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="9a657-103">IMSLogon::OpenEntry</span></span>

  
  
<span data-ttu-id="9a657-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9a657-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9a657-105">打开文件夹或 message 对象并返回指向要进一步提供访问权限的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9a657-105">Opens a folder or message object and returns a pointer to the object to provide further access.</span></span> 
  
```cpp
HRESULT OpenEntry(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulOpenFlags,
  ULONG FAR * lpulObjType,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="9a657-106">参数</span><span class="sxs-lookup"><span data-stu-id="9a657-106">Parameters</span></span>

 <span data-ttu-id="9a657-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="9a657-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="9a657-108">[in]以字节为单位_lpEntryID_参数指向的项标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="9a657-108">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="9a657-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="9a657-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="9a657-110">[in]指向要打开的文件夹或邮件的对象的项标识符的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9a657-110">[in] A pointer to the address of the entry identifier of the folder or message object to open.</span></span> 
    
 <span data-ttu-id="9a657-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="9a657-111">_lpInterface_</span></span>
  
> <span data-ttu-id="9a657-112">[in]指向对象的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="9a657-112">[in] A pointer to the interface identifier (IID) for the object.</span></span> <span data-ttu-id="9a657-113">传递 NULL 指示，该对象强制转换为标准接口此类对象。</span><span class="sxs-lookup"><span data-stu-id="9a657-113">Passing NULL indicates that the object is cast to the standard interface for such an object.</span></span> <span data-ttu-id="9a657-114">_LpInterface_参数还可以设置为适当的接口的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="9a657-114">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the object.</span></span> 
    
 <span data-ttu-id="9a657-115">_ulOpenFlags_</span><span class="sxs-lookup"><span data-stu-id="9a657-115">_ulOpenFlags_</span></span>
  
> <span data-ttu-id="9a657-116">[in]位掩码的标志，控制如何打开对象。</span><span class="sxs-lookup"><span data-stu-id="9a657-116">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="9a657-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="9a657-117">The following flags can be set:</span></span>
    
<span data-ttu-id="9a657-118">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="9a657-118">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="9a657-119">应与为用户和最大客户端应用程序权限允许的最大权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="9a657-119">The object should be opened with the maximum permissions allowed for the user and the maximum client application permissions.</span></span> <span data-ttu-id="9a657-120">例如，如果客户端具有读/写权限，则对象打开具有读/写权限;如果客户端具有只读权限，则打开对象时具有只读权限。</span><span class="sxs-lookup"><span data-stu-id="9a657-120">For example, if the client has read/write permission, the object is opened with read/write permission; if the client has read-only permission, the object is opened with read-only permission.</span></span> <span data-ttu-id="9a657-121">客户端可以通过获取**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性来检索的权限级别。</span><span class="sxs-lookup"><span data-stu-id="9a657-121">The client can retrieve the permission level by getting the **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="9a657-122">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="9a657-122">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="9a657-123">若要成功执行，即使基础对象不是可用于呼叫的应用程序，即允许该呼叫。</span><span class="sxs-lookup"><span data-stu-id="9a657-123">The call is allowed to succeed even if the underlying object is not available to the calling application.</span></span> <span data-ttu-id="9a657-124">如果对象不可用，对对象的后续调用可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="9a657-124">If the object is not available, a subsequent call to the object might return an error.</span></span>
    
<span data-ttu-id="9a657-125">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="9a657-125">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="9a657-126">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="9a657-126">Requests read/write permission.</span></span> <span data-ttu-id="9a657-127">默认情况下，对象在创建具有只读权限，并以为，读/写权限授予客户端不起作用。</span><span class="sxs-lookup"><span data-stu-id="9a657-127">By default, objects are created with read-only permission, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="9a657-128">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="9a657-128">_lpulObjType_</span></span>
  
> <span data-ttu-id="9a657-129">[输出]一个指向打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="9a657-129">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="9a657-130">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="9a657-130">_lppUnk_</span></span>
  
> <span data-ttu-id="9a657-131">[输出]指向打开的对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="9a657-131">[out] A pointer to the pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9a657-132">返回值</span><span class="sxs-lookup"><span data-stu-id="9a657-132">Return value</span></span>

<span data-ttu-id="9a657-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a657-133">S_OK</span></span> 
  
> <span data-ttu-id="9a657-134">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="9a657-134">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9a657-135">注解</span><span class="sxs-lookup"><span data-stu-id="9a657-135">Remarks</span></span>

<span data-ttu-id="9a657-136">MAPI 调用**IMSLogon::OpenEntry**方法打开邮件存储区中的文件夹或一条消息。</span><span class="sxs-lookup"><span data-stu-id="9a657-136">MAPI calls the **IMSLogon::OpenEntry** method to open a folder or a message in a message store.</span></span> <span data-ttu-id="9a657-137">要打开的对象的项标识符中传递 MAPI。</span><span class="sxs-lookup"><span data-stu-id="9a657-137">MAPI passes in the entry identifier of the object to open.</span></span> <span data-ttu-id="9a657-138">消息存储提供程序应返回使进一步访问_lppUnk_参数中指定的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9a657-138">The message store provider should return a pointer that enables further access to the object specified in the  _lppUnk_ parameter.</span></span> 
  
<span data-ttu-id="9a657-139">MAPI 调用**IMSLogon::OpenEntry**之前，首先确定给定的邮件或文件夹条目标识符匹配一个注册的此消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="9a657-139">Before MAPI calls **IMSLogon::OpenEntry**, it first determines that the given message or folder entry identifier matches one registered by this message store provider.</span></span> <span data-ttu-id="9a657-140">有关如何存储提供程序注册项标识符的详细信息，请参阅[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)。</span><span class="sxs-lookup"><span data-stu-id="9a657-140">For more information about how store providers register entry identifiers, see [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md).</span></span>
  
 <span data-ttu-id="9a657-141">**IMSLogon::OpenEntry**相同的[IMsgStore::OpenEntry](imsgstore-openentry.md)方法的消息存储对象，只是客户端不会调用**IMSLogon::OpenEntry**;MAPI 调用**IMSLogon::OpenEntry**处理**IMAPISession::OpenEntry**方法时。</span><span class="sxs-lookup"><span data-stu-id="9a657-141">**IMSLogon::OpenEntry** is identical to the [IMsgStore::OpenEntry](imsgstore-openentry.md) method of the message store object, except that the client does not call **IMSLogon::OpenEntry**; MAPI calls **IMSLogon::OpenEntry** when it processes an **IMAPISession::OpenEntry** method.</span></span> <span data-ttu-id="9a657-142">应使用**IMSLogon::OpenEntry**打开的对象会被视为完全相同对象打开使用消息存储对象;具体而言，发布的消息存储对象时，应无效对象使用此呼叫打开。</span><span class="sxs-lookup"><span data-stu-id="9a657-142">Objects opened by using **IMSLogon::OpenEntry** should be treated exactly the same as objects opened by using the message store object; in particular, objects opened by using this call should be invalidated when the message store object is released.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9a657-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a657-143">See also</span></span>



[<span data-ttu-id="9a657-144">IMAPISupport::SetProviderUID</span><span class="sxs-lookup"><span data-stu-id="9a657-144">IMAPISupport::SetProviderUID</span></span>](imapisupport-setprovideruid.md)
  
[<span data-ttu-id="9a657-145">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="9a657-145">IMsgStore::OpenEntry</span></span>](imsgstore-openentry.md)
  
[<span data-ttu-id="9a657-146">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9a657-146">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

