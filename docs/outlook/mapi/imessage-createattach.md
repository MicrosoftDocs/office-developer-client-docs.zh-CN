---
title: IMessageCreateAttach
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.IMessage::CreateAttach
api_type:
- COM
ms.assetid: 01711aca-c598-438c-88d7-0719b6691e34
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f534912377aadb3c342030fc02fce26693857476
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417669"
---
# <a name="imessagecreateattach"></a><span data-ttu-id="ddf9e-103">IMessage::CreateAttach</span><span class="sxs-lookup"><span data-stu-id="ddf9e-103">IMessage::CreateAttach</span></span>

  
  
<span data-ttu-id="ddf9e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ddf9e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ddf9e-105">创建新的附件。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-105">Creates a new attachment.</span></span>
  
```cpp
HRESULT CreateAttach(
LPCIID lpInterface,
ULONG ulFlags,
ULONG FAR * lpulAttachmentNum,
LPATTACH FAR * lppAttach
);
```

## <a name="parameters"></a><span data-ttu-id="ddf9e-106">参数</span><span class="sxs-lookup"><span data-stu-id="ddf9e-106">Parameters</span></span>

 <span data-ttu-id="ddf9e-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="ddf9e-107">_lpInterface_</span></span>
  
> <span data-ttu-id="ddf9e-108">[in]指向接口标识符的 (IID) 表示用于访问邮件的接口的 IID 标识符。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-108">[in] Pointer to the interface identifier (IID) representing the interface to be used to access the message.</span></span> <span data-ttu-id="ddf9e-109">传递 NULL 会导致返回邮件的标准接口 **IMessage。**</span><span class="sxs-lookup"><span data-stu-id="ddf9e-109">Passing NULL results in the message's standard interface, or **IMessage**, being returned.</span></span> 
    
 <span data-ttu-id="ddf9e-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ddf9e-110">_ulFlags_</span></span>
  
> <span data-ttu-id="ddf9e-111">[in]控制附件创建方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-111">[in] Bitmask of flags that controls how the attachment is created.</span></span> <span data-ttu-id="ddf9e-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ddf9e-112">The following flag can be set:</span></span>
    
<span data-ttu-id="ddf9e-113">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="ddf9e-113">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="ddf9e-114">允许 **CreateAttach** 在调用客户端完全访问附件之前成功返回。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-114">Allows **CreateAttach** to return successfully, possibly before the attachment is fully accessible to the calling client.</span></span> <span data-ttu-id="ddf9e-115">如果附件不可访问，则对附件进行后续调用可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-115">If the attachment is not accessible, making a subsequent call to it can result in an error.</span></span> 
    
 <span data-ttu-id="ddf9e-116">_lpulAttachmentNum_</span><span class="sxs-lookup"><span data-stu-id="ddf9e-116">_lpulAttachmentNum_</span></span>
  
> <span data-ttu-id="ddf9e-117">[out]指向标识新创建的附件的索引号的指针。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-117">[out] Pointer to an index number identifying the newly created attachment.</span></span> <span data-ttu-id="ddf9e-118">此号码仅在邮件打开时有效，是附件的 PR_ATTACH_NUM ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 的基础。 </span><span class="sxs-lookup"><span data-stu-id="ddf9e-118">This number is valid only when the message is open and is the basis for the attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="ddf9e-119">_lppAttach_</span><span class="sxs-lookup"><span data-stu-id="ddf9e-119">_lppAttach_</span></span>
  
> <span data-ttu-id="ddf9e-120">[out]指向打开的 attachment 对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-120">[out] Pointer to a pointer to the open attachment object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ddf9e-121">返回值</span><span class="sxs-lookup"><span data-stu-id="ddf9e-121">Return value</span></span>

<span data-ttu-id="ddf9e-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="ddf9e-122">S_OK</span></span> 
  
> <span data-ttu-id="ddf9e-123">已成功创建附件。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-123">The attachment was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ddf9e-124">备注</span><span class="sxs-lookup"><span data-stu-id="ddf9e-124">Remarks</span></span>

<span data-ttu-id="ddf9e-125">**IMessage：：CreateAttach** 方法在邮件上创建新附件。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-125">The **IMessage::CreateAttach** method creates a new attachment on a message.</span></span> <span data-ttu-id="ddf9e-126">在客户端同时调用附件的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法和邮件的 **IMAPIProp：：SaveChanges** 方法之前，新附件及其设置的任何属性都不可用。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-126">The new attachment and any properties that are set for it, are not available until a client has called both the attachment's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method and the message's **IMAPIProp::SaveChanges** method.</span></span> 
  
<span data-ttu-id="ddf9e-127">_lpulAttachmentNum_ 指向的附件编号是唯一的，并且仅在邮件上下文中有效。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-127">The attachment number pointed to by  _lpulAttachmentNum_ is unique and valid only within the context of the message.</span></span> <span data-ttu-id="ddf9e-128">也就是说，两个不同邮件中的两个附件可以具有相同的编号，而同一邮件中的两个附件不能相同。</span><span class="sxs-lookup"><span data-stu-id="ddf9e-128">That is, two attachments in two different messages can have the same number while two attachments in the same message cannot.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ddf9e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddf9e-129">See also</span></span>



[<span data-ttu-id="ddf9e-130">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ddf9e-130">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

