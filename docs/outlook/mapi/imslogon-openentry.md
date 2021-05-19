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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 544aaaace18a9d26972e6484803b63a1ee7060fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416298"
---
# <a name="imslogonopenentry"></a><span data-ttu-id="53567-103">IMSLogon::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="53567-103">IMSLogon::OpenEntry</span></span>

  
  
<span data-ttu-id="53567-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53567-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53567-105">打开文件夹或邮件对象，并返回指向该对象的指针以提供进一步的访问。</span><span class="sxs-lookup"><span data-stu-id="53567-105">Opens a folder or message object and returns a pointer to the object to provide further access.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="53567-106">参数</span><span class="sxs-lookup"><span data-stu-id="53567-106">Parameters</span></span>

 <span data-ttu-id="53567-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="53567-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="53567-108">[in]  _lpEntryID_ 参数指向的条目标识符的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="53567-108">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="53567-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="53567-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="53567-110">[in]指向要打开的文件夹或邮件对象的条目标识符的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="53567-110">[in] A pointer to the address of the entry identifier of the folder or message object to open.</span></span> 
    
 <span data-ttu-id="53567-111">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="53567-111">_lpInterface_</span></span>
  
> <span data-ttu-id="53567-112">[in]指向对象的 IID (接口) 指针。</span><span class="sxs-lookup"><span data-stu-id="53567-112">[in] A pointer to the interface identifier (IID) for the object.</span></span> <span data-ttu-id="53567-113">传递 NULL 表示对象被强制转换到此类对象的标准接口。</span><span class="sxs-lookup"><span data-stu-id="53567-113">Passing NULL indicates that the object is cast to the standard interface for such an object.</span></span> <span data-ttu-id="53567-114">_还可以将 lpInterface_ 参数设置为对象相应接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="53567-114">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the object.</span></span> 
    
 <span data-ttu-id="53567-115">_ulOpenFlags_</span><span class="sxs-lookup"><span data-stu-id="53567-115">_ulOpenFlags_</span></span>
  
> <span data-ttu-id="53567-116">[in]控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="53567-116">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="53567-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="53567-117">The following flags can be set:</span></span>
    
<span data-ttu-id="53567-118">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="53567-118">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="53567-119">该对象应该使用用户允许的最大权限和最大客户端应用程序权限打开。</span><span class="sxs-lookup"><span data-stu-id="53567-119">The object should be opened with the maximum permissions allowed for the user and the maximum client application permissions.</span></span> <span data-ttu-id="53567-120">例如，如果客户端具有读/写权限，则使用读/写权限打开对象;如果客户端具有只读权限，则使用只读权限打开对象。</span><span class="sxs-lookup"><span data-stu-id="53567-120">For example, if the client has read/write permission, the object is opened with read/write permission; if the client has read-only permission, the object is opened with read-only permission.</span></span> <span data-ttu-id="53567-121">客户端可以通过获取[PidTagAccessLevel](pidtagaccesslevel-canonical-property.md) PR_ACCESS_LEVEL (权限) 级别。 </span><span class="sxs-lookup"><span data-stu-id="53567-121">The client can retrieve the permission level by getting the **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="53567-122">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="53567-122">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="53567-123">即使基础对象对调用应用程序不可用，也允许调用成功。</span><span class="sxs-lookup"><span data-stu-id="53567-123">The call is allowed to succeed even if the underlying object is not available to the calling application.</span></span> <span data-ttu-id="53567-124">如果该对象不可用，则对该对象的后续调用可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="53567-124">If the object is not available, a subsequent call to the object might return an error.</span></span>
    
<span data-ttu-id="53567-125">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="53567-125">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="53567-126">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="53567-126">Requests read/write permission.</span></span> <span data-ttu-id="53567-127">默认情况下，使用只读权限创建对象，客户端不应在已授予读/写权限的假设下工作。</span><span class="sxs-lookup"><span data-stu-id="53567-127">By default, objects are created with read-only permission, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="53567-128">_lpulObjType_</span><span class="sxs-lookup"><span data-stu-id="53567-128">_lpulObjType_</span></span>
  
> <span data-ttu-id="53567-129">[out]指向已打开对象的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="53567-129">[out] A pointer to the type of the opened object.</span></span>
    
 <span data-ttu-id="53567-130">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="53567-130">_lppUnk_</span></span>
  
> <span data-ttu-id="53567-131">[out]指向已打开对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="53567-131">[out] A pointer to the pointer to the opened object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="53567-132">返回值</span><span class="sxs-lookup"><span data-stu-id="53567-132">Return value</span></span>

<span data-ttu-id="53567-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="53567-133">S_OK</span></span> 
  
> <span data-ttu-id="53567-134">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="53567-134">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="53567-135">备注</span><span class="sxs-lookup"><span data-stu-id="53567-135">Remarks</span></span>

<span data-ttu-id="53567-136">MAPI 调用 **IMSLogon：：OpenEntry** 方法打开邮件存储中的文件夹或邮件。</span><span class="sxs-lookup"><span data-stu-id="53567-136">MAPI calls the **IMSLogon::OpenEntry** method to open a folder or a message in a message store.</span></span> <span data-ttu-id="53567-137">MAPI 将传递要打开的对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="53567-137">MAPI passes in the entry identifier of the object to open.</span></span> <span data-ttu-id="53567-138">邮件存储提供程序应返回一个指针，允许进一步访问  _lppUnk_ 参数中指定的对象。</span><span class="sxs-lookup"><span data-stu-id="53567-138">The message store provider should return a pointer that enables further access to the object specified in the  _lppUnk_ parameter.</span></span> 
  
<span data-ttu-id="53567-139">在 MAPI 调用 **IMSLogon：：OpenEntry** 之前，它首先确定给定的邮件或文件夹条目标识符与由此消息存储提供程序注册的邮件或文件夹条目标识符匹配。</span><span class="sxs-lookup"><span data-stu-id="53567-139">Before MAPI calls **IMSLogon::OpenEntry**, it first determines that the given message or folder entry identifier matches one registered by this message store provider.</span></span> <span data-ttu-id="53567-140">有关存储提供程序如何注册条目标识符的信息，请参阅 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md)。</span><span class="sxs-lookup"><span data-stu-id="53567-140">For more information about how store providers register entry identifiers, see [IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md).</span></span>
  
 <span data-ttu-id="53567-141">**IMSLogon：：OpenEntry** 与消息存储对象的 [IMsgStore：：OpenEntry](imsgstore-openentry.md)方法相同，只不过客户端不调用 **IMSLogon：：OpenEntry**;MAPI 在处理 **IMAPISession：：OpenEntry 方法时调用 IMSLogon：：OpenEntry。** </span><span class="sxs-lookup"><span data-stu-id="53567-141">**IMSLogon::OpenEntry** is identical to the [IMsgStore::OpenEntry](imsgstore-openentry.md) method of the message store object, except that the client does not call **IMSLogon::OpenEntry**; MAPI calls **IMSLogon::OpenEntry** when it processes an **IMAPISession::OpenEntry** method.</span></span> <span data-ttu-id="53567-142">使用 **IMSLogon：：OpenEntry** 打开的对象处理方式应该与使用消息存储对象打开的对象完全相同;特别是，当释放邮件存储对象时，使用此调用打开的对象应失效。</span><span class="sxs-lookup"><span data-stu-id="53567-142">Objects opened by using **IMSLogon::OpenEntry** should be treated exactly the same as objects opened by using the message store object; in particular, objects opened by using this call should be invalidated when the message store object is released.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="53567-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53567-143">See also</span></span>



[<span data-ttu-id="53567-144">IMAPISupport::SetProviderUID</span><span class="sxs-lookup"><span data-stu-id="53567-144">IMAPISupport::SetProviderUID</span></span>](imapisupport-setprovideruid.md)
  
[<span data-ttu-id="53567-145">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="53567-145">IMsgStore::OpenEntry</span></span>](imsgstore-openentry.md)
  
[<span data-ttu-id="53567-146">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="53567-146">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

