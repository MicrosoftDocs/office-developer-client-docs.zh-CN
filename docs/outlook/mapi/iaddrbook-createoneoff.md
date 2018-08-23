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
ms.openlocfilehash: ddb87af4b14be6d728bcceddb4d958ba49229ad4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579037"
---
# <a name="iaddrbookcreateoneoff"></a><span data-ttu-id="c9b98-103">IAddrBook::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="c9b98-103">IAddrBook::CreateOneOff</span></span>

  
  
<span data-ttu-id="c9b98-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c9b98-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c9b98-105">创建一个一次性地址的项标识符。</span><span class="sxs-lookup"><span data-stu-id="c9b98-105">Creates an entry identifier for a one-off address.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="c9b98-106">参数</span><span class="sxs-lookup"><span data-stu-id="c9b98-106">Parameters</span></span>

 <span data-ttu-id="c9b98-107">_lpszName_</span><span class="sxs-lookup"><span data-stu-id="c9b98-107">_lpszName_</span></span>
  
> <span data-ttu-id="c9b98-108">[in]一个指向收件人的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="c9b98-108">[in] A pointer to the value of the recipient's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span> <span data-ttu-id="c9b98-109">_LpszName_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="c9b98-109">The  _lpszName_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="c9b98-110">_lpszAdrType_</span><span class="sxs-lookup"><span data-stu-id="c9b98-110">_lpszAdrType_</span></span>
  
> <span data-ttu-id="c9b98-111">[in]一个指向的收件人，例如传真或 SMTP 地址类型。</span><span class="sxs-lookup"><span data-stu-id="c9b98-111">[in] A pointer to the address type of the recipient, such as FAX or SMTP.</span></span> <span data-ttu-id="c9b98-112">_LpszAdrType_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c9b98-112">The  _lpszAdrType_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="c9b98-113">_lpszAddress_</span><span class="sxs-lookup"><span data-stu-id="c9b98-113">_lpszAddress_</span></span>
  
> <span data-ttu-id="c9b98-114">[in]一个指向收件人的地址。</span><span class="sxs-lookup"><span data-stu-id="c9b98-114">[in] A pointer to the address of the recipient.</span></span> <span data-ttu-id="c9b98-115">_LpszAddress_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c9b98-115">The  _lpszAddress_ parameter cannot be NULL.</span></span> 
    
 <span data-ttu-id="c9b98-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c9b98-116">_ulFlags_</span></span>
  
> <span data-ttu-id="c9b98-117">[in]位掩码的标志影响一次性收件人。</span><span class="sxs-lookup"><span data-stu-id="c9b98-117">[in] A bitmask of flags that affects the one-off recipient.</span></span> <span data-ttu-id="c9b98-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="c9b98-118">The following flags can be set:</span></span>
    
<span data-ttu-id="c9b98-119">MAPI_SEND_NO_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="c9b98-119">MAPI_SEND_NO_RICH_INFO</span></span> 
  
> <span data-ttu-id="c9b98-120">收件人无法处理格式化的消息内容。</span><span class="sxs-lookup"><span data-stu-id="c9b98-120">The recipient cannot handle formatted message content.</span></span> <span data-ttu-id="c9b98-121">如果设置 MAPI_SEND_NO_RICH_INFO，MAPI 将收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="c9b98-121">If MAPI_SEND_NO_RICH_INFO is set, MAPI sets the recipient's **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property to FALSE.</span></span> <span data-ttu-id="c9b98-122">如果未设置 MAPI_SEND_NO_RICH_INFO，MAPI 设为 true，此属性，除非由_lpszAddress_指向的收件人的消息地址被解释为 Internet 地址。</span><span class="sxs-lookup"><span data-stu-id="c9b98-122">If MAPI_SEND_NO_RICH_INFO is not set, MAPI sets this property to TRUE unless the recipient's messaging address pointed to by  _lpszAddress_ is interpreted to be an Internet address.</span></span> <span data-ttu-id="c9b98-123">在这种情况下，MAPI 将**PR_SEND_RICH_INFO**设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="c9b98-123">In this case, MAPI sets **PR_SEND_RICH_INFO** to FALSE.</span></span> 
    
<span data-ttu-id="c9b98-124">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="c9b98-124">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="c9b98-125">显示名称、 地址类型和地址采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="c9b98-125">The display name, address type, and address are in Unicode format.</span></span> <span data-ttu-id="c9b98-126">如果未设置 MAPI_UNICODE 标志，这些字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="c9b98-126">If the MAPI_UNICODE flag is not set, these strings are in ANSI format.</span></span>
    
 <span data-ttu-id="c9b98-127">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="c9b98-127">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="c9b98-128">[输出]一个指向_lppEntryID_参数指向该条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="c9b98-128">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="c9b98-129">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="c9b98-129">_lppEntryID_</span></span>
  
> <span data-ttu-id="c9b98-130">[输出]指向一次性收件人的项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c9b98-130">[out] A pointer to a pointer to the entry identifier for the one-off recipient.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c9b98-131">返回值</span><span class="sxs-lookup"><span data-stu-id="c9b98-131">Return value</span></span>

<span data-ttu-id="c9b98-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9b98-132">S_OK</span></span> 
  
> <span data-ttu-id="c9b98-133">一次性条目标识符已成功创建。</span><span class="sxs-lookup"><span data-stu-id="c9b98-133">The one-off entry identifier was created successfully.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c9b98-134">注解</span><span class="sxs-lookup"><span data-stu-id="c9b98-134">Remarks</span></span>

<span data-ttu-id="c9b98-135">客户端调用**CreateOneOff**方法创建的项标识符一次性收件人 — 不属于任何容器与任何当前加载的地址簿提供程序的收件人。</span><span class="sxs-lookup"><span data-stu-id="c9b98-135">Clients call the **CreateOneOff** method to create an entry identifier for a one-off recipient — a recipient that does not belong to any of the containers from any of the currently loaded address book providers.</span></span> <span data-ttu-id="c9b98-136">一次性收件人可以会话有任何一种由一个活动地址簿提供程序支持的地址。</span><span class="sxs-lookup"><span data-stu-id="c9b98-136">One-off recipients can have any kind of address that is supported by one of the active address book providers for the session.</span></span> 
  
<span data-ttu-id="c9b98-137">一次性收件人通常是使用其特定地址类型的模板创建的。</span><span class="sxs-lookup"><span data-stu-id="c9b98-137">One-off recipients are typically created with a template for their particular address type.</span></span> <span data-ttu-id="c9b98-138">支持的地址类型通讯簿提供程序提供的模板。</span><span class="sxs-lookup"><span data-stu-id="c9b98-138">The address book provider that supports the address type supplies the template.</span></span> <span data-ttu-id="c9b98-139">客户端应用程序的用户输入到模板相关信息。</span><span class="sxs-lookup"><span data-stu-id="c9b98-139">A user of a client application enters the relevant information into the template.</span></span>
  
<span data-ttu-id="c9b98-140">MAPI 的显示名称、 地址类型和**CreateOneOff**地址参数支持 Unicode 字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="c9b98-140">MAPI supports Unicode character strings for the display name, address type, and address parameters of **CreateOneOff**.</span></span>
  
<span data-ttu-id="c9b98-141">MAPI_SEND_NO_RICH_INFO 标志控制是否以及每封邮件发送带格式的文本中富文本格式 (RTF)。</span><span class="sxs-lookup"><span data-stu-id="c9b98-141">The MAPI_SEND_NO_RICH_INFO flag controls whether formatted text in Rich Text Format (RTF) is sent along with each message.</span></span> <span data-ttu-id="c9b98-142">传输中性封装格式 (TNEF) — 用于传输格式格式化文本 — 发送的大多数传输提供程序，无论收件人将其**PR_SEND_RICH_INFO**属性的设置。</span><span class="sxs-lookup"><span data-stu-id="c9b98-142">The Transport Neutral Encapsulation Format (TNEF) — a format that is used for transmitting formatted text — is sent by most transport providers, regardless of how the recipient sets its **PR_SEND_RICH_INFO** property.</span></span> <span data-ttu-id="c9b98-143">这不是使用人际邮件的客户端消息的问题。</span><span class="sxs-lookup"><span data-stu-id="c9b98-143">This is not an issue for messaging clients that work with interpersonal messages.</span></span> <span data-ttu-id="c9b98-144">但是，因为 TNEF 通常用于发送自定义邮件类的自定义属性，则不支持可以是基于窗体的客户端或客户端需要自定义的 MAPI 属性的问题。</span><span class="sxs-lookup"><span data-stu-id="c9b98-144">However, because TNEF is typically used to send custom properties for custom message classes, not supporting it can be a problem for form-based clients or clients that require custom MAPI properties.</span></span> <span data-ttu-id="c9b98-145">有关详细信息，请参阅[TNEF 发送邮件](sending-messages-with-tnef.md)。</span><span class="sxs-lookup"><span data-stu-id="c9b98-145">For more information, see [Sending Messages with TNEF](sending-messages-with-tnef.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c9b98-146">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="c9b98-146">MFCMAPI reference</span></span>

<span data-ttu-id="c9b98-147">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c9b98-147">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c9b98-148">**文件**</span><span class="sxs-lookup"><span data-stu-id="c9b98-148">**File**</span></span>|<span data-ttu-id="c9b98-149">**函数**</span><span class="sxs-lookup"><span data-stu-id="c9b98-149">**Function**</span></span>|<span data-ttu-id="c9b98-150">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c9b98-150">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9b98-151">Mapiabfunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="c9b98-151">Mapiabfunctions.cpp</span></span>  <br/> |<span data-ttu-id="c9b98-152">AddOneOffAddress</span><span class="sxs-lookup"><span data-stu-id="c9b98-152">AddOneOffAddress</span></span>  <br/> |<span data-ttu-id="c9b98-153">MFCMAPI 使用**CreateOneOff**方法创建的任何通讯簿中找不到的地址条目 ID。</span><span class="sxs-lookup"><span data-stu-id="c9b98-153">MFCMAPI uses the **CreateOneOff** method to create an entry ID for an address that is not found in any address book.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c9b98-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9b98-154">See also</span></span>



[<span data-ttu-id="c9b98-155">IMAPISupport::CreateOneOff</span><span class="sxs-lookup"><span data-stu-id="c9b98-155">IMAPISupport::CreateOneOff</span></span>](imapisupport-createoneoff.md)
  
[<span data-ttu-id="c9b98-156">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c9b98-156">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="c9b98-157">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c9b98-157">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

