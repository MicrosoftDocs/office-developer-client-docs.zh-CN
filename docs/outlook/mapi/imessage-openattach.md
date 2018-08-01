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
ms.openlocfilehash: c702e4063bf5e5a06a9e476a02172a780c7e326a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775761"
---
# <a name="imessageopenattach"></a><span data-ttu-id="fb27f-103">IMessage::OpenAttach</span><span class="sxs-lookup"><span data-stu-id="fb27f-103">IMessage::OpenAttach</span></span>

  
  
<span data-ttu-id="fb27f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fb27f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fb27f-105">打开附件。</span><span class="sxs-lookup"><span data-stu-id="fb27f-105">Opens an attachment.</span></span> 
  
```cpp
HRESULT OpenAttach(
  ULONG ulAttachmentNum,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPATTACH FAR * lppAttach
);
```

## <a name="parameters"></a><span data-ttu-id="fb27f-106">参数</span><span class="sxs-lookup"><span data-stu-id="fb27f-106">Parameters</span></span>

 <span data-ttu-id="fb27f-107">_ulAttachmentNum_</span><span class="sxs-lookup"><span data-stu-id="fb27f-107">_ulAttachmentNum_</span></span>
  
> <span data-ttu-id="fb27f-108">[in]若要打开，存储在附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中的附件的索引号。</span><span class="sxs-lookup"><span data-stu-id="fb27f-108">[in] Index number of the attachment to open, as stored in the attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span> <span data-ttu-id="fb27f-109">此索引号唯一地标识邮件中的附件，仅在邮件的上下文中有效。</span><span class="sxs-lookup"><span data-stu-id="fb27f-109">This index number uniquely identifies the attachment in the message and is valid only in the context of the message.</span></span>
    
 <span data-ttu-id="fb27f-110">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="fb27f-110">_lpInterface_</span></span>
  
> <span data-ttu-id="fb27f-111">[in]表示要用于访问该附件的接口的界面标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="fb27f-111">[in] Pointer to the interface identifier (IID) representing the interface to be used to access the attachment.</span></span> <span data-ttu-id="fb27f-112">传递 NULL 将导致附件的标准界面或**IAttach**，返回。</span><span class="sxs-lookup"><span data-stu-id="fb27f-112">Passing NULL results in the attachment's standard interface, or **IAttach**, being returned.</span></span> 
    
 <span data-ttu-id="fb27f-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fb27f-113">_ulFlags_</span></span>
  
> <span data-ttu-id="fb27f-114">[in]位掩码的标志，控制如何打开附件。</span><span class="sxs-lookup"><span data-stu-id="fb27f-114">[in] Bitmask of flags that controls how the attachment is opened.</span></span> <span data-ttu-id="fb27f-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="fb27f-115">The following flags can be set:</span></span> 
    
<span data-ttu-id="fb27f-116">MAPI_BEST_ACCESS</span><span class="sxs-lookup"><span data-stu-id="fb27f-116">MAPI_BEST_ACCESS</span></span> 
  
> <span data-ttu-id="fb27f-117">请求具有最大网络权限允许用户和最大客户端应用程序访问打开的附件。</span><span class="sxs-lookup"><span data-stu-id="fb27f-117">Requests that the attachment be opened with the maximum network permissions allowed for the user and the maximum client application access.</span></span> <span data-ttu-id="fb27f-118">例如，如果客户端具有读/写权限，附件应打开具有读/写权限;如果客户端具有只读访问权限，则应具有只读访问权限打开附件。</span><span class="sxs-lookup"><span data-stu-id="fb27f-118">For example, if the client has read/write permission, the attachment should be opened with read/write permission; if the client has read-only access, the attachment should be opened with read-only access.</span></span> 
    
<span data-ttu-id="fb27f-119">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="fb27f-119">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="fb27f-120">允许**OpenAttach**返回成功，可能之前附件是完全可调用客户端。</span><span class="sxs-lookup"><span data-stu-id="fb27f-120">Allows **OpenAttach** to return successfully, possibly before the attachment is fully available to the calling client.</span></span> <span data-ttu-id="fb27f-121">如果附件不可用，请进行后续呼叫到它会导致出错。</span><span class="sxs-lookup"><span data-stu-id="fb27f-121">If the attachment is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="fb27f-122">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="fb27f-122">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="fb27f-123">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="fb27f-123">Requests read/write permission.</span></span> <span data-ttu-id="fb27f-124">默认情况下，具有只读访问权限打开的附件和客户端不应以为，读/写权限授予起作用。</span><span class="sxs-lookup"><span data-stu-id="fb27f-124">By default, attachments are opened with read-only access, and clients should not work on the assumption that read/write permission has been granted.</span></span> 
    
 <span data-ttu-id="fb27f-125">_lppAttach_</span><span class="sxs-lookup"><span data-stu-id="fb27f-125">_lppAttach_</span></span>
  
> <span data-ttu-id="fb27f-126">[输出]为打开的附件指针的指针。</span><span class="sxs-lookup"><span data-stu-id="fb27f-126">[out] Pointer to a pointer to the open attachment.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fb27f-127">返回值</span><span class="sxs-lookup"><span data-stu-id="fb27f-127">Return value</span></span>

<span data-ttu-id="fb27f-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb27f-128">S_OK</span></span> 
  
> <span data-ttu-id="fb27f-129">已成功打开附件。</span><span class="sxs-lookup"><span data-stu-id="fb27f-129">The attachment was successfully opened.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fb27f-130">说明</span><span class="sxs-lookup"><span data-stu-id="fb27f-130">Remarks</span></span>

<span data-ttu-id="fb27f-131">**IMessage::OpenAttach**方法打开邮件附件。</span><span class="sxs-lookup"><span data-stu-id="fb27f-131">The **IMessage::OpenAttach** method opens a message's attachment.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="fb27f-132">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="fb27f-132">Notes to callers</span></span>

<span data-ttu-id="fb27f-133">若要打开附件，您必须对附件编号或**PR_ATTACH_NUM**属性的访问。</span><span class="sxs-lookup"><span data-stu-id="fb27f-133">To open an attachment, you must have access to its attachment number or **PR_ATTACH_NUM** property.</span></span> <span data-ttu-id="fb27f-134">调用[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)检索邮件的附件表并定位到值，该值代表打开的附件的行。</span><span class="sxs-lookup"><span data-stu-id="fb27f-134">Call [IMessage::GetAttachmentTable](imessage-getattachmenttable.md) to retrieve the message's attachment table and locate the row that represents the attachment to be opened.</span></span> <span data-ttu-id="fb27f-135">有关详细信息，请参阅[打开附件](opening-an-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="fb27f-135">See [Opening an Attachment](opening-an-attachment.md) for more information.</span></span> 
  
<span data-ttu-id="fb27f-136">不要尝试打开一个附件多次;则结果为未定义和依赖于在消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb27f-136">Do not try to open one attachment multiple times; the results are undefined and dependent on the message store provider.</span></span>
  
<span data-ttu-id="fb27f-137">您可以请求的读/写模式，而不是默认只读模式中打开附件。</span><span class="sxs-lookup"><span data-stu-id="fb27f-137">You can request that the attachment be opened in read/write mode, instead of the default read-only mode.</span></span> <span data-ttu-id="fb27f-138">但是，是否附件实际上都将在读/写模式中打开是最多的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="fb27f-138">However, whether the attachment will actually be opened in read/write mode is up to the message store provider.</span></span> <span data-ttu-id="fb27f-139">您可以修改附件，或者是尝试准备处理可能失败，或检查的检索附件的**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性，如果可用授予的访问级别。</span><span class="sxs-lookup"><span data-stu-id="fb27f-139">You can either attempt to modify the attachment, preparing to handle possible failure, or check the level of access that was granted by retrieving the attachment's **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property, if it is available.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="fb27f-140">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="fb27f-140">MFCMAPI reference</span></span>

<span data-ttu-id="fb27f-141">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="fb27f-141">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="fb27f-142">**文件**</span><span class="sxs-lookup"><span data-stu-id="fb27f-142">**File**</span></span>|<span data-ttu-id="fb27f-143">**函数**</span><span class="sxs-lookup"><span data-stu-id="fb27f-143">**Function**</span></span>|<span data-ttu-id="fb27f-144">**Comment**</span><span class="sxs-lookup"><span data-stu-id="fb27f-144">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb27f-145">用于 AttachmentsDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="fb27f-145">AttachmentsDlg.cpp Used to</span></span>  <br/> |<span data-ttu-id="fb27f-146">CAttachmentsDlg::OpenItemProp</span><span class="sxs-lookup"><span data-stu-id="fb27f-146">CAttachmentsDlg::OpenItemProp</span></span>  <br/> |<span data-ttu-id="fb27f-147">MFCMAPI 使用**IMessage::OpenAttach**方法打开 attachment 对象</span><span class="sxs-lookup"><span data-stu-id="fb27f-147">MFCMAPI uses the **IMessage::OpenAttach** method to open attachment objects,</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fb27f-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb27f-148">See also</span></span>



[<span data-ttu-id="fb27f-149">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fb27f-149">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)


[<span data-ttu-id="fb27f-150">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="fb27f-150">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

