---
title: IMAPISupportCreateOneOff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CreateOneOff
api_type:
- COM
ms.assetid: ee57d6e0-9de0-4427-97ce-371c1c01f3de
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9571d51e01c2d58d9b8a9a913ba2c210ae0bd44d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411993"
---
# <a name="imapisupportcreateoneoff"></a><span data-ttu-id="2c8fe-103">IMAPISupport::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="2c8fe-103">IMAPISupport::CreateOneOff</span></span>

  
  
<span data-ttu-id="2c8fe-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2c8fe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2c8fe-105">为一次性地址创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-105">Creates an entry identifier for a one-off address.</span></span>
  
```cpp
HRESULT CreateOneOff(
  LPSTR lpszName,
  LPSTR lpszAdrType,
  LPSTR lpszAddress,
  ULONG ulFlags,
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="2c8fe-106">参数</span><span class="sxs-lookup"><span data-stu-id="2c8fe-106">Parameters</span></span>

 <span data-ttu-id="2c8fe-107">_lpszName_</span><span class="sxs-lookup"><span data-stu-id="2c8fe-107">_lpszName_</span></span>
  
> <span data-ttu-id="2c8fe-108">实时指向收件人的显示名称的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的指针。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-108">[in] A pointer to the display name of the recipient the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span> <span data-ttu-id="2c8fe-109">_lpszName_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-109">The  _lpszName_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="2c8fe-110">_lpszAdrType_</span><span class="sxs-lookup"><span data-stu-id="2c8fe-110">_lpszAdrType_</span></span>
  
> <span data-ttu-id="2c8fe-111">实时指向收件人的地址类型 (如传真、SMTP 或 X500) 的指针。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-111">[in] A pointer to the address type (such as FAX, SMTP, or X500) of the recipient.</span></span> <span data-ttu-id="2c8fe-112">_lpszAdrType_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-112">The  _lpszAdrType_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="2c8fe-113">_lpszAddress_</span><span class="sxs-lookup"><span data-stu-id="2c8fe-113">_lpszAddress_</span></span>
  
> <span data-ttu-id="2c8fe-114">实时指向收件人的邮件地址的指针。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-114">[in] A pointer to the messaging address of the recipient.</span></span> <span data-ttu-id="2c8fe-115">_lpszAddress_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-115">The  _lpszAddress_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="2c8fe-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2c8fe-116">_ulFlags_</span></span>
  
> <span data-ttu-id="2c8fe-117">实时影响一次性收件人的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-117">[in] A bitmask of flags that affects the one-off recipient.</span></span> <span data-ttu-id="2c8fe-118">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2c8fe-118">The following flags can be set:</span></span>
    
<span data-ttu-id="2c8fe-119">MAPI_SEND_NO_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="2c8fe-119">MAPI_SEND_NO_RICH_INFO</span></span> 
  
> <span data-ttu-id="2c8fe-120">收件人无法处理格式化的邮件内容。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-120">The recipient cannot handle formatted message content.</span></span> <span data-ttu-id="2c8fe-121">如果设置了 MAPI_SEND_NO_RICH_INFO, MAPI 会将收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-121">If MAPI_SEND_NO_RICH_INFO is set, MAPI sets the recipient's **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property to FALSE.</span></span> <span data-ttu-id="2c8fe-122">如果未设置 MAPI_SEND_NO_RICH_INFO, 则 MAPI 会将此属性设置为 TRUE, 除非收件人指向的收件人的__ 邮件地址被解释为 Internet 地址。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-122">If MAPI_SEND_NO_RICH_INFO is not set, MAPI sets this property to TRUE unless the recipient's messaging address pointed to by  _lpszAddress_ is interpreted to be an Internet address.</span></span> <span data-ttu-id="2c8fe-123">在这种情况下, MAPI 会将**PR_SEND_RICH_INFO**设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-123">In this case, MAPI sets **PR_SEND_RICH_INFO** to FALSE.</span></span> 
    
<span data-ttu-id="2c8fe-124">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2c8fe-124">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="2c8fe-125">显示名称、地址类型和地址采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-125">The display name, address type, and address are in Unicode format.</span></span> <span data-ttu-id="2c8fe-126">如果未设置 MAPI_UNICODE 标志, 则这些字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-126">If the MAPI_UNICODE flag is not set, these strings are in ANSI format.</span></span>
    
 <span data-ttu-id="2c8fe-127">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="2c8fe-127">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="2c8fe-128">排除一个指针, 指向_lppEntryID_参数指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-128">[out] A pointer to the count of bytes in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="2c8fe-129">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="2c8fe-129">_lppEntryID_</span></span>
  
> <span data-ttu-id="2c8fe-130">排除指向一次性收件人的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-130">[out] A pointer to a pointer to the entry identifier for the one-off recipient.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2c8fe-131">返回值</span><span class="sxs-lookup"><span data-stu-id="2c8fe-131">Return value</span></span>

<span data-ttu-id="2c8fe-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c8fe-132">S_OK</span></span> 
  
> <span data-ttu-id="2c8fe-133">已成功创建一次性条目标识符。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-133">The one-off entry identifier was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2c8fe-134">说明</span><span class="sxs-lookup"><span data-stu-id="2c8fe-134">Remarks</span></span>

<span data-ttu-id="2c8fe-135">**IMAPISupport:: CreateOneOff**方法是为所有服务提供程序支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-135">The **IMAPISupport::CreateOneOff** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="2c8fe-136">服务提供程序调用**CreateOneOff**为一次性收件人 (不属于任何当前已加载的通讯簿提供程序中的任何容器的收件人) 创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-136">Service providers call **CreateOneOff** to create an entry identifier for a one-off recipient (a recipient that does not belong to any of the containers from any of the currently loaded address book providers).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="2c8fe-137">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2c8fe-137">Notes to callers</span></span>

<span data-ttu-id="2c8fe-138">使用**CreateOneOff**返回的条目标识符完成后, 使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放为条目标识符分配的内存。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-138">When you are finished using the entry identifier returned by **CreateOneOff**, free the memory allocated for the entry identifier by using the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="notes-to-transport-providers"></a><span data-ttu-id="2c8fe-139">传输提供程序注意事项</span><span class="sxs-lookup"><span data-stu-id="2c8fe-139">Notes to Transport Providers</span></span>

<span data-ttu-id="2c8fe-140">支持传输中性封装格式 (TNEF), 并使用**PR_SEND_RICH_INFO**属性的值来确定是否在传输邮件时使用 TNEF。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-140">Support the Transport Neutral Encapsulation Format (TNEF) and use the value of the **PR_SEND_RICH_INFO** property to determine whether to use TNEF when you transport a message.</span></span> <span data-ttu-id="2c8fe-141">如果不支持 TNEF 或在请求邮件时不以这种格式发送邮件, 则可能会对需要自定义 MAPI 属性的基于表单的客户端或客户端产生问题。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-141">Not supporting TNEF or not sending a message in this format when it is requested can be a problem for form-based clients or clients that require custom MAPI properties.</span></span> <span data-ttu-id="2c8fe-142">这是因为 TNEF 通常用于发送自定义邮件类的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="2c8fe-142">This is because TNEF is typically used to send custom properties for custom message classes.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2c8fe-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c8fe-143">See also</span></span>



[<span data-ttu-id="2c8fe-144">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="2c8fe-144">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="2c8fe-145">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="2c8fe-145">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)
  
[<span data-ttu-id="2c8fe-146">PidTagSendRichInfo 规范属性</span><span class="sxs-lookup"><span data-stu-id="2c8fe-146">PidTagSendRichInfo Canonical Property</span></span>](pidtagsendrichinfo-canonical-property.md)
  
[<span data-ttu-id="2c8fe-147">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2c8fe-147">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

