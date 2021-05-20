---
title: IAddrBookCreateOneOff
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.CreateOneOff
api_type:
- COM
ms.assetid: bcacfbdf-edff-4810-a985-e6d2c9271901
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 980ac82c6f7fcb5771a6013b3fb033b0bdfd05e0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427379"
---
# <a name="iaddrbookcreateoneoff"></a><span data-ttu-id="cebb1-103">IAddrBook::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="cebb1-103">IAddrBook::CreateOneOff</span></span>

  
  
<span data-ttu-id="cebb1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cebb1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cebb1-105">为一次地址创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="cebb1-105">Creates an entry identifier for a one-off address.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="cebb1-106">参数</span><span class="sxs-lookup"><span data-stu-id="cebb1-106">Parameters</span></span>

 <span data-ttu-id="cebb1-107">_lpszName_</span><span class="sxs-lookup"><span data-stu-id="cebb1-107">_lpszName_</span></span>
  
> <span data-ttu-id="cebb1-108">[in]指向[PidTagDisplayName](pidtagdisplayname-canonical-property.md)属性中收件人PR_DISPLAY_NAME () 值的指针。</span><span class="sxs-lookup"><span data-stu-id="cebb1-108">[in] A pointer to the value of the recipient's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span> <span data-ttu-id="cebb1-109">_lpszName_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="cebb1-109">The  _lpszName_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="cebb1-110">_lpszAdrType_</span><span class="sxs-lookup"><span data-stu-id="cebb1-110">_lpszAdrType_</span></span>
  
> <span data-ttu-id="cebb1-111">[in]指向收件人的地址类型（如 FAX 或 SMTP）的指针。</span><span class="sxs-lookup"><span data-stu-id="cebb1-111">[in] A pointer to the address type of the recipient, such as FAX or SMTP.</span></span> <span data-ttu-id="cebb1-112">_lpszAdrType_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="cebb1-112">The  _lpszAdrType_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="cebb1-113">_lpszAddress_</span><span class="sxs-lookup"><span data-stu-id="cebb1-113">_lpszAddress_</span></span>
  
> <span data-ttu-id="cebb1-114">[in]指向收件人地址的指针。</span><span class="sxs-lookup"><span data-stu-id="cebb1-114">[in] A pointer to the address of the recipient.</span></span> <span data-ttu-id="cebb1-115">_lpszAddress_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="cebb1-115">The  _lpszAddress_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="cebb1-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="cebb1-116">_ulFlags_</span></span>
  
> <span data-ttu-id="cebb1-117">[in]影响一次收件人的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="cebb1-117">[in] A bitmask of flags that affects the one-off recipient.</span></span> <span data-ttu-id="cebb1-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="cebb1-118">The following flags can be set:</span></span>
    
<span data-ttu-id="cebb1-119">MAPI_SEND_NO_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="cebb1-119">MAPI_SEND_NO_RICH_INFO</span></span> 
  
> <span data-ttu-id="cebb1-120">收件人无法处理格式化的邮件内容。</span><span class="sxs-lookup"><span data-stu-id="cebb1-120">The recipient cannot handle formatted message content.</span></span> <span data-ttu-id="cebb1-121">如果MAPI_SEND_NO_RICH_INFO，MAPI 将收件人的 PR_SEND_RICH_INFO ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 设置为 FALSE。 </span><span class="sxs-lookup"><span data-stu-id="cebb1-121">If MAPI_SEND_NO_RICH_INFO is set, MAPI sets the recipient's **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property to FALSE.</span></span> <span data-ttu-id="cebb1-122">如果未MAPI_SEND_NO_RICH_INFO，MAPI 将此属性设置为 TRUE，除非  _lpszAddress_ 指向的收件人的邮件地址被解释为 Internet 地址。</span><span class="sxs-lookup"><span data-stu-id="cebb1-122">If MAPI_SEND_NO_RICH_INFO is not set, MAPI sets this property to TRUE unless the recipient's messaging address pointed to by  _lpszAddress_ is interpreted to be an Internet address.</span></span> <span data-ttu-id="cebb1-123">在这种情况下，MAPI **将PR_SEND_RICH_INFO** FALSE。</span><span class="sxs-lookup"><span data-stu-id="cebb1-123">In this case, MAPI sets **PR_SEND_RICH_INFO** to FALSE.</span></span> 
    
<span data-ttu-id="cebb1-124">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cebb1-124">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="cebb1-125">该显示名称、地址类型和地址采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="cebb1-125">The display name, address type, and address are in Unicode format.</span></span> <span data-ttu-id="cebb1-126">如果未MAPI_UNICODE，则这些字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="cebb1-126">If the MAPI_UNICODE flag is not set, these strings are in ANSI format.</span></span>
    
 <span data-ttu-id="cebb1-127">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="cebb1-127">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="cebb1-128">[out]指向  _lppEntryID_ 参数指向的条目标识符中的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="cebb1-128">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="cebb1-129">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="cebb1-129">_lppEntryID_</span></span>
  
> <span data-ttu-id="cebb1-130">[out]指向指向一次收件人的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="cebb1-130">[out] A pointer to a pointer to the entry identifier for the one-off recipient.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="cebb1-131">返回值</span><span class="sxs-lookup"><span data-stu-id="cebb1-131">Return value</span></span>

<span data-ttu-id="cebb1-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="cebb1-132">S_OK</span></span> 
  
> <span data-ttu-id="cebb1-133">已成功创建一次项标识符。</span><span class="sxs-lookup"><span data-stu-id="cebb1-133">The one-off entry identifier was created successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cebb1-134">备注</span><span class="sxs-lookup"><span data-stu-id="cebb1-134">Remarks</span></span>

<span data-ttu-id="cebb1-135">客户端调用 **CreateOneOff** 方法为一次收件人（不属于任何当前加载的通讯簿提供程序的任何容器的收件人）创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="cebb1-135">Clients call the **CreateOneOff** method to create an entry identifier for a one-off recipient — a recipient that does not belong to any of the containers from any of the currently loaded address book providers.</span></span> <span data-ttu-id="cebb1-136">一对一收件人可以拥有会话的一个活动通讯簿提供程序支持的任何一种地址。</span><span class="sxs-lookup"><span data-stu-id="cebb1-136">One-off recipients can have any kind of address that is supported by one of the active address book providers for the session.</span></span> 
  
<span data-ttu-id="cebb1-137">一次收件人通常使用特定地址类型的模板创建。</span><span class="sxs-lookup"><span data-stu-id="cebb1-137">One-off recipients are typically created with a template for their particular address type.</span></span> <span data-ttu-id="cebb1-138">支持地址类型的通讯簿提供程序提供模板。</span><span class="sxs-lookup"><span data-stu-id="cebb1-138">The address book provider that supports the address type supplies the template.</span></span> <span data-ttu-id="cebb1-139">客户端应用程序的用户将相关信息输入到模板中。</span><span class="sxs-lookup"><span data-stu-id="cebb1-139">A user of a client application enters the relevant information into the template.</span></span>
  
<span data-ttu-id="cebb1-140">MAPI 支持 CreateOneOff 的 显示名称、地址类型和地址参数的 **Unicode 字符字符串**。</span><span class="sxs-lookup"><span data-stu-id="cebb1-140">MAPI supports Unicode character strings for the display name, address type, and address parameters of **CreateOneOff**.</span></span>
  
<span data-ttu-id="cebb1-141">此MAPI_SEND_NO_RICH_INFO标志控制 RTF 格式格式 (格式) 文本是否随每封邮件一起发送。</span><span class="sxs-lookup"><span data-stu-id="cebb1-141">The MAPI_SEND_NO_RICH_INFO flag controls whether formatted text in Rich Text Format (RTF) is sent along with each message.</span></span> <span data-ttu-id="cebb1-142">传输中性封装格式 (TNEF) （一种用于传输格式文本的格式）由大多数传输提供程序发送，而不管收件人如何设置其 **PR_SEND_RICH_INFO** 属性。</span><span class="sxs-lookup"><span data-stu-id="cebb1-142">The Transport Neutral Encapsulation Format (TNEF) — a format that is used for transmitting formatted text — is sent by most transport providers, regardless of how the recipient sets its **PR_SEND_RICH_INFO** property.</span></span> <span data-ttu-id="cebb1-143">对于处理不和谐消息的邮件客户端，这不是问题。</span><span class="sxs-lookup"><span data-stu-id="cebb1-143">This is not an issue for messaging clients that work with interpersonal messages.</span></span> <span data-ttu-id="cebb1-144">但是，由于 TNEF 通常用于发送自定义邮件类的自定义属性，因此不支持它可能是基于表单的客户端或需要自定义 MAPI 属性的客户端的问题。</span><span class="sxs-lookup"><span data-stu-id="cebb1-144">However, because TNEF is typically used to send custom properties for custom message classes, not supporting it can be a problem for form-based clients or clients that require custom MAPI properties.</span></span> <span data-ttu-id="cebb1-145">有关详细信息，请参阅使用 [TNEF 发送邮件](sending-messages-with-tnef.md)。</span><span class="sxs-lookup"><span data-stu-id="cebb1-145">For more information, see [Sending Messages with TNEF](sending-messages-with-tnef.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="cebb1-146">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="cebb1-146">MFCMAPI reference</span></span>

<span data-ttu-id="cebb1-147">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="cebb1-147">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="cebb1-148">**文件**</span><span class="sxs-lookup"><span data-stu-id="cebb1-148">**File**</span></span>|<span data-ttu-id="cebb1-149">**函数**</span><span class="sxs-lookup"><span data-stu-id="cebb1-149">**Function**</span></span>|<span data-ttu-id="cebb1-150">**备注**</span><span class="sxs-lookup"><span data-stu-id="cebb1-150">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cebb1-151">Mapiabfunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="cebb1-151">Mapiabfunctions.cpp</span></span>  <br/> |<span data-ttu-id="cebb1-152">AddOneOffAddress</span><span class="sxs-lookup"><span data-stu-id="cebb1-152">AddOneOffAddress</span></span>  <br/> |<span data-ttu-id="cebb1-153">MFCMAPI 使用 **CreateOneOff** 方法为在任何通讯簿中找不到的地址创建条目 ID。</span><span class="sxs-lookup"><span data-stu-id="cebb1-153">MFCMAPI uses the **CreateOneOff** method to create an entry ID for an address that is not found in any address book.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cebb1-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cebb1-154">See also</span></span>



[<span data-ttu-id="cebb1-155">IMAPISupport::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="cebb1-155">IMAPISupport::CreateOneOff</span></span>](imapisupport-createoneoff.md)
  
[<span data-ttu-id="cebb1-156">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="cebb1-156">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="cebb1-157">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="cebb1-157">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

