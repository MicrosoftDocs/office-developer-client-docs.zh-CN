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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c12750b7899403e62b9c1603615e9fd6caa95eca
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569524"
---
# <a name="imapipropsavechanges"></a><span data-ttu-id="8e8b8-103">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="8e8b8-103">IMAPIProp::SaveChanges</span></span>

  
  
<span data-ttu-id="8e8b8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8e8b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8e8b8-105">使永久自上次保存操作对对象进行的任何更改。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-105">Makes permanent any changes that were made to an object since the last save operation.</span></span> 
  
```cpp
HRESULT SaveChanges(
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="8e8b8-106">参数</span><span class="sxs-lookup"><span data-stu-id="8e8b8-106">Parameters</span></span>

 <span data-ttu-id="8e8b8-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8e8b8-107">_ulFlags_</span></span>
  
> <span data-ttu-id="8e8b8-108">[in]位掩码的标志，用于控制调用**IMAPIProp::SaveChanges**方法时，该对象会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-108">[in] A bitmask of flags that controls what happens to the object when the **IMAPIProp::SaveChanges** method is called.</span></span> <span data-ttu-id="8e8b8-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="8e8b8-109">The following flags can be set:</span></span> 
    
<span data-ttu-id="8e8b8-110">NON_EMS_XP_SAVE</span><span class="sxs-lookup"><span data-stu-id="8e8b8-110">NON_EMS_XP_SAVE</span></span>
  
> <span data-ttu-id="8e8b8-111">指示邮件尚未传递从 Microsoft Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-111">Indicates that the message has not been delivered from a Microsoft Exchange Server.</span></span> <span data-ttu-id="8e8b8-112">此标志应结合使用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法和 ITEMPROC_FORCE 标志，以指示到 PST 存储符合条件的邮件规则处理之前的个人文件夹文件 (PST) 存储通知任何邮件已到达的侦听客户端。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-112">This flag should be used in combination with the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method and the ITEMPROC_FORCE flag to indicate to a PST store that the message is eligible for rules processing before the Personal Folders file (PST) store notifies any listening client that the message has arrived.</span></span> <span data-ttu-id="8e8b8-113">处理仅适用于新创建的邮件使用[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)不是 Exchange 服务器，这种情况下的服务器上 Exchange Server 此规则将已处理邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-113">This rules processing only applies to new messages that are created with [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) on a server that is not an Exchange Server, in which case the Exchange Server would have already processed rules on the message.</span></span> 
    
<span data-ttu-id="8e8b8-114">FORCE_SAVE</span><span class="sxs-lookup"><span data-stu-id="8e8b8-114">FORCE_SAVE</span></span> 
  
> <span data-ttu-id="8e8b8-115">更改应写入替代对该对象，所做的任何以前更改的对象，以及应关闭该对象。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-115">Changes should be written to the object, overriding any previous changes that were made to the object, and the object should be closed.</span></span> <span data-ttu-id="8e8b8-116">若要成功执行此操作，必须设置读/写权限。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-116">Read/write permission must be set for the operation to succeed.</span></span> <span data-ttu-id="8e8b8-117">**SaveChanges**为以前的呼叫返回 MAPI_E_OBJECT_CHANGED 之后使用 FORCE_SAVE 标志。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-117">The FORCE_SAVE flag is used after a previous call to **SaveChanges** returned MAPI_E_OBJECT_CHANGED.</span></span> 
    
<span data-ttu-id="8e8b8-118">KEEP_OPEN_READONLY</span><span class="sxs-lookup"><span data-stu-id="8e8b8-118">KEEP_OPEN_READONLY</span></span> 
  
> <span data-ttu-id="8e8b8-119">应将更改提交和对象应保持打开以进行读取。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-119">Changes should be committed and the object should be kept open for reading.</span></span> <span data-ttu-id="8e8b8-120">将不进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-120">No additional changes will be made.</span></span> 
    
<span data-ttu-id="8e8b8-121">KEEP_OPEN_READWRITE</span><span class="sxs-lookup"><span data-stu-id="8e8b8-121">KEEP_OPEN_READWRITE</span></span> 
  
> <span data-ttu-id="8e8b8-122">应将更改提交和对象应保持打开读/写权限。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-122">Changes should be committed and the object should be kept open for read/write permission.</span></span> <span data-ttu-id="8e8b8-123">读/写权限的首次打开对象时，通常是设置此标志。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-123">This flag is usually set when the object was first opened for read/write permission.</span></span> <span data-ttu-id="8e8b8-124">允许对对象的后续更改。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-124">Subsequent changes to the object are allowed.</span></span> 
    
<span data-ttu-id="8e8b8-125">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="8e8b8-125">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="8e8b8-126">允许**SaveChanges**返回成功，原因可能是完全提交更改之前。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-126">Allows **SaveChanges** to return successfully, possibly before the changes have been fully committed.</span></span> 
    
<span data-ttu-id="8e8b8-127">SPAMFILTER_ONSAVE</span><span class="sxs-lookup"><span data-stu-id="8e8b8-127">SPAMFILTER_ONSAVE</span></span>
  
> <span data-ttu-id="8e8b8-128">启用垃圾邮件筛选正在保存一条消息。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-128">Enables spam filtering on a message that is being saved.</span></span> <span data-ttu-id="8e8b8-129">只有当发件人的电子邮件地址类型为简单邮件传输协议 (SMTP)，并且将存储个人文件夹文件 (PST) 用于保存邮件的垃圾邮件筛选支持可用。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-129">Spam filtering support is available only if the sender's email address type is Simple Mail Transfer Protocol (SMTP), and the message is being saved to a store for a Personal Folders file (PST).</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8e8b8-130">返回值</span><span class="sxs-lookup"><span data-stu-id="8e8b8-130">Return value</span></span>

<span data-ttu-id="8e8b8-131">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e8b8-131">S_OK</span></span> 
  
> <span data-ttu-id="8e8b8-132">更改的承诺成功。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-132">The commitment of changes was successful.</span></span>
    
<span data-ttu-id="8e8b8-133">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="8e8b8-133">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="8e8b8-134">**SaveChanges**无法该对象保持打开状态的只读权限 KEEP_OPEN_READONLY 是否集或读/写权限如果 KEEP_OPEN_READWRITE 设置。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-134">**SaveChanges** cannot keep the object open for read-only permission if KEEP_OPEN_READONLY is set, or read/write permission if KEEP_OPEN_READWRITE is set.</span></span> <span data-ttu-id="8e8b8-135">无更改被提交。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-135">No changes are committed.</span></span> 
    
<span data-ttu-id="8e8b8-136">MAPI_E_OBJECT_CHANGED</span><span class="sxs-lookup"><span data-stu-id="8e8b8-136">MAPI_E_OBJECT_CHANGED</span></span> 
  
> <span data-ttu-id="8e8b8-137">对象已更改，因为它打开的。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-137">The object has changed since it was opened.</span></span>
    
<span data-ttu-id="8e8b8-138">MAPI_E_OBJECT_DELETED</span><span class="sxs-lookup"><span data-stu-id="8e8b8-138">MAPI_E_OBJECT_DELETED</span></span> 
  
> <span data-ttu-id="8e8b8-139">对象已被删除，因为它打开的。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-139">The object has been deleted since it was opened.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8e8b8-140">注解</span><span class="sxs-lookup"><span data-stu-id="8e8b8-140">Remarks</span></span>

<span data-ttu-id="8e8b8-141">**IMAPIProp::SaveChanges**方法使属性更改永久支持处理，如邮件、 附件、 通讯簿容器和邮件用户对象的事务模型的对象。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-141">The **IMAPIProp::SaveChanges** method makes property changes permanent for objects that support the transaction model of processing, such as messages, attachments, address book containers, and messaging user objects.</span></span> <span data-ttu-id="8e8b8-142">不支持事务，如文件夹、 消息存储和配置文件节的对象进行的更改永久立即。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-142">Objects that do not support transactions, such as folders, message stores, and profile sections, make changes permanent immediately.</span></span> <span data-ttu-id="8e8b8-143">不需要调用**SaveChanges**是必需的。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-143">No call to **SaveChanges** is required.</span></span> 
  
<span data-ttu-id="8e8b8-144">服务提供商不需要生成其对象的项标识符已保存了所有属性之前，因为对象的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性可能不可用直到后其**SaveChanges**方法调用了。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-144">Because service providers do not have to generate an entry identifier for their objects until all properties have been saved, an object's **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property might not be available until after its **SaveChanges** method has been called.</span></span> <span data-ttu-id="8e8b8-145">某些提供程序等待，直到 KEEP_OPEN_READONLY 标志设置**SaveChanges**呼叫。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-145">Some providers wait until the KEEP_OPEN_READONLY flag is set on the **SaveChanges** call.</span></span> <span data-ttu-id="8e8b8-146">KEEP_OPEN_READONLY 指示保存在当前呼叫中的更改将最后一个将对对象所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-146">KEEP_OPEN_READONLY indicates that the changes to be saved in the current call will be the last changes that will be made on the object.</span></span> 
  
<span data-ttu-id="8e8b8-147">某些消息存储实现执行操作不显示新创建的文件夹中的邮件客户端之前保存邮件使用**SaveChanges**更改，并使用[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法释放消息对象。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-147">Some message store implementations do not show newly created messages in a folder until a client saves the message changes by using **SaveChanges** and releases the message objects by using the [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) method.</span></span> <span data-ttu-id="8e8b8-148">此外，某些对象实现无法生成新创建的对象，直到**PR_ENTRYID**属性后已调用**SaveChanges** ，并且某些可以仅在**SaveChanges**已由使用 KEEP_OPEN_READONLY 调用之后执行此操作在_ulFlags_中设置。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-148">In addition, some object implementations cannot generate a **PR_ENTRYID** property for a newly created object until after **SaveChanges** has been called, and some can do so only after **SaveChanges** has been called by using KEEP_OPEN_READONLY set in  _ulFlags_.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="8e8b8-149">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="8e8b8-149">Notes to implementers</span></span>

<span data-ttu-id="8e8b8-150">如果您收到 KEEP_OPEN_READONLY 标志，您可以离开以读/写对象的访问。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-150">If you receive the KEEP_OPEN_READONLY flag, you have the option of leaving the object's access as read/write.</span></span> <span data-ttu-id="8e8b8-151">但是，提供程序可以从不使对象处于只读状态时传递 KEEP_OPEN_READWRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-151">However, a provider can never leave an object in a read-only state when the KEEP_OPEN_READWRITE flag is passed.</span></span>
  
<span data-ttu-id="8e8b8-152">时客户端多个将附件保存到多个邮件，每个附件和每个邮件将调用的**SaveChanges**方法。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-152">When a client saves multiple attachments to multiple messages, it calls the **SaveChanges** method for every attachment and every message.</span></span> <span data-ttu-id="8e8b8-153">通常客户端将为每个这些呼叫的最后一个除设置 MAPI_DEFERRED_ERRORS。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-153">Often clients will set MAPI_DEFERRED_ERRORS for each of these calls except for the last one.</span></span> <span data-ttu-id="8e8b8-154">您可以返回错误是与早期的呼叫的最后一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-154">You can return errors either with the last call or earlier calls.</span></span> <span data-ttu-id="8e8b8-155">您甚至可以忽略标志。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-155">You can even ignore the flag.</span></span> 
  
<span data-ttu-id="8e8b8-156">如果 KEEP_OPEN_READWRITE 或 KEEP_OPEN_READONLY MAPI_DEFERRED_ERRORS 一起设置，可以忽略错误延期请求。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-156">If either KEEP_OPEN_READWRITE or KEEP_OPEN_READONLY is set together with MAPI_DEFERRED_ERRORS, you can ignore the error deferment request.</span></span> <span data-ttu-id="8e8b8-157">如果_ulFlags_中未设置 MAPI_DEFERRED_ERRORS，之前延迟的错误之一可以返回**SaveChanges**呼叫。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-157">If MAPI_DEFERRED_ERRORS is not set in  _ulFlags_, one of the previously deferred errors can be returned for the **SaveChanges** call.</span></span> 
  
<span data-ttu-id="8e8b8-158">远程传输提供程序是否提供功能齐全的实现此方法是可选的取决于您的实现中其他设计选项。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-158">Whether a remote transport provider provides a functional implementation of this method is optional and depends on other design choices in your implementation.</span></span> <span data-ttu-id="8e8b8-159">如果实现此方法，请根据下面的文档。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-159">If you implement this method, do so according to the documentation here.</span></span> <span data-ttu-id="8e8b8-160">文件夹对象和状态对象不事务处理，因为至少远程传输提供程序的实现的**SaveChanges**必须返回 S_OK 而不实际执行任何工作。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-160">Because folder objects and status objects are not transacted, at a minimum a remote transport provider's implementation of **SaveChanges** must return S_OK without actually doing any work.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="8e8b8-161">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8e8b8-161">Notes to callers</span></span>

<span data-ttu-id="8e8b8-162">如果客户端将传递 KEEP_OPEN_READONLY 和调用[IMAPIProp::SetProps](imapiprop-setprops.md)方法，然后再次调用**SaveChanges** ，相同的实现可能会失败。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-162">If a client passes KEEP_OPEN_READONLY, calls the [IMAPIProp::SetProps](imapiprop-setprops.md) method, and then calls **SaveChanges** again, the same implementation might fail.</span></span> 
  
<span data-ttu-id="8e8b8-163">从呼叫接收 MAPI_E_NO_ACCESS 之后在其中将设置 KEEP_OPEN_READWRITE，您将继续具有对对象的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-163">After receiving MAPI_E_NO_ACCESS from a call in which you set KEEP_OPEN_READWRITE, you will continue to have read/write permission to the object.</span></span> <span data-ttu-id="8e8b8-164">您可以调用**SaveChanges**再次，传递 KEEP_OPEN_READONLY 标志或 KEEP_OPEN_SUFFIX 与任何标志。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-164">You can call **SaveChanges** again, passing either the KEEP_OPEN_READONLY flag or no flags with KEEP_OPEN_SUFFIX.</span></span> 
  
<span data-ttu-id="8e8b8-165">提供程序是否支持 KEEP_OPEN_READWRITE 标志取决于提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-165">Whether a provider supports the KEEP_OPEN_READWRITE flag depends on the provider's implementation.</span></span> 
  
<span data-ttu-id="8e8b8-166">若要指示仅在**SaveChanges**后进行的对象上呼叫**IUnknown::Release**，请设置_ulFlags_参数的任何标志。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-166">To indicate that the only call to be made on the object after **SaveChanges** is **IUnknown::Release**, set no flags for the  _ulFlags_ parameter.</span></span> <span data-ttu-id="8e8b8-167">从**SaveChanges**错误指示，它无法使待处理的更改永久。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-167">An error from **SaveChanges** indicates that it could not make the pending changes permanent.</span></span> <span data-ttu-id="8e8b8-168">不同的提供程序以不同方式处理标志**SaveChanges**呼叫不存在。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-168">Different providers handle the absence of flags on the **SaveChanges** call differently.</span></span> <span data-ttu-id="8e8b8-169">某些提供程序视为此状态相同 KEEP_OPEN_READONLY;其他提供程序将其解释 KEEP_OPEN_READWRITE 相同。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-169">Some providers treat this state the same as KEEP_OPEN_READONLY; other providers interpret it the same as KEEP_OPEN_READWRITE.</span></span> <span data-ttu-id="8e8b8-170">仍然其他提供程序关闭该对象时不会收到上**SaveChanges**呼叫的标志。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-170">Still other providers shut down the object when they do not receive flags on the **SaveChanges** call.</span></span> 
  
<span data-ttu-id="8e8b8-171">在您调用**SaveChanges**之前以及在某些情况下，**发布**无法处理某些属性，通常计算属性。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-171">Some properties, typically computed properties, cannot be processed until you call **SaveChanges** and, in some cases, **Release**.</span></span>
  
<span data-ttu-id="8e8b8-172">当您进行批量更改，如将附件保存到多个邮件时延迟处理通过_ulFlags_中设置 MAPI_DEFERRED_ERRORS 标志的错误。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-172">When you make bulk changes, such as saving attachments to multiple messages, defer error processing by setting the MAPI_DEFERRED_ERRORS flag in  _ulFlags_.</span></span> <span data-ttu-id="8e8b8-173">如果保存多个附件给多个邮件，使一个**SaveChanges**对每个附件的调用和一个**SaveChanges**调用每条消息。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-173">If you save multiple attachments to multiple messages, make one **SaveChanges** call to each attachment and one **SaveChanges** call to each message.</span></span> <span data-ttu-id="8e8b8-174">设置 MAPI_DEFERRED_ERRORS 标志为每个附件呼叫和最后一个除外的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-174">Set the MAPI_DEFERRED_ERRORS flag for each attachment call and for all messages except for the last one.</span></span> 
  
<span data-ttu-id="8e8b8-175">如果**SaveChanges**返回 MAPI_E_OBJECT_CHANGED，检查是否已修改的原始对象。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-175">If **SaveChanges** returns MAPI_E_OBJECT_CHANGED, check whether the original object has been modified.</span></span> <span data-ttu-id="8e8b8-176">如果是这样，警告的用户，也可以请求所做的更改覆盖以前的更改，或保存在其他地方的对象。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-176">If so, warn the user, who can either request that the changes overwrite the previous changes or save the object elsewhere.</span></span> <span data-ttu-id="8e8b8-177">如果原始对象已被删除，警告用户要为其提供的机会将对象保存在另一个位置。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-177">If the original object has been deleted, warn the user to give them the opportunity to save the object in another location.</span></span> 
  
<span data-ttu-id="8e8b8-178">不能与上打开的对象已删除的 FORCE_SAVE 标志调用**SaveChanges** 。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-178">You cannot call **SaveChanges** with the FORCE_SAVE flag on an open object that has been deleted.</span></span> 
  
<span data-ttu-id="8e8b8-179">如果**SaveChanges**返回一个错误，其更改已保存保持对象打开，无论设置_ulFlags_参数中的标志。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-179">If **SaveChanges** returns an error, the object whose changes were to be saved remains open, regardless of the flags set in the  _ulFlags_ parameter.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8e8b8-180">_UlFlags_ NON_EMS_XP_SAVE 和 SPAMFILTER_ONSAVE 可能未定义当前具有可下载头文件中，在这种情况下您可以将其添加到代码中使用以下值： >`#define SPAMFILTER_ONSAVE ((ULONG) 0x00000080)`>  `#define NON_EMS_XP_SAVE ((ULONG) 0x00001000)`</span><span class="sxs-lookup"><span data-stu-id="8e8b8-180">The  _ulFlags_ NON_EMS_XP_SAVE and SPAMFILTER_ONSAVE might not be defined in the downloadable header file you currently have, in which case you can add it to your code using the following values: >  `#define SPAMFILTER_ONSAVE ((ULONG) 0x00000080)`>  `#define NON_EMS_XP_SAVE ((ULONG) 0x00001000)`</span></span>
  
<span data-ttu-id="8e8b8-181">有关详细信息，请参阅[保存 MAPI 属性](saving-mapi-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="8e8b8-181">For more information, see [Saving MAPI Properties](saving-mapi-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8e8b8-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e8b8-182">See also</span></span>



[<span data-ttu-id="8e8b8-183">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="8e8b8-183">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="8e8b8-184">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="8e8b8-184">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)
  
[<span data-ttu-id="8e8b8-185">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8e8b8-185">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="8e8b8-186">保存 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8e8b8-186">Saving MAPI Properties</span></span>](saving-mapi-properties.md)

