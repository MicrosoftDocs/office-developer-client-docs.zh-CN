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
ms.openlocfilehash: 4d38648f5e3084c8342fca8d18f0bd3efc915155
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412630"
---
# <a name="imapifoldercreatemessage"></a><span data-ttu-id="288f2-103">IMAPIFolder::CreateMessage</span><span class="sxs-lookup"><span data-stu-id="288f2-103">IMAPIFolder::CreateMessage</span></span>

  
  
<span data-ttu-id="288f2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="288f2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="288f2-105">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="288f2-105">Creates a new message.</span></span>
  
```cpp
HRESULT CreateMessage(
  LPCIID lpInterface,
  ULONG ulFlags,
  LPMESSAGE FAR * lppMessage
);
```

## <a name="parameters"></a><span data-ttu-id="288f2-106">参数</span><span class="sxs-lookup"><span data-stu-id="288f2-106">Parameters</span></span>

 <span data-ttu-id="288f2-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="288f2-107">_lpInterface_</span></span>
  
> <span data-ttu-id="288f2-108">[in]指向接口标识符的指针 (IID) 表示用于访问新邮件的接口的 IID 标识符。</span><span class="sxs-lookup"><span data-stu-id="288f2-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the new message.</span></span> <span data-ttu-id="288f2-109">有效的接口标识符包括IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer和IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="288f2-109">Valid interface identifiers include IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, and IID_IMAPIFolder.</span></span> <span data-ttu-id="288f2-110">传递 NULL 会导致邮件存储提供程序返回标准消息接口 [IMessage ： IMAPIProp](imessageimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="288f2-110">Passing NULL causes the message store provider to return the standard message interface, [IMessage : IMAPIProp](imessageimapiprop.md).</span></span> 
    
 <span data-ttu-id="288f2-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="288f2-111">_ulFlags_</span></span>
  
> <span data-ttu-id="288f2-112">[in]控制邮件创建方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="288f2-112">[in] A bitmask of flags that controls how the message is created.</span></span> <span data-ttu-id="288f2-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="288f2-113">The following flags can be set:</span></span>
    
<span data-ttu-id="288f2-114">ITEMPROC_FORCE</span><span class="sxs-lookup"><span data-stu-id="288f2-114">ITEMPROC_FORCE</span></span>
  
> <span data-ttu-id="288f2-115">向 PST (个人文件夹存储) 在存储通知任何侦听客户端新邮件到达之前，该邮件符合规则处理条件。</span><span class="sxs-lookup"><span data-stu-id="288f2-115">Indicates to the personal folder store (PST) that the message is eligible for rules processing before the store notifies any listening client of the arrival of the new message.</span></span> <span data-ttu-id="288f2-116">规则处理仅适用于在非规则服务器上创建的新Microsoft Exchange Server，Exchange Server处理服务器上邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="288f2-116">Rules processing only applies to new messages that are created on a server that is not a Microsoft Exchange Server, because Exchange Server processes rules for messages on the server.</span></span> <span data-ttu-id="288f2-117">因此，创建邮件的提供程序或客户端必须使用 NON_EMS_XP_SAVE 将邮件与[IMAPIPProp：：SaveChanges](imapiprop-savechanges.md)一起传递此标志，这表示服务器不是 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="288f2-117">Therefore, the provider or client creating the message must pass this flag in combination with saving a message with [IMAPIPProp::SaveChanges](imapiprop-savechanges.md) using NON_EMS_XP_SAVE, which indicates that the server is not an Exchange Server.</span></span> 
    
<span data-ttu-id="288f2-118">MAPI_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="288f2-118">MAPI_ASSOCIATED</span></span> 
  
> <span data-ttu-id="288f2-119">要创建的消息应包含在关联的内容表中，而不是标准内容表中。</span><span class="sxs-lookup"><span data-stu-id="288f2-119">The message to be created should be included in the associated contents table instead of the standard contents table.</span></span> <span data-ttu-id="288f2-120">关联消息在用户交互中隐藏。</span><span class="sxs-lookup"><span data-stu-id="288f2-120">Associated messages are hidden from user interaction.</span></span>
    
<span data-ttu-id="288f2-121">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="288f2-121">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="288f2-122">即使创建操作尚未完成，也允许 **CreateMessage** 成功。</span><span class="sxs-lookup"><span data-stu-id="288f2-122">**CreateMessage** is allowed to succeed even if the create operation has not fully completed.</span></span> <span data-ttu-id="288f2-123">这意味着新邮件可能不会立即对呼叫者可用。</span><span class="sxs-lookup"><span data-stu-id="288f2-123">This implies that the new message might not be immediately available to the caller.</span></span> 
    
 <span data-ttu-id="288f2-124">_lppMessage_</span><span class="sxs-lookup"><span data-stu-id="288f2-124">_lppMessage_</span></span>
  
> <span data-ttu-id="288f2-125">[out]指向指向新创建的消息的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="288f2-125">[out] A pointer to a pointer to the newly created message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="288f2-126">返回值</span><span class="sxs-lookup"><span data-stu-id="288f2-126">Return value</span></span>

<span data-ttu-id="288f2-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="288f2-127">S_OK</span></span> 
  
> <span data-ttu-id="288f2-128">已成功创建邮件。</span><span class="sxs-lookup"><span data-stu-id="288f2-128">The message was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="288f2-129">备注</span><span class="sxs-lookup"><span data-stu-id="288f2-129">Remarks</span></span>

<span data-ttu-id="288f2-130">**IMAPIFolder：：CreateMessage** 方法创建包含通用或关联内容的新消息，并分配条目标识符。</span><span class="sxs-lookup"><span data-stu-id="288f2-130">The **IMAPIFolder::CreateMessage** method creates a new message with generic or associated content and assigns an entry identifier.</span></span> <span data-ttu-id="288f2-131">条目标识符由一个代表邮件存储提供程序的部件和一个代表单个邮件的部件组成。</span><span class="sxs-lookup"><span data-stu-id="288f2-131">The entry identifier consists of a part that represents the message store provider and a part that represents the individual message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="288f2-132">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="288f2-132">Notes to implementers</span></span>

<span data-ttu-id="288f2-133">您可以选择是设置 **CreateMessage** 中或邮件 [的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法中所需的全部邮件属性。</span><span class="sxs-lookup"><span data-stu-id="288f2-133">You can choose whether to set all of the required message properties in **CreateMessage** or in the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="288f2-134">在成功保存之前，不需要使这些属性可用。</span><span class="sxs-lookup"><span data-stu-id="288f2-134">You do not have to make these properties available until a successful save has occurred.</span></span> 
  
<span data-ttu-id="288f2-135">若要详细了解如何处理相关信息，请参阅[Folder-Associated Information Tables](folder-associated-information-tables.md) and [Contents Tables。](contents-tables.md)</span><span class="sxs-lookup"><span data-stu-id="288f2-135">For more information about how to work with associated information, see [Folder-Associated Information Tables](folder-associated-information-tables.md) and [Contents Tables](contents-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="288f2-136">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="288f2-136">Notes to callers</span></span>

<span data-ttu-id="288f2-137">某些邮件存储提供程序允许在 **CreateMessage** 返回后立即提供新邮件的条目标识符;其他邮件存储提供程序会延迟其可用性，直到邮件保存。</span><span class="sxs-lookup"><span data-stu-id="288f2-137">Some message store providers allow the entry identifier of the new message to be available immediately after **CreateMessage** returns; other message store providers delay its availability until the message is saved.</span></span> <span data-ttu-id="288f2-138">由于在调用邮件的 **IMAPIProp：：SaveChanges** 方法之前，并非所有邮件存储提供程序都会生成新邮件的条目标识符，因此在 **CreateMessage** 返回时，可能无法访问条目标识符。</span><span class="sxs-lookup"><span data-stu-id="288f2-138">Because not all message store providers generate an entry identifier for a new message until you have called the message's **IMAPIProp::SaveChanges** method, you may be unable to access the entry identifier when **CreateMessage** returns.</span></span> <span data-ttu-id="288f2-139">此外，在保存发生之前，新邮件可能不包含在文件夹的内容表中。</span><span class="sxs-lookup"><span data-stu-id="288f2-139">Also, the new message may not be included in the folder's contents table until the save occurs.</span></span> 
  
<span data-ttu-id="288f2-140">预计分配给新邮件的条目标识符不仅在当前邮件存储中是唯一的，而且很可能在所有同时打开的邮件存储中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="288f2-140">Expect the entry identifier assigned to the new message to be unique not only in the current message store, but most likely across all of the message stores that are open at the same time.</span></span> <span data-ttu-id="288f2-141">当配置文件中出现邮件存储的多个条目时，会出现此规则的一个例外。</span><span class="sxs-lookup"><span data-stu-id="288f2-141">One exception to this rule occurs when multiple entries for a message store appear in the profile.</span></span> <span data-ttu-id="288f2-142">这将导致多次打开邮件存储并复制条目标识符。</span><span class="sxs-lookup"><span data-stu-id="288f2-142">This causes the message store to be opened multiple times and entry identifiers to be duplicated.</span></span> 
  
<span data-ttu-id="288f2-143">若要创建传出邮件，请调用发件箱文件夹的 **IMAPIFolder：：CreateMessage** 方法。</span><span class="sxs-lookup"><span data-stu-id="288f2-143">To create an outgoing message, call the Outbox folder's **IMAPIFolder::CreateMessage** method.</span></span> 
  
<span data-ttu-id="288f2-144">如果在保存邮件之前删除包含新邮件的文件夹，则结果未定义。</span><span class="sxs-lookup"><span data-stu-id="288f2-144">If you delete a folder that contains a new message before the message is saved, the results are undefined.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="288f2-145">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="288f2-145">MFCMAPI reference</span></span>

<span data-ttu-id="288f2-146">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="288f2-146">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="288f2-147">**文件**</span><span class="sxs-lookup"><span data-stu-id="288f2-147">**File**</span></span>|<span data-ttu-id="288f2-148">**函数**</span><span class="sxs-lookup"><span data-stu-id="288f2-148">**Function**</span></span>|<span data-ttu-id="288f2-149">**备注**</span><span class="sxs-lookup"><span data-stu-id="288f2-149">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="288f2-150">FolderDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="288f2-150">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="288f2-151">CFolder：：OnNewMessage</span><span class="sxs-lookup"><span data-stu-id="288f2-151">CFolder::OnNewMessage</span></span>  <br/> |<span data-ttu-id="288f2-152">MFCMAPI 使用 **IMAPIFolder：：CreateMessage** 方法创建和保存新邮件。</span><span class="sxs-lookup"><span data-stu-id="288f2-152">MFCMAPI uses the **IMAPIFolder::CreateMessage** method to create and save a new message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="288f2-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="288f2-153">See also</span></span>



[<span data-ttu-id="288f2-154">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="288f2-154">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="288f2-155">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="288f2-155">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="288f2-156">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="288f2-156">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

