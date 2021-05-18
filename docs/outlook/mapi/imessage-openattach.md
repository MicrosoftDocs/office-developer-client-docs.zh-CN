---
title: IMessageOpenAttach
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMessage.OpenAttach
api_type:
- COM
ms.assetid: b680f5a7-0df3-4e7b-bf3b-f149eb42be8d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e0c3747b48526b715f976e7bf3c142097c85f29a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405896"
---
# <a name="imessageopenattach"></a><span data-ttu-id="6305e-103">IMessage::OpenAttach</span><span class="sxs-lookup"><span data-stu-id="6305e-103">IMessage::OpenAttach</span></span>

  
  
<span data-ttu-id="6305e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6305e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6305e-105">打开附件。</span><span class="sxs-lookup"><span data-stu-id="6305e-105">Opens an attachment.</span></span> 
  
```cpp
HRESULT OpenAttach(
  ULONG ulAttachmentNum,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPATTACH FAR * lppAttach
);
```

## <a name="parameters"></a><span data-ttu-id="6305e-106">参数</span><span class="sxs-lookup"><span data-stu-id="6305e-106">Parameters</span></span>

 <span data-ttu-id="6305e-107">_ulAttachmentNum_</span><span class="sxs-lookup"><span data-stu-id="6305e-107">_ulAttachmentNum_</span></span>
  
> <span data-ttu-id="6305e-108">[in]要打开的附件的索引号，存储在附件的 PR_ATTACH_NUM ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中。 </span><span class="sxs-lookup"><span data-stu-id="6305e-108">[in] Index number of the attachment to open, as stored in the attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span> <span data-ttu-id="6305e-109">此索引号唯一标识邮件中的附件，并且仅在邮件上下文中有效。</span><span class="sxs-lookup"><span data-stu-id="6305e-109">This index number uniquely identifies the attachment in the message and is valid only in the context of the message.</span></span>
    
 <span data-ttu-id="6305e-110">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="6305e-110">_lpInterface_</span></span>
  
> <span data-ttu-id="6305e-111">[in]指向接口标识符 (IID) 表示用于访问附件的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="6305e-111">[in] Pointer to the interface identifier (IID) representing the interface to be used to access the attachment.</span></span> <span data-ttu-id="6305e-112">传递 NULL 会导致返回附件的标准接口 **IAttach。**</span><span class="sxs-lookup"><span data-stu-id="6305e-112">Passing NULL results in the attachment's standard interface, or **IAttach**, being returned.</span></span> 
    
 <span data-ttu-id="6305e-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6305e-113">_ulFlags_</span></span>
  
> <span data-ttu-id="6305e-114">[in]控制附件打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="6305e-114">[in] Bitmask of flags that controls how the attachment is opened.</span></span> <span data-ttu-id="6305e-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="6305e-115">The following flags can be set:</span></span> 
    
<span data-ttu-id="6305e-116">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="6305e-116">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="6305e-117">请求以用户允许的最大网络权限和最大客户端应用程序访问权限打开附件。</span><span class="sxs-lookup"><span data-stu-id="6305e-117">Requests that the attachment be opened with the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="6305e-118">例如，如果客户端具有读/写权限，则应该使用读/写权限打开附件;如果客户端具有只读访问权限，则应该以只读访问权限打开附件。</span><span class="sxs-lookup"><span data-stu-id="6305e-118">For example, if the client has read/write permission, the attachment should be opened with read/write permission; if the client has read-only access, the attachment should be opened with read-only access.</span></span> 
    
<span data-ttu-id="6305e-119">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="6305e-119">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="6305e-120">允许 **OpenAttach** 在附件完全可供调用客户端使用之前成功返回。</span><span class="sxs-lookup"><span data-stu-id="6305e-120">Allows **OpenAttach** to return successfully, possibly before the attachment is fully available to the calling client.</span></span> <span data-ttu-id="6305e-121">如果附件不可用，则对附件进行后续调用会导致错误。</span><span class="sxs-lookup"><span data-stu-id="6305e-121">If the attachment is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="6305e-122">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="6305e-122">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="6305e-123">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="6305e-123">Requests read/write permission.</span></span> <span data-ttu-id="6305e-124">默认情况下，使用只读访问权限打开附件，客户端不应在已授予读/写权限的假设下工作。</span><span class="sxs-lookup"><span data-stu-id="6305e-124">By default, attachments are opened with read-only access, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="6305e-125">_lppAttach_</span><span class="sxs-lookup"><span data-stu-id="6305e-125">_lppAttach_</span></span>
  
> <span data-ttu-id="6305e-126">[out]指向打开的附件的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="6305e-126">[out] Pointer to a pointer to the open attachment.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6305e-127">返回值</span><span class="sxs-lookup"><span data-stu-id="6305e-127">Return value</span></span>

<span data-ttu-id="6305e-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="6305e-128">S_OK</span></span> 
  
> <span data-ttu-id="6305e-129">已成功打开附件。</span><span class="sxs-lookup"><span data-stu-id="6305e-129">The attachment was successfully opened.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6305e-130">备注</span><span class="sxs-lookup"><span data-stu-id="6305e-130">Remarks</span></span>

<span data-ttu-id="6305e-131">**IMessage：：OpenAttach** 方法打开邮件的附件。</span><span class="sxs-lookup"><span data-stu-id="6305e-131">The **IMessage::OpenAttach** method opens a message's attachment.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="6305e-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="6305e-132">Notes to callers</span></span>

<span data-ttu-id="6305e-133">若要打开附件，您必须有权访问其附件 **编号或PR_ATTACH_NUM** 属性。</span><span class="sxs-lookup"><span data-stu-id="6305e-133">To open an attachment, you must have access to its attachment number or **PR_ATTACH_NUM** property.</span></span> <span data-ttu-id="6305e-134">调用 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md) 以检索邮件的附件表并找到表示要打开的附件的行。</span><span class="sxs-lookup"><span data-stu-id="6305e-134">Call [IMessage::GetAttachmentTable](imessage-getattachmenttable.md) to retrieve the message's attachment table and locate the row that represents the attachment to be opened.</span></span> <span data-ttu-id="6305e-135">有关详细信息 [，请参阅打开](opening-an-attachment.md) 附件。</span><span class="sxs-lookup"><span data-stu-id="6305e-135">See [Opening an Attachment](opening-an-attachment.md) for more information.</span></span> 
  
<span data-ttu-id="6305e-136">不要尝试多次打开一个附件;结果未定义，取决于邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="6305e-136">Do not try to open one attachment multiple times; the results are undefined and dependent on the message store provider.</span></span>
  
<span data-ttu-id="6305e-137">您可以请求以读/写模式而不是默认的只读模式打开附件。</span><span class="sxs-lookup"><span data-stu-id="6305e-137">You can request that the attachment be opened in read/write mode, instead of the default read-only mode.</span></span> <span data-ttu-id="6305e-138">但是，是否实际以读/写模式打开附件取决于邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="6305e-138">However, whether the attachment will actually be opened in read/write mode is up to the message store provider.</span></span> <span data-ttu-id="6305e-139">您可以尝试修改附件、准备处理可能失败，或者检查通过检索附件的 **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性（如果可用）授予的访问权限级别。</span><span class="sxs-lookup"><span data-stu-id="6305e-139">You can either attempt to modify the attachment, preparing to handle possible failure, or check the level of access that was granted by retrieving the attachment's **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property, if it is available.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6305e-140">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="6305e-140">MFCMAPI reference</span></span>

<span data-ttu-id="6305e-141">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6305e-141">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6305e-142">**文件**</span><span class="sxs-lookup"><span data-stu-id="6305e-142">**File**</span></span>|<span data-ttu-id="6305e-143">**函数**</span><span class="sxs-lookup"><span data-stu-id="6305e-143">**Function**</span></span>|<span data-ttu-id="6305e-144">**备注**</span><span class="sxs-lookup"><span data-stu-id="6305e-144">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6305e-145">AttachmentsDlg.cpp 用于</span><span class="sxs-lookup"><span data-stu-id="6305e-145">AttachmentsDlg.cpp Used to</span></span>  <br/> |<span data-ttu-id="6305e-146">CAttachmentsDlg：：OpenItemProp</span><span class="sxs-lookup"><span data-stu-id="6305e-146">CAttachmentsDlg::OpenItemProp</span></span>  <br/> |<span data-ttu-id="6305e-147">MFCMAPI 使用 **IMessage：：OpenAttach** 方法打开附件对象，</span><span class="sxs-lookup"><span data-stu-id="6305e-147">MFCMAPI uses the **IMessage::OpenAttach** method to open attachment objects,</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6305e-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6305e-148">See also</span></span>



[<span data-ttu-id="6305e-149">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="6305e-149">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)


[<span data-ttu-id="6305e-150">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="6305e-150">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

