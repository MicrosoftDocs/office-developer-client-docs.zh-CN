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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9cc2f5f3880466c0a70febedbc7aaec987b62bb3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572082"
---
# <a name="imessagecreateattach"></a><span data-ttu-id="1c47b-103">IMessage::CreateAttach</span><span class="sxs-lookup"><span data-stu-id="1c47b-103">IMessage::CreateAttach</span></span>

  
  
<span data-ttu-id="1c47b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1c47b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1c47b-105">创建一个新附件。</span><span class="sxs-lookup"><span data-stu-id="1c47b-105">Creates a new attachment.</span></span>
  
```cpp
HRESULT CreateAttach(
LPCIID lpInterface,
ULONG ulFlags,
ULONG FAR * lpulAttachmentNum,
LPATTACH FAR * lppAttach
);
```

## <a name="parameters"></a><span data-ttu-id="1c47b-106">参数</span><span class="sxs-lookup"><span data-stu-id="1c47b-106">Parameters</span></span>

 <span data-ttu-id="1c47b-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="1c47b-107">_lpInterface_</span></span>
  
> <span data-ttu-id="1c47b-108">[in]表示要用于访问邮件的接口的界面标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="1c47b-108">[in] Pointer to the interface identifier (IID) representing the interface to be used to access the message.</span></span> <span data-ttu-id="1c47b-109">传递 NULL 将导致消息的标准界面或**IMessage**，返回。</span><span class="sxs-lookup"><span data-stu-id="1c47b-109">Passing NULL results in the message's standard interface, or **IMessage**, being returned.</span></span> 
    
 <span data-ttu-id="1c47b-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1c47b-110">_ulFlags_</span></span>
  
> <span data-ttu-id="1c47b-111">[in]位掩码的标志，控制如何创建附件。</span><span class="sxs-lookup"><span data-stu-id="1c47b-111">[in] Bitmask of flags that controls how the attachment is created.</span></span> <span data-ttu-id="1c47b-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="1c47b-112">The following flag can be set:</span></span>
    
<span data-ttu-id="1c47b-113">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="1c47b-113">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="1c47b-114">允许**CreateAttach**返回成功，可能之前附件是完全可调用客户端。</span><span class="sxs-lookup"><span data-stu-id="1c47b-114">Allows **CreateAttach** to return successfully, possibly before the attachment is fully accessible to the calling client.</span></span> <span data-ttu-id="1c47b-115">如果附件不可访问，则进行后续呼叫到它会导致错误。</span><span class="sxs-lookup"><span data-stu-id="1c47b-115">If the attachment is not accessible, making a subsequent call to it can result in an error.</span></span> 
    
 <span data-ttu-id="1c47b-116">_lpulAttachmentNum_</span><span class="sxs-lookup"><span data-stu-id="1c47b-116">_lpulAttachmentNum_</span></span>
  
> <span data-ttu-id="1c47b-117">[输出]指向标识新创建的附件的索引号。</span><span class="sxs-lookup"><span data-stu-id="1c47b-117">[out] Pointer to an index number identifying the newly created attachment.</span></span> <span data-ttu-id="1c47b-118">仅当邮件处于打开状态，并且基础的附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性时，此数字是有效。</span><span class="sxs-lookup"><span data-stu-id="1c47b-118">This number is valid only when the message is open and is the basis for the attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="1c47b-119">_lppAttach_</span><span class="sxs-lookup"><span data-stu-id="1c47b-119">_lppAttach_</span></span>
  
> <span data-ttu-id="1c47b-120">[输出]指向打开附件对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1c47b-120">[out] Pointer to a pointer to the open attachment object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1c47b-121">返回值</span><span class="sxs-lookup"><span data-stu-id="1c47b-121">Return value</span></span>

<span data-ttu-id="1c47b-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c47b-122">S_OK</span></span> 
  
> <span data-ttu-id="1c47b-123">附件已成功创建。</span><span class="sxs-lookup"><span data-stu-id="1c47b-123">The attachment was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1c47b-124">注解</span><span class="sxs-lookup"><span data-stu-id="1c47b-124">Remarks</span></span>

<span data-ttu-id="1c47b-125">**IMessage::CreateAttach**方法创建一个新附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="1c47b-125">The **IMessage::CreateAttach** method creates a new attachment on a message.</span></span> <span data-ttu-id="1c47b-126">客户端具有调用附件的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法和消息的**IMAPIProp::SaveChanges**方法之前，新的附件和该设置的任何属性不可用。</span><span class="sxs-lookup"><span data-stu-id="1c47b-126">The new attachment and any properties that are set for it, are not available until a client has called both the attachment's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method and the message's **IMAPIProp::SaveChanges** method.</span></span> 
  
<span data-ttu-id="1c47b-127">指向_lpulAttachmentNum_的附件数是唯一的并且只在邮件的上下文中有效。</span><span class="sxs-lookup"><span data-stu-id="1c47b-127">The attachment number pointed to by  _lpulAttachmentNum_ is unique and valid only within the context of the message.</span></span> <span data-ttu-id="1c47b-128">即两个不同的邮件中的两个附件可以具有相同数量，而不能在同一消息中的两个附件。</span><span class="sxs-lookup"><span data-stu-id="1c47b-128">That is, two attachments in two different messages can have the same number while two attachments in the same message cannot.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1c47b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c47b-129">See also</span></span>



[<span data-ttu-id="1c47b-130">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="1c47b-130">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

