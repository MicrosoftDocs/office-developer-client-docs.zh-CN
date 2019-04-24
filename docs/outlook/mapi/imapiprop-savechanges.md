---
title: IMAPIPropSaveChanges
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.SaveChanges
api_type:
- COM
ms.assetid: 864dbc3e-2039-435a-a279-385d79d1d13f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2c8244180a5cafedc887fa72f36f233fb5084f79
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316630"
---
# <a name="imapipropsavechanges"></a><span data-ttu-id="288e5-103">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="288e5-103">IMAPIProp::SaveChanges</span></span>

  
  
<span data-ttu-id="288e5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="288e5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="288e5-105">使自上次保存操作后对对象进行的任何更改成为永久性的。</span><span class="sxs-lookup"><span data-stu-id="288e5-105">Makes permanent any changes that were made to an object since the last save operation.</span></span> 
  
```cpp
HRESULT SaveChanges(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="288e5-106">参数</span><span class="sxs-lookup"><span data-stu-id="288e5-106">Parameters</span></span>

 <span data-ttu-id="288e5-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="288e5-107">_ulFlags_</span></span>
  
> <span data-ttu-id="288e5-108">实时标志的位掩码, 用于控制在调用**IMAPIProp:: SaveChanges**方法时对对象所发生的操作。</span><span class="sxs-lookup"><span data-stu-id="288e5-108">[in] A bitmask of flags that controls what happens to the object when the **IMAPIProp::SaveChanges** method is called.</span></span> <span data-ttu-id="288e5-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="288e5-109">The following flags can be set:</span></span> 
    
<span data-ttu-id="288e5-110">NON_EMS_XP_SAVE</span><span class="sxs-lookup"><span data-stu-id="288e5-110">NON_EMS_XP_SAVE</span></span>
  
> <span data-ttu-id="288e5-111">指示邮件尚未从 Microsoft Exchange Server 传递。</span><span class="sxs-lookup"><span data-stu-id="288e5-111">Indicates that the message has not been delivered from a Microsoft Exchange Server.</span></span> <span data-ttu-id="288e5-112">应将此标志与[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法和 ITEMPROC_FORCE 标志结合使用, 以向 PST 存储中指明邮件是否符合规则处理规则, 然后再将个人文件夹文件 (PST) 存储通知任何侦听客户端邮件已到达。</span><span class="sxs-lookup"><span data-stu-id="288e5-112">This flag should be used in combination with the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method and the ITEMPROC_FORCE flag to indicate to a PST store that the message is eligible for rules processing before the Personal Folders file (PST) store notifies any listening client that the message has arrived.</span></span> <span data-ttu-id="288e5-113">此规则处理仅适用于在不是 Exchange 服务器的服务器上使用[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)创建的新邮件, 在这种情况下, Exchange server 可能已经处理了邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="288e5-113">This rules processing only applies to new messages that are created with [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) on a server that is not an Exchange Server, in which case the Exchange Server would have already processed rules on the message.</span></span> 
    
<span data-ttu-id="288e5-114">FORCE_SAVE</span><span class="sxs-lookup"><span data-stu-id="288e5-114">FORCE_SAVE</span></span> 
  
> <span data-ttu-id="288e5-115">应将更改写入对象, 覆盖对对象所做的任何以前的更改, 并且应关闭该对象。</span><span class="sxs-lookup"><span data-stu-id="288e5-115">Changes should be written to the object, overriding any previous changes that were made to the object, and the object should be closed.</span></span> <span data-ttu-id="288e5-116">必须设置读/写权限, 才能成功执行此操作。</span><span class="sxs-lookup"><span data-stu-id="288e5-116">Read/write permission must be set for the operation to succeed.</span></span> <span data-ttu-id="288e5-117">在对**SaveChanges**返回的上一次调用后使用 FORCE_SAVE 标志 MAPI_E_OBJECT_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="288e5-117">The FORCE_SAVE flag is used after a previous call to **SaveChanges** returned MAPI_E_OBJECT_CHANGED.</span></span> 
    
<span data-ttu-id="288e5-118">KEEP_OPEN_READONLY</span><span class="sxs-lookup"><span data-stu-id="288e5-118">KEEP_OPEN_READONLY</span></span> 
  
> <span data-ttu-id="288e5-119">应提交更改, 并将对象保持打开状态以供阅读。</span><span class="sxs-lookup"><span data-stu-id="288e5-119">Changes should be committed and the object should be kept open for reading.</span></span> <span data-ttu-id="288e5-120">不会进行其他更改。</span><span class="sxs-lookup"><span data-stu-id="288e5-120">No additional changes will be made.</span></span> 
    
<span data-ttu-id="288e5-121">KEEP_OPEN_READWRITE</span><span class="sxs-lookup"><span data-stu-id="288e5-121">KEEP_OPEN_READWRITE</span></span> 
  
> <span data-ttu-id="288e5-122">应提交更改, 应将该对象保持打开状态以进行读/写权限。</span><span class="sxs-lookup"><span data-stu-id="288e5-122">Changes should be committed and the object should be kept open for read/write permission.</span></span> <span data-ttu-id="288e5-123">在首次打开对象以进行读/写权限时, 通常会设置此标志。</span><span class="sxs-lookup"><span data-stu-id="288e5-123">This flag is usually set when the object was first opened for read/write permission.</span></span> <span data-ttu-id="288e5-124">允许对该对象进行后续更改。</span><span class="sxs-lookup"><span data-stu-id="288e5-124">Subsequent changes to the object are allowed.</span></span> 
    
<span data-ttu-id="288e5-125">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="288e5-125">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="288e5-126">允许**SaveChanges**成功返回, 可能在更改完全提交之前。</span><span class="sxs-lookup"><span data-stu-id="288e5-126">Allows **SaveChanges** to return successfully, possibly before the changes have been fully committed.</span></span> 
    
<span data-ttu-id="288e5-127">SPAMFILTER_ONSAVE</span><span class="sxs-lookup"><span data-stu-id="288e5-127">SPAMFILTER_ONSAVE</span></span>
  
> <span data-ttu-id="288e5-128">对要保存的邮件启用垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="288e5-128">Enables spam filtering on a message that is being saved.</span></span> <span data-ttu-id="288e5-129">垃圾邮件筛选支持只有在发件人的电子邮件地址类型为简单邮件传输协议 (SMTP) 且正在将邮件保存到个人文件夹文件 (PST) 存储区的情况下可用。</span><span class="sxs-lookup"><span data-stu-id="288e5-129">Spam filtering support is available only if the sender's email address type is Simple Mail Transfer Protocol (SMTP), and the message is being saved to a store for a Personal Folders file (PST).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="288e5-130">返回值</span><span class="sxs-lookup"><span data-stu-id="288e5-130">Return value</span></span>

<span data-ttu-id="288e5-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="288e5-131">S_OK</span></span> 
  
> <span data-ttu-id="288e5-132">更改的承诺已成功完成。</span><span class="sxs-lookup"><span data-stu-id="288e5-132">The commitment of changes was successful.</span></span>
    
<span data-ttu-id="288e5-133">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="288e5-133">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="288e5-134">如果设置了 KEEP_OPEN_READONLY, 则**SaveChanges**无法保持打开对象以进行只读权限, 如果设置了 KEEP_OPEN_READWRITE, 则不能读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="288e5-134">**SaveChanges** cannot keep the object open for read-only permission if KEEP_OPEN_READONLY is set, or read/write permission if KEEP_OPEN_READWRITE is set.</span></span> <span data-ttu-id="288e5-135">不提交任何更改。</span><span class="sxs-lookup"><span data-stu-id="288e5-135">No changes are committed.</span></span> 
    
<span data-ttu-id="288e5-136">MAPI_E_OBJECT_CHANGED</span><span class="sxs-lookup"><span data-stu-id="288e5-136">MAPI_E_OBJECT_CHANGED</span></span> 
  
> <span data-ttu-id="288e5-137">对象在打开后已更改。</span><span class="sxs-lookup"><span data-stu-id="288e5-137">The object has changed since it was opened.</span></span>
    
<span data-ttu-id="288e5-138">MAPI_E_OBJECT_DELETED</span><span class="sxs-lookup"><span data-stu-id="288e5-138">MAPI_E_OBJECT_DELETED</span></span> 
  
> <span data-ttu-id="288e5-139">对象已被删除, 因为它已被打开。</span><span class="sxs-lookup"><span data-stu-id="288e5-139">The object has been deleted since it was opened.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="288e5-140">注解</span><span class="sxs-lookup"><span data-stu-id="288e5-140">Remarks</span></span>

<span data-ttu-id="288e5-141">对于支持处理的事务模型的对象, **IMAPIProp:: SaveChanges**方法会永久更改属性, 例如邮件、附件、通讯簿容器和邮件用户对象。</span><span class="sxs-lookup"><span data-stu-id="288e5-141">The **IMAPIProp::SaveChanges** method makes property changes permanent for objects that support the transaction model of processing, such as messages, attachments, address book containers, and messaging user objects.</span></span> <span data-ttu-id="288e5-142">不支持事务的对象 (如文件夹、邮件存储区和配置文件节) 会立即永久更改。</span><span class="sxs-lookup"><span data-stu-id="288e5-142">Objects that do not support transactions, such as folders, message stores, and profile sections, make changes permanent immediately.</span></span> <span data-ttu-id="288e5-143">不需要对**SaveChanges**的调用。</span><span class="sxs-lookup"><span data-stu-id="288e5-143">No call to **SaveChanges** is required.</span></span> 
  
<span data-ttu-id="288e5-144">由于在保存所有属性之前, 服务提供程序不一定要为其对象生成条目标识符, 因此对象的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性在其**SaveChanges**方法后面可能不可用已调用。</span><span class="sxs-lookup"><span data-stu-id="288e5-144">Because service providers do not have to generate an entry identifier for their objects until all properties have been saved, an object's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property might not be available until after its **SaveChanges** method has been called.</span></span> <span data-ttu-id="288e5-145">有些提供程序会等到在**SaveChanges**调用上设置 KEEP_OPEN_READONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="288e5-145">Some providers wait until the KEEP_OPEN_READONLY flag is set on the **SaveChanges** call.</span></span> <span data-ttu-id="288e5-146">KEEP_OPEN_READONLY 指示要在当前调用中保存的更改是将对该对象进行的最后一处更改。</span><span class="sxs-lookup"><span data-stu-id="288e5-146">KEEP_OPEN_READONLY indicates that the changes to be saved in the current call will be the last changes that will be made on the object.</span></span> 
  
<span data-ttu-id="288e5-147">在客户端通过使用**SaveChanges**保存邮件更改并使用[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法释放 message 对象之前, 某些邮件存储实现不会在文件夹中显示新创建的邮件。</span><span class="sxs-lookup"><span data-stu-id="288e5-147">Some message store implementations do not show newly created messages in a folder until a client saves the message changes by using **SaveChanges** and releases the message objects by using the [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method.</span></span> <span data-ttu-id="288e5-148">此外, 在调用**savechanges**之前, 某些对象实现无法为新创建的对象生成**PR_ENTRYID**属性, 并且某些对象实现只有在使用 KEEP_OPEN_READONLY 调用**savechanges**之后才能为新创建的对象生成该属性。在_ulFlags_中设置。</span><span class="sxs-lookup"><span data-stu-id="288e5-148">In addition, some object implementations cannot generate a **PR_ENTRYID** property for a newly created object until after **SaveChanges** has been called, and some can do so only after **SaveChanges** has been called by using KEEP_OPEN_READONLY set in  _ulFlags_.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="288e5-149">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="288e5-149">Notes to implementers</span></span>

<span data-ttu-id="288e5-150">如果您收到 KEEP_OPEN_READONLY 标志, 则可以选择将对象的访问保留为读/写。</span><span class="sxs-lookup"><span data-stu-id="288e5-150">If you receive the KEEP_OPEN_READONLY flag, you have the option of leaving the object's access as read/write.</span></span> <span data-ttu-id="288e5-151">但是, 在传递 KEEP_OPEN_READWRITE 标志时, 提供程序不能使对象处于只读状态。</span><span class="sxs-lookup"><span data-stu-id="288e5-151">However, a provider can never leave an object in a read-only state when the KEEP_OPEN_READWRITE flag is passed.</span></span>
  
<span data-ttu-id="288e5-152">当客户端将多个附件保存到多个邮件中时, 它会为每个附件和每个邮件调用**SaveChanges**方法。</span><span class="sxs-lookup"><span data-stu-id="288e5-152">When a client saves multiple attachments to multiple messages, it calls the **SaveChanges** method for every attachment and every message.</span></span> <span data-ttu-id="288e5-153">通常, 客户端会为这些呼叫中的每个调用 (最后一个除外) 设置 MAPI_DEFERRED_ERRORS。</span><span class="sxs-lookup"><span data-stu-id="288e5-153">Often clients will set MAPI_DEFERRED_ERRORS for each of these calls except for the last one.</span></span> <span data-ttu-id="288e5-154">您可以使用上一次调用或更早的调用返回错误。</span><span class="sxs-lookup"><span data-stu-id="288e5-154">You can return errors either with the last call or earlier calls.</span></span> <span data-ttu-id="288e5-155">甚至可以忽略该标志。</span><span class="sxs-lookup"><span data-stu-id="288e5-155">You can even ignore the flag.</span></span> 
  
<span data-ttu-id="288e5-156">如果 KEEP_OPEN_READWRITE 或 KEEP_OPEN_READONLY 与 MAPI_DEFERRED_ERRORS 一起设置, 则可以忽略错误延期请求。</span><span class="sxs-lookup"><span data-stu-id="288e5-156">If either KEEP_OPEN_READWRITE or KEEP_OPEN_READONLY is set together with MAPI_DEFERRED_ERRORS, you can ignore the error deferment request.</span></span> <span data-ttu-id="288e5-157">如果_ulFlags_中未设置 MAPI_DEFERRED_ERRORS, 则可以为**SaveChanges**调用返回以前延迟的错误之一。</span><span class="sxs-lookup"><span data-stu-id="288e5-157">If MAPI_DEFERRED_ERRORS is not set in  _ulFlags_, one of the previously deferred errors can be returned for the **SaveChanges** call.</span></span> 
  
<span data-ttu-id="288e5-158">远程传输提供程序是否提供此方法的功能实现是可选的, 并取决于实现中的其他设计选择。</span><span class="sxs-lookup"><span data-stu-id="288e5-158">Whether a remote transport provider provides a functional implementation of this method is optional and depends on other design choices in your implementation.</span></span> <span data-ttu-id="288e5-159">如果您实现此方法, 请根据此处的文档执行此操作。</span><span class="sxs-lookup"><span data-stu-id="288e5-159">If you implement this method, do so according to the documentation here.</span></span> <span data-ttu-id="288e5-160">由于不会对 folder 对象和 status 对象进行事务处理, 因此, 至少远程传输提供程序的**SaveChanges**实现必须返回 S_OK, 而不实际执行任何工作。</span><span class="sxs-lookup"><span data-stu-id="288e5-160">Because folder objects and status objects are not transacted, at a minimum a remote transport provider's implementation of **SaveChanges** must return S_OK without actually doing any work.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="288e5-161">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="288e5-161">Notes to callers</span></span>

<span data-ttu-id="288e5-162">如果客户端传递 KEEP_OPEN_READONLY, 则调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法, 然后再次调用**SaveChanges** , 相同的实现可能会失败。</span><span class="sxs-lookup"><span data-stu-id="288e5-162">If a client passes KEEP_OPEN_READONLY, calls the [IMAPIProp::SetProps](imapiprop-setprops.md) method, and then calls **SaveChanges** again, the same implementation might fail.</span></span> 
  
<span data-ttu-id="288e5-163">从设置 KEEP_OPEN_READWRITE 的呼叫中接收 MAPI_E_NO_ACCESS 之后, 您将继续拥有对该对象的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="288e5-163">After receiving MAPI_E_NO_ACCESS from a call in which you set KEEP_OPEN_READWRITE, you will continue to have read/write permission to the object.</span></span> <span data-ttu-id="288e5-164">您可以再次调用**SaveChanges** , 将 KEEP_OPEN_READONLY 标志或没有标志传递给 KEEP_OPEN_SUFFIX。</span><span class="sxs-lookup"><span data-stu-id="288e5-164">You can call **SaveChanges** again, passing either the KEEP_OPEN_READONLY flag or no flags with KEEP_OPEN_SUFFIX.</span></span> 
  
<span data-ttu-id="288e5-165">提供程序是否支持 KEEP_OPEN_READWRITE 标志取决于提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="288e5-165">Whether a provider supports the KEEP_OPEN_READWRITE flag depends on the provider's implementation.</span></span> 
  
<span data-ttu-id="288e5-166">若要指示在**SaveChanges**为 IUnknown 之后对对象进行的唯一调用 **:: Release**, 请为_ulFlags_参数设置无标志。</span><span class="sxs-lookup"><span data-stu-id="288e5-166">To indicate that the only call to be made on the object after **SaveChanges** is **IUnknown::Release**, set no flags for the  _ulFlags_ parameter.</span></span> <span data-ttu-id="288e5-167">**SaveChanges**中的错误指示它无法使挂起的更改成为永久更改。</span><span class="sxs-lookup"><span data-stu-id="288e5-167">An error from **SaveChanges** indicates that it could not make the pending changes permanent.</span></span> <span data-ttu-id="288e5-168">不同的提供程序以不同的方式处理**SaveChanges**调用上缺少的标志。</span><span class="sxs-lookup"><span data-stu-id="288e5-168">Different providers handle the absence of flags on the **SaveChanges** call differently.</span></span> <span data-ttu-id="288e5-169">某些提供程序将此状态视为与 KEEP_OPEN_READONLY 相同;其他提供程序会将其解释为 KEEP_OPEN_READWRITE。</span><span class="sxs-lookup"><span data-stu-id="288e5-169">Some providers treat this state the same as KEEP_OPEN_READONLY; other providers interpret it the same as KEEP_OPEN_READWRITE.</span></span> <span data-ttu-id="288e5-170">当其他提供程序在**SaveChanges**调用上未收到标志时, 仍会关闭该对象。</span><span class="sxs-lookup"><span data-stu-id="288e5-170">Still other providers shut down the object when they do not receive flags on the **SaveChanges** call.</span></span> 
  
<span data-ttu-id="288e5-171">某些属性 (通常是计算属性) 在您调用**SaveChanges**和 (在某些情况下)**发布**之前无法处理。</span><span class="sxs-lookup"><span data-stu-id="288e5-171">Some properties, typically computed properties, cannot be processed until you call **SaveChanges** and, in some cases, **Release**.</span></span>
  
<span data-ttu-id="288e5-172">当您进行批量更改 (如将附件保存到多封邮件中) 时, 通过在_ulFlags_中设置 MAPI_DEFERRED_ERRORS 标志来推迟错误处理。</span><span class="sxs-lookup"><span data-stu-id="288e5-172">When you make bulk changes, such as saving attachments to multiple messages, defer error processing by setting the MAPI_DEFERRED_ERRORS flag in  _ulFlags_.</span></span> <span data-ttu-id="288e5-173">如果将多个附件保存到多封邮件中, 则对每个附件进行一次**savechanges**调用, 并对每封邮件执行一次**savechanges**调用。</span><span class="sxs-lookup"><span data-stu-id="288e5-173">If you save multiple attachments to multiple messages, make one **SaveChanges** call to each attachment and one **SaveChanges** call to each message.</span></span> <span data-ttu-id="288e5-174">为每个附件呼叫和除最后一个邮件之外的所有邮件设置 MAPI_DEFERRED_ERRORS 标志。</span><span class="sxs-lookup"><span data-stu-id="288e5-174">Set the MAPI_DEFERRED_ERRORS flag for each attachment call and for all messages except for the last one.</span></span> 
  
<span data-ttu-id="288e5-175">如果**SaveChanges**返回 MAPI_E_OBJECT_CHANGED, 请检查原始对象是否已被修改。</span><span class="sxs-lookup"><span data-stu-id="288e5-175">If **SaveChanges** returns MAPI_E_OBJECT_CHANGED, check whether the original object has been modified.</span></span> <span data-ttu-id="288e5-176">如果是这样, 则向用户发出警告, 用户可以请求所做的更改覆盖以前的更改, 或将对象保存到其他位置。</span><span class="sxs-lookup"><span data-stu-id="288e5-176">If so, warn the user, who can either request that the changes overwrite the previous changes or save the object elsewhere.</span></span> <span data-ttu-id="288e5-177">如果原始对象已被删除, 则向用户发出警告, 让他们有机会将该对象保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="288e5-177">If the original object has been deleted, warn the user to give them the opportunity to save the object in another location.</span></span> 
  
<span data-ttu-id="288e5-178">您无法在已删除的打开对象上使用 FORCE_SAVE 标志调用**SaveChanges** 。</span><span class="sxs-lookup"><span data-stu-id="288e5-178">You cannot call **SaveChanges** with the FORCE_SAVE flag on an open object that has been deleted.</span></span> 
  
<span data-ttu-id="288e5-179">如果**SaveChanges**返回错误, 则无论_ulFlags_参数中设置了何种标志, 要保存其更改的对象仍保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="288e5-179">If **SaveChanges** returns an error, the object whose changes were to be saved remains open, regardless of the flags set in the  _ulFlags_ parameter.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="288e5-180">_ulFlags_ NON_EMS_XP_SAVE 和 SPAMFILTER_ONSAVE 可能不是在您当前拥有的可下载头文件中定义的, 在这种情况下, 您可以使用以下值将其添加到代码中: >`#define SPAMFILTER_ONSAVE ((ULONG) 0x00000080)`>  `#define NON_EMS_XP_SAVE ((ULONG) 0x00001000)`</span><span class="sxs-lookup"><span data-stu-id="288e5-180">The  _ulFlags_ NON_EMS_XP_SAVE and SPAMFILTER_ONSAVE might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following values: >  `#define SPAMFILTER_ONSAVE ((ULONG) 0x00000080)`>  `#define NON_EMS_XP_SAVE ((ULONG) 0x00001000)`</span></span>
  
<span data-ttu-id="288e5-181">有关详细信息, 请参阅[保存 MAPI 属性](saving-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="288e5-181">For more information, see [Saving MAPI Properties](saving-mapi-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="288e5-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="288e5-182">See also</span></span>



[<span data-ttu-id="288e5-183">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="288e5-183">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="288e5-184">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="288e5-184">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)
  
[<span data-ttu-id="288e5-185">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="288e5-185">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="288e5-186">保存 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="288e5-186">Saving MAPI Properties</span></span>](saving-mapi-properties.md)

