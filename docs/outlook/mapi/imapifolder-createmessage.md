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
# <a name="imapifoldercreatemessage"></a><span data-ttu-id="933f4-103">IMAPIFolder::CreateMessage</span><span class="sxs-lookup"><span data-stu-id="933f4-103">IMAPIFolder::CreateMessage</span></span>

  
  
<span data-ttu-id="933f4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="933f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="933f4-105">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="933f4-105">Creates a new message.</span></span>
  
```cpp
HRESULT CreateMessage(
  LPCIID lpInterface,
  ULONG ulFlags,
  LPMESSAGE FAR * lppMessage
);
```

## <a name="parameters"></a><span data-ttu-id="933f4-106">参数</span><span class="sxs-lookup"><span data-stu-id="933f4-106">Parameters</span></span>

 <span data-ttu-id="933f4-107">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="933f4-107">_lpInterface_</span></span>
  
> <span data-ttu-id="933f4-108">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问新邮件的接口。</span><span class="sxs-lookup"><span data-stu-id="933f4-108">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the new message.</span></span> <span data-ttu-id="933f4-109">有效的接口标识符包括 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 和 IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="933f4-109">Valid interface identifiers include IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, and IID_IMAPIFolder.</span></span> <span data-ttu-id="933f4-110">传递 NULL 将导致邮件存储区提供程序返回标准的邮件接口[IMessage: IMAPIProp](imessageimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="933f4-110">Passing NULL causes the message store provider to return the standard message interface, [IMessage : IMAPIProp](imessageimapiprop.md).</span></span> 
    
 <span data-ttu-id="933f4-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="933f4-111">_ulFlags_</span></span>
  
> <span data-ttu-id="933f4-112">实时用于控制如何创建邮件的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="933f4-112">[in] A bitmask of flags that controls how the message is created.</span></span> <span data-ttu-id="933f4-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="933f4-113">The following flags can be set:</span></span>
    
<span data-ttu-id="933f4-114">ITEMPROC_FORCE</span><span class="sxs-lookup"><span data-stu-id="933f4-114">ITEMPROC_FORCE</span></span>
  
> <span data-ttu-id="933f4-115">向个人文件夹存储 (PST) 表明, 在存储通知任何侦听客户端的新邮件到达之前, 该邮件符合规则的处理条件。</span><span class="sxs-lookup"><span data-stu-id="933f4-115">Indicates to the personal folder store (PST) that the message is eligible for rules processing before the store notifies any listening client of the arrival of the new message.</span></span> <span data-ttu-id="933f4-116">规则处理仅适用于在不是 Microsoft Exchange server 的服务器上创建的新邮件, 因为 Exchange server 会在服务器上处理邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="933f4-116">Rules processing only applies to new messages that are created on a server that is not a Microsoft Exchange Server, because Exchange Server processes rules for messages on the server.</span></span> <span data-ttu-id="933f4-117">因此, 创建邮件的提供程序或客户端必须结合使用[IMAPIPProp:: SaveChanges](imapiprop-savechanges.md) using NON_EMS_XP_SAVE (指示服务器不是 Exchange 服务器) 中的另一封邮件传递此标志。</span><span class="sxs-lookup"><span data-stu-id="933f4-117">Therefore, the provider or client creating the message must pass this flag in combination with saving a message with [IMAPIPProp::SaveChanges](imapiprop-savechanges.md) using NON_EMS_XP_SAVE, which indicates that the server is not an Exchange Server.</span></span> 
    
<span data-ttu-id="933f4-118">MAPI_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="933f4-118">MAPI_ASSOCIATED</span></span> 
  
> <span data-ttu-id="933f4-119">要创建的邮件应包含在 "关联的内容" 表中, 而不是 "标准内容" 表中。</span><span class="sxs-lookup"><span data-stu-id="933f4-119">The message to be created should be included in the associated contents table instead of the standard contents table.</span></span> <span data-ttu-id="933f4-120">将隐藏用户交互中的关联邮件。</span><span class="sxs-lookup"><span data-stu-id="933f4-120">Associated messages are hidden from user interaction.</span></span>
    
<span data-ttu-id="933f4-121">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="933f4-121">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="933f4-122">即使创建操作尚未完全完成, 也允许**CreateMessage**成功。</span><span class="sxs-lookup"><span data-stu-id="933f4-122">**CreateMessage** is allowed to succeed even if the create operation has not fully completed.</span></span> <span data-ttu-id="933f4-123">这意味着可能无法立即向呼叫者提供新邮件。</span><span class="sxs-lookup"><span data-stu-id="933f4-123">This implies that the new message might not be immediately available to the caller.</span></span> 
    
 <span data-ttu-id="933f4-124">_lppMessage_</span><span class="sxs-lookup"><span data-stu-id="933f4-124">_lppMessage_</span></span>
  
> <span data-ttu-id="933f4-125">排除指向新创建的邮件的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="933f4-125">[out] A pointer to a pointer to the newly created message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="933f4-126">返回值</span><span class="sxs-lookup"><span data-stu-id="933f4-126">Return value</span></span>

<span data-ttu-id="933f4-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="933f4-127">S_OK</span></span> 
  
> <span data-ttu-id="933f4-128">邮件已成功创建。</span><span class="sxs-lookup"><span data-stu-id="933f4-128">The message was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="933f4-129">说明</span><span class="sxs-lookup"><span data-stu-id="933f4-129">Remarks</span></span>

<span data-ttu-id="933f4-130">**IMAPIFolder:: CreateMessage**方法创建一个包含常规或关联内容的新邮件, 并分配一个条目标识符。</span><span class="sxs-lookup"><span data-stu-id="933f4-130">The **IMAPIFolder::CreateMessage** method creates a new message with generic or associated content and assigns an entry identifier.</span></span> <span data-ttu-id="933f4-131">条目标识符由表示邮件存储提供程序的部件和表示单个邮件的部件组成。</span><span class="sxs-lookup"><span data-stu-id="933f4-131">The entry identifier consists of a part that represents the message store provider and a part that represents the individual message.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="933f4-132">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="933f4-132">Notes to implementers</span></span>

<span data-ttu-id="933f4-133">您可以选择是在**CreateMessage**中还是在邮件的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法中设置所有必需的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="933f4-133">You can choose whether to set all of the required message properties in **CreateMessage** or in the message's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="933f4-134">只有在成功保存之后, 才必须使这些属性可用。</span><span class="sxs-lookup"><span data-stu-id="933f4-134">You do not have to make these properties available until a successful save has occurred.</span></span> 
  
<span data-ttu-id="933f4-135">有关如何使用关联信息的详细信息, 请参阅与[文件夹相关的信息表](folder-associated-information-tables.md)和[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="933f4-135">For more information about how to work with associated information, see [Folder-Associated Information Tables](folder-associated-information-tables.md) and [Contents Tables](contents-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="933f4-136">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="933f4-136">Notes to callers</span></span>

<span data-ttu-id="933f4-137">某些邮件存储提供程序允许新邮件的条目标识符在**CreateMessage**返回后立即可用。在保存邮件之前, 其他邮件存储提供程序会延迟其可用性。</span><span class="sxs-lookup"><span data-stu-id="933f4-137">Some message store providers allow the entry identifier of the new message to be available immediately after **CreateMessage** returns; other message store providers delay its availability until the message is saved.</span></span> <span data-ttu-id="933f4-138">由于并非所有邮件存储提供程序都会为新邮件生成条目标识符, 直到您调用邮件的**IMAPIProp:: SaveChanges**方法之后, 您可能无法在**CreateMessage**返回时访问条目标识符。</span><span class="sxs-lookup"><span data-stu-id="933f4-138">Because not all message store providers generate an entry identifier for a new message until you have called the message's **IMAPIProp::SaveChanges** method, you may be unable to access the entry identifier when **CreateMessage** returns.</span></span> <span data-ttu-id="933f4-139">此外, 在保存过程中, 新邮件可能不会包含在文件夹的内容表中。</span><span class="sxs-lookup"><span data-stu-id="933f4-139">Also, the new message may not be included in the folder's contents table until the save occurs.</span></span> 
  
<span data-ttu-id="933f4-140">预计分配给新邮件的条目标识符不仅在当前邮件存储中是唯一的, 而且很可能跨所有同时打开的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="933f4-140">Expect the entry identifier assigned to the new message to be unique not only in the current message store, but most likely across all of the message stores that are open at the same time.</span></span> <span data-ttu-id="933f4-141">当邮件存储区中的多个条目出现在配置文件中时, 将发生此规则的一个例外。</span><span class="sxs-lookup"><span data-stu-id="933f4-141">One exception to this rule occurs when multiple entries for a message store appear in the profile.</span></span> <span data-ttu-id="933f4-142">这会导致邮件存储区多次打开, 并且条目标识符将被复制。</span><span class="sxs-lookup"><span data-stu-id="933f4-142">This causes the message store to be opened multiple times and entry identifiers to be duplicated.</span></span> 
  
<span data-ttu-id="933f4-143">若要创建传出邮件, 请调用 "发件箱" 文件夹的**IMAPIFolder:: CreateMessage**方法。</span><span class="sxs-lookup"><span data-stu-id="933f4-143">To create an outgoing message, call the Outbox folder's **IMAPIFolder::CreateMessage** method.</span></span> 
  
<span data-ttu-id="933f4-144">如果在保存邮件之前删除了包含新邮件的文件夹, 则结果是不确定的。</span><span class="sxs-lookup"><span data-stu-id="933f4-144">If you delete a folder that contains a new message before the message is saved, the results are undefined.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="933f4-145">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="933f4-145">MFCMAPI reference</span></span>

<span data-ttu-id="933f4-146">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="933f4-146">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="933f4-147">**文件**</span><span class="sxs-lookup"><span data-stu-id="933f4-147">**File**</span></span>|<span data-ttu-id="933f4-148">**函数**</span><span class="sxs-lookup"><span data-stu-id="933f4-148">**Function**</span></span>|<span data-ttu-id="933f4-149">**备注**</span><span class="sxs-lookup"><span data-stu-id="933f4-149">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="933f4-150">FolderDlg</span><span class="sxs-lookup"><span data-stu-id="933f4-150">FolderDlg.cpp</span></span>  <br/> |<span data-ttu-id="933f4-151">CFolder:: OnNewMessage</span><span class="sxs-lookup"><span data-stu-id="933f4-151">CFolder::OnNewMessage</span></span>  <br/> |<span data-ttu-id="933f4-152">MFCMAPI 使用**IMAPIFolder:: CreateMessage**方法创建并保存新邮件。</span><span class="sxs-lookup"><span data-stu-id="933f4-152">MFCMAPI uses the **IMAPIFolder::CreateMessage** method to create and save a new message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="933f4-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="933f4-153">See also</span></span>



[<span data-ttu-id="933f4-154">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="933f4-154">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="933f4-155">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="933f4-155">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="933f4-156">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="933f4-156">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

