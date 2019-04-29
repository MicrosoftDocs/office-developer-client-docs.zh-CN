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
# <a name="iaddrbookcreateoneoff"></a><span data-ttu-id="a88f7-103">IAddrBook::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="a88f7-103">IAddrBook::CreateOneOff</span></span>

  
  
<span data-ttu-id="a88f7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a88f7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a88f7-105">为一次性地址创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a88f7-105">Creates an entry identifier for a one-off address.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="a88f7-106">参数</span><span class="sxs-lookup"><span data-stu-id="a88f7-106">Parameters</span></span>

 <span data-ttu-id="a88f7-107">_lpszName_</span><span class="sxs-lookup"><span data-stu-id="a88f7-107">_lpszName_</span></span>
  
> <span data-ttu-id="a88f7-108">实时指向收件人的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值的指针。</span><span class="sxs-lookup"><span data-stu-id="a88f7-108">[in] A pointer to the value of the recipient's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span> <span data-ttu-id="a88f7-109">_lpszName_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a88f7-109">The  _lpszName_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="a88f7-110">_lpszAdrType_</span><span class="sxs-lookup"><span data-stu-id="a88f7-110">_lpszAdrType_</span></span>
  
> <span data-ttu-id="a88f7-111">实时指向收件人的地址类型的指针, 如 "传真" 或 "SMTP"。</span><span class="sxs-lookup"><span data-stu-id="a88f7-111">[in] A pointer to the address type of the recipient, such as FAX or SMTP.</span></span> <span data-ttu-id="a88f7-112">_lpszAdrType_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a88f7-112">The  _lpszAdrType_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="a88f7-113">_lpszAddress_</span><span class="sxs-lookup"><span data-stu-id="a88f7-113">_lpszAddress_</span></span>
  
> <span data-ttu-id="a88f7-114">实时指向收件人地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a88f7-114">[in] A pointer to the address of the recipient.</span></span> <span data-ttu-id="a88f7-115">_lpszAddress_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a88f7-115">The  _lpszAddress_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="a88f7-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a88f7-116">_ulFlags_</span></span>
  
> <span data-ttu-id="a88f7-117">实时影响一次性收件人的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a88f7-117">[in] A bitmask of flags that affects the one-off recipient.</span></span> <span data-ttu-id="a88f7-118">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a88f7-118">The following flags can be set:</span></span>
    
<span data-ttu-id="a88f7-119">MAPI_SEND_NO_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="a88f7-119">MAPI_SEND_NO_RICH_INFO</span></span> 
  
> <span data-ttu-id="a88f7-120">收件人无法处理格式化的邮件内容。</span><span class="sxs-lookup"><span data-stu-id="a88f7-120">The recipient cannot handle formatted message content.</span></span> <span data-ttu-id="a88f7-121">如果设置了 MAPI_SEND_NO_RICH_INFO, MAPI 会将收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="a88f7-121">If MAPI_SEND_NO_RICH_INFO is set, MAPI sets the recipient's **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property to FALSE.</span></span> <span data-ttu-id="a88f7-122">如果未设置 MAPI_SEND_NO_RICH_INFO, 则 MAPI 会将此属性设置为 TRUE, 除非收件人指向的收件人的__ 邮件地址被解释为 Internet 地址。</span><span class="sxs-lookup"><span data-stu-id="a88f7-122">If MAPI_SEND_NO_RICH_INFO is not set, MAPI sets this property to TRUE unless the recipient's messaging address pointed to by  _lpszAddress_ is interpreted to be an Internet address.</span></span> <span data-ttu-id="a88f7-123">在这种情况下, MAPI 会将**PR_SEND_RICH_INFO**设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="a88f7-123">In this case, MAPI sets **PR_SEND_RICH_INFO** to FALSE.</span></span> 
    
<span data-ttu-id="a88f7-124">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a88f7-124">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a88f7-125">显示名称、地址类型和地址采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a88f7-125">The display name, address type, and address are in Unicode format.</span></span> <span data-ttu-id="a88f7-126">如果未设置 MAPI_UNICODE 标志, 则这些字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a88f7-126">If the MAPI_UNICODE flag is not set, these strings are in ANSI format.</span></span>
    
 <span data-ttu-id="a88f7-127">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="a88f7-127">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="a88f7-128">排除指向条目标识符中由_lppEntryID_参数指向的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="a88f7-128">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="a88f7-129">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="a88f7-129">_lppEntryID_</span></span>
  
> <span data-ttu-id="a88f7-130">排除指向一次性收件人的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a88f7-130">[out] A pointer to a pointer to the entry identifier for the one-off recipient.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a88f7-131">返回值</span><span class="sxs-lookup"><span data-stu-id="a88f7-131">Return value</span></span>

<span data-ttu-id="a88f7-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="a88f7-132">S_OK</span></span> 
  
> <span data-ttu-id="a88f7-133">已成功创建一次性条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a88f7-133">The one-off entry identifier was created successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a88f7-134">说明</span><span class="sxs-lookup"><span data-stu-id="a88f7-134">Remarks</span></span>

<span data-ttu-id="a88f7-135">客户端调用**CreateOneOff**方法为一次性收件人创建条目标识符, 即不属于任何当前已加载的通讯簿提供程序中任何容器的收件人。</span><span class="sxs-lookup"><span data-stu-id="a88f7-135">Clients call the **CreateOneOff** method to create an entry identifier for a one-off recipient — a recipient that does not belong to any of the containers from any of the currently loaded address book providers.</span></span> <span data-ttu-id="a88f7-136">一次性收件人可以具有该会话的一个活动通讯簿提供程序支持的任何类型的地址。</span><span class="sxs-lookup"><span data-stu-id="a88f7-136">One-off recipients can have any kind of address that is supported by one of the active address book providers for the session.</span></span> 
  
<span data-ttu-id="a88f7-137">一次性收件人通常是使用其特定地址类型的模板创建的。</span><span class="sxs-lookup"><span data-stu-id="a88f7-137">One-off recipients are typically created with a template for their particular address type.</span></span> <span data-ttu-id="a88f7-138">支持该地址类型的通讯簿提供程序提供该模板。</span><span class="sxs-lookup"><span data-stu-id="a88f7-138">The address book provider that supports the address type supplies the template.</span></span> <span data-ttu-id="a88f7-139">客户端应用程序的用户将相关信息输入到模板中。</span><span class="sxs-lookup"><span data-stu-id="a88f7-139">A user of a client application enters the relevant information into the template.</span></span>
  
<span data-ttu-id="a88f7-140">MAPI 支持**CreateOneOff**的显示名称、地址类型和地址参数的 Unicode 字符字符串。</span><span class="sxs-lookup"><span data-stu-id="a88f7-140">MAPI supports Unicode character strings for the display name, address type, and address parameters of **CreateOneOff**.</span></span>
  
<span data-ttu-id="a88f7-141">MAPI_SEND_NO_RICH_INFO 标志控制是否随每封邮件一起发送 rtf 格式的格式化文本。</span><span class="sxs-lookup"><span data-stu-id="a88f7-141">The MAPI_SEND_NO_RICH_INFO flag controls whether formatted text in Rich Text Format (RTF) is sent along with each message.</span></span> <span data-ttu-id="a88f7-142">传输中性封装格式 (TNEF) —一种用于传输格式化文本的格式, 它由大部分传输提供程序发送, 而不管收件人如何设置其**PR_SEND_RICH_INFO**属性。</span><span class="sxs-lookup"><span data-stu-id="a88f7-142">The Transport Neutral Encapsulation Format (TNEF) — a format that is used for transmitting formatted text — is sent by most transport providers, regardless of how the recipient sets its **PR_SEND_RICH_INFO** property.</span></span> <span data-ttu-id="a88f7-143">对于处理人际邮件的邮件客户端而言, 这并不是问题。</span><span class="sxs-lookup"><span data-stu-id="a88f7-143">This is not an issue for messaging clients that work with interpersonal messages.</span></span> <span data-ttu-id="a88f7-144">但是, 由于 TNEF 通常用于发送自定义邮件类别的自定义属性, 因此, 不支持需要自定义 MAPI 属性的基于表单的客户端或客户端可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="a88f7-144">However, because TNEF is typically used to send custom properties for custom message classes, not supporting it can be a problem for form-based clients or clients that require custom MAPI properties.</span></span> <span data-ttu-id="a88f7-145">有关详细信息, 请参阅[使用 TNEF 发送邮件](sending-messages-with-tnef.md)。</span><span class="sxs-lookup"><span data-stu-id="a88f7-145">For more information, see [Sending Messages with TNEF](sending-messages-with-tnef.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a88f7-146">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a88f7-146">MFCMAPI reference</span></span>

<span data-ttu-id="a88f7-147">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a88f7-147">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a88f7-148">**文件**</span><span class="sxs-lookup"><span data-stu-id="a88f7-148">**File**</span></span>|<span data-ttu-id="a88f7-149">**函数**</span><span class="sxs-lookup"><span data-stu-id="a88f7-149">**Function**</span></span>|<span data-ttu-id="a88f7-150">**备注**</span><span class="sxs-lookup"><span data-stu-id="a88f7-150">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a88f7-151">Mapiabfunctions</span><span class="sxs-lookup"><span data-stu-id="a88f7-151">Mapiabfunctions.cpp</span></span>  <br/> |<span data-ttu-id="a88f7-152">AddOneOffAddress</span><span class="sxs-lookup"><span data-stu-id="a88f7-152">AddOneOffAddress</span></span>  <br/> |<span data-ttu-id="a88f7-153">MFCMAPI 使用**CreateOneOff**方法为在任何通讯簿中找不到的地址创建条目 ID。</span><span class="sxs-lookup"><span data-stu-id="a88f7-153">MFCMAPI uses the **CreateOneOff** method to create an entry ID for an address that is not found in any address book.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a88f7-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a88f7-154">See also</span></span>



[<span data-ttu-id="a88f7-155">IMAPISupport::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="a88f7-155">IMAPISupport::CreateOneOff</span></span>](imapisupport-createoneoff.md)
  
[<span data-ttu-id="a88f7-156">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a88f7-156">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="a88f7-157">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a88f7-157">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

