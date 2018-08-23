---
title: IMAPIFolderCreateMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CreateMessage
api_type:
- COM
ms.assetid: e0222afa-c148-4735-a603-cac7be6c91f9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e740e86fc25307457119aabf6e2aa0c42a9d69b9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568222"
---
# <a name="imapifoldercreatemessage"></a><span data-ttu-id="1f319-103">IMAPIFolder::CreateMessage</span><span class="sxs-lookup"><span data-stu-id="1f319-103">IMAPIFolder::CreateMessage</span></span>

  
  
<span data-ttu-id="1f319-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f319-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f319-105">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="1f319-105">Creates a new message.</span></span>
  
```cpp
HRESULT CreateMessage(
  LPCIID lpInterface,
  ULONG ulFlags,
  LPMESSAGE FAR * lppMessage
);
```

## <a name="parameters"></a><span data-ttu-id="1f319-106">参数</span><span class="sxs-lookup"><span data-stu-id="1f319-106">Parameters</span></span>

 <span data-ttu-id="1f319-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="1f319-107">_lpInterface_</span></span>
  
> <span data-ttu-id="1f319-108">[in]指向接口标识 (IID) 值，该值代表要用于访问新邮件的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1f319-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the new message.</span></span> <span data-ttu-id="1f319-109">有效的接口标识符包括 IID_IUnknown、 IID_IMAPIProp、 IID_IMAPIContainer 和 IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="1f319-109">Valid interface identifiers include IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, and IID_IMAPIFolder.</span></span> <span data-ttu-id="1f319-110">传递 NULL 将导致消息存储提供程序返回的标准消息接口， [IMessage: IMAPIProp](imessageimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="1f319-110">Passing NULL causes the message store provider to return the standard message interface, [IMessage : IMAPIProp](imessageimapiprop.md).</span></span> 
    
 <span data-ttu-id="1f319-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1f319-111">_ulFlags_</span></span>
  
> <span data-ttu-id="1f319-112">[in]位掩码的标志，控制如何创建消息。</span><span class="sxs-lookup"><span data-stu-id="1f319-112">[in] A bitmask of flags that controls how the message is created.</span></span> <span data-ttu-id="1f319-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="1f319-113">The following flags can be set:</span></span>
    
<span data-ttu-id="1f319-114">ITEMPROC_FORCE</span><span class="sxs-lookup"><span data-stu-id="1f319-114">ITEMPROC_FORCE</span></span>
  
> <span data-ttu-id="1f319-115">指示到个人文件夹存储区 (PST) 邮件是否符合规则处理之前存储通知新消息的到达任何侦听客户端。</span><span class="sxs-lookup"><span data-stu-id="1f319-115">Indicates to the personal folder store (PST) that the message is eligible for rules processing before the store notifies any listening client of the arrival of the new message.</span></span> <span data-ttu-id="1f319-116">规则仅处理适用于 Exchange Server 处理服务器上的邮件的规则，因为不是 Microsoft Exchange Server，服务器创建的新邮件。</span><span class="sxs-lookup"><span data-stu-id="1f319-116">Rules processing only applies to new messages that are created on a server that is not a Microsoft Exchange Server, because Exchange Server processes rules for messages on the server.</span></span> <span data-ttu-id="1f319-117">因此，提供程序或创建邮件客户端必须通过此标志结合使用[IMAPIPProp::SaveChanges](imapiprop-savechanges.md)保存一条消息，使用 NON_EMS_XP_SAVE，这表明服务器不是 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="1f319-117">Therefore, the provider or client creating the message must pass this flag in combination with saving a message with [IMAPIPProp::SaveChanges](imapiprop-savechanges.md) using NON_EMS_XP_SAVE, which indicates that the server is not an Exchange Server.</span></span> 
    
<span data-ttu-id="1f319-118">MAPI_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="1f319-118">MAPI_ASSOCIATED</span></span> 
  
> <span data-ttu-id="1f319-119">应关联的内容表而不是标准内容表中包含要创建的消息。</span><span class="sxs-lookup"><span data-stu-id="1f319-119">The message to be created should be included in the associated contents table instead of the standard contents table.</span></span> <span data-ttu-id="1f319-120">从用户交互将隐藏相关联的消息。</span><span class="sxs-lookup"><span data-stu-id="1f319-120">Associated messages are hidden from user interaction.</span></span>
    
<span data-ttu-id="1f319-121">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="1f319-121">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="1f319-122">允许**CreateMessage**即使未全部完成创建操作已成功。</span><span class="sxs-lookup"><span data-stu-id="1f319-122">**CreateMessage** is allowed to succeed even if the create operation has not fully completed.</span></span> <span data-ttu-id="1f319-123">这意味着新邮件可能不会与呼叫者立即可用。</span><span class="sxs-lookup"><span data-stu-id="1f319-123">This implies that the new message might not be immediately available to the caller.</span></span> 
    
 <span data-ttu-id="1f319-124">_lppMessage_</span><span class="sxs-lookup"><span data-stu-id="1f319-124">_lppMessage_</span></span>
  
> <span data-ttu-id="1f319-125">[输出]指向新创建的消息的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1f319-125">[out] A pointer to a pointer to the newly created message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1f319-126">返回值</span><span class="sxs-lookup"><span data-stu-id="1f319-126">Return value</span></span>

<span data-ttu-id="1f319-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f319-127">S_OK</span></span> 
  
> <span data-ttu-id="1f319-128">邮件已成功创建。</span><span class="sxs-lookup"><span data-stu-id="1f319-128">The message was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1f319-129">注解</span><span class="sxs-lookup"><span data-stu-id="1f319-129">Remarks</span></span>

<span data-ttu-id="1f319-130">**IMAPIFolder::CreateMessage**方法使用泛型或关联的内容创建一个新的邮件和分配条目标识符。</span><span class="sxs-lookup"><span data-stu-id="1f319-130">The **IMAPIFolder::CreateMessage** method creates a new message with generic or associated content and assigns an entry identifier.</span></span> <span data-ttu-id="1f319-131">项标识符由部件的表示的消息存储提供程序和代表单个邮件的部件组成。</span><span class="sxs-lookup"><span data-stu-id="1f319-131">The entry identifier consists of a part that represents the message store provider and a part that represents the individual message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="1f319-132">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="1f319-132">Notes to implementers</span></span>

<span data-ttu-id="1f319-133">您可以选择是否在**CreateMessage**或消息的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法设置的所有必需的消息属性。</span><span class="sxs-lookup"><span data-stu-id="1f319-133">You can choose whether to set all of the required message properties in **CreateMessage** or in the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="1f319-134">您不必公开这些属性，直到成功保存发生。</span><span class="sxs-lookup"><span data-stu-id="1f319-134">You do not have to make these properties available until a successful save has occurred.</span></span> 
  
<span data-ttu-id="1f319-135">有关如何使用相关的信息，请参阅[Folder-Associated 信息表](folder-associated-information-tables.md)和[内容表](contents-tables.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1f319-135">For more information about how to work with associated information, see [Folder-Associated Information Tables](folder-associated-information-tables.md) and [Contents Tables](contents-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1f319-136">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1f319-136">Notes to callers</span></span>

<span data-ttu-id="1f319-137">某些消息存储提供程序允许可返回**CreateMessage** ; 后立即的新邮件的项标识符其他消息存储提供程序直到保存邮件延迟其可用性。</span><span class="sxs-lookup"><span data-stu-id="1f319-137">Some message store providers allow the entry identifier of the new message to be available immediately after **CreateMessage** returns; other message store providers delay its availability until the message is saved.</span></span> <span data-ttu-id="1f319-138">并非所有的消息存储提供程序直到以前呼叫过该消息的**IMAPIProp::SaveChanges**方法生成一个新的邮件的项标识符，因为您可能无法访问**CreateMessage**返回的项标识符。</span><span class="sxs-lookup"><span data-stu-id="1f319-138">Because not all message store providers generate an entry identifier for a new message until you have called the message's **IMAPIProp::SaveChanges** method, you may be unable to access the entry identifier when **CreateMessage** returns.</span></span> <span data-ttu-id="1f319-139">此外，新邮件可能不会包含该文件夹的内容表中之前保存，发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1f319-139">Also, the new message may not be included in the folder's contents table until the save occurs.</span></span> 
  
<span data-ttu-id="1f319-140">预期分配给该新消息的消息存储库同时打开的所有成为唯一而不是只在当前消息存储库，但最可能的项标识符。</span><span class="sxs-lookup"><span data-stu-id="1f319-140">Expect the entry identifier assigned to the new message to be unique not only in the current message store, but most likely across all of the message stores that are open at the same time.</span></span> <span data-ttu-id="1f319-141">配置文件中出现的消息存储库的多个条目时发生此规则的一个例外。</span><span class="sxs-lookup"><span data-stu-id="1f319-141">One exception to this rule occurs when multiple entries for a message store appear in the profile.</span></span> <span data-ttu-id="1f319-142">这会导致要打开多次消息存储和要重复的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="1f319-142">This causes the message store to be opened multiple times and entry identifiers to be duplicated.</span></span> 
  
<span data-ttu-id="1f319-143">若要创建传出邮件，请调用发件箱文件夹的**IMAPIFolder::CreateMessage**方法。</span><span class="sxs-lookup"><span data-stu-id="1f319-143">To create an outgoing message, call the Outbox folder's **IMAPIFolder::CreateMessage** method.</span></span> 
  
<span data-ttu-id="1f319-144">如果您删除之前保存邮件包含一封新邮件的文件夹，则结果是未定义。</span><span class="sxs-lookup"><span data-stu-id="1f319-144">If you delete a folder that contains a new message before the message is saved, the results are undefined.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1f319-145">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1f319-145">MFCMAPI reference</span></span>

<span data-ttu-id="1f319-146">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1f319-146">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1f319-147">**文件**</span><span class="sxs-lookup"><span data-stu-id="1f319-147">**File**</span></span>|<span data-ttu-id="1f319-148">**函数**</span><span class="sxs-lookup"><span data-stu-id="1f319-148">**Function**</span></span>|<span data-ttu-id="1f319-149">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1f319-149">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f319-150">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="1f319-150">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="1f319-151">CFolder::OnNewMessage</span><span class="sxs-lookup"><span data-stu-id="1f319-151">CFolder::OnNewMessage</span></span>  <br/> |<span data-ttu-id="1f319-152">MFCMAPI 使用**IMAPIFolder::CreateMessage**方法创建和保存新邮件。</span><span class="sxs-lookup"><span data-stu-id="1f319-152">MFCMAPI uses the **IMAPIFolder::CreateMessage** method to create and save a new message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1f319-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f319-153">See also</span></span>



[<span data-ttu-id="1f319-154">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="1f319-154">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="1f319-155">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="1f319-155">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="1f319-156">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1f319-156">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

