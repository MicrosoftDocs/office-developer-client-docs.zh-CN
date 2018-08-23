---
title: IMAPIFolderCreateFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CreateFolder
api_type:
- COM
ms.assetid: 39d07fc8-09aa-4122-af32-b02f2c893d29
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 694f7ec5715a7348c9bd90c28d14f30d43d19974
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581781"
---
# <a name="imapifoldercreatefolder"></a><span data-ttu-id="1b66b-103">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="1b66b-103">IMAPIFolder::CreateFolder</span></span>

  
  
<span data-ttu-id="1b66b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1b66b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1b66b-105">创建新的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-105">Creates a new subfolder.</span></span>
  
```cpp
HRESULT CreateFolder(
  ULONG ulFolderType,
  LPSTR lpszFolderName,
  LPSTR lpszFolderComment,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPMAPIFOLDER FAR * lppFolder
);
```

## <a name="parameters"></a><span data-ttu-id="1b66b-106">参数</span><span class="sxs-lookup"><span data-stu-id="1b66b-106">Parameters</span></span>

 <span data-ttu-id="1b66b-107">_ulFolderType_</span><span class="sxs-lookup"><span data-stu-id="1b66b-107">_ulFolderType_</span></span>
  
> <span data-ttu-id="1b66b-108">[in]若要创建的文件夹的类型。</span><span class="sxs-lookup"><span data-stu-id="1b66b-108">[in] The type of folder to create.</span></span> <span data-ttu-id="1b66b-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="1b66b-109">The following flags can be set:</span></span>
    
<span data-ttu-id="1b66b-110">FOLDER_GENERIC</span><span class="sxs-lookup"><span data-stu-id="1b66b-110">FOLDER_GENERIC</span></span> 
  
> <span data-ttu-id="1b66b-111">应创建一个通用的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-111">A generic folder should be created.</span></span>
    
<span data-ttu-id="1b66b-112">FOLDER_SEARCH</span><span class="sxs-lookup"><span data-stu-id="1b66b-112">FOLDER_SEARCH</span></span> 
  
> <span data-ttu-id="1b66b-113">应创建一个搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-113">A search-results folder should be created.</span></span>
    
 <span data-ttu-id="1b66b-114">_lpszFolderName_</span><span class="sxs-lookup"><span data-stu-id="1b66b-114">_lpszFolderName_</span></span>
  
> <span data-ttu-id="1b66b-115">[in]一个指向一个字符串，包含新的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="1b66b-115">[in] A pointer to a string that contains the name for the new folder.</span></span> <span data-ttu-id="1b66b-116">此名称是新文件夹的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的基础。</span><span class="sxs-lookup"><span data-stu-id="1b66b-116">This name is the basis for the new folder's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="1b66b-117">_lpszFolderComment_</span><span class="sxs-lookup"><span data-stu-id="1b66b-117">_lpszFolderComment_</span></span>
  
> <span data-ttu-id="1b66b-118">[in]一个指向一个字符串，包含与新的文件夹关联的注释。</span><span class="sxs-lookup"><span data-stu-id="1b66b-118">[in] A pointer to a string that contains a comment associated with the new folder.</span></span> <span data-ttu-id="1b66b-119">此字符串将成为新文件夹的**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="1b66b-119">This string becomes the value of the new folder's **PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) property.</span></span> <span data-ttu-id="1b66b-120">如果传递 NULL，则文件夹具有没有初始的注释。</span><span class="sxs-lookup"><span data-stu-id="1b66b-120">If NULL is passed, the folder has no initial comment.</span></span>
    
 <span data-ttu-id="1b66b-121">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="1b66b-121">_lpInterface_</span></span>
  
> <span data-ttu-id="1b66b-122">[in]指向接口标识 (IID) 值，该值代表要用于访问新文件夹的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1b66b-122">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the new folder.</span></span> <span data-ttu-id="1b66b-123">传递 NULL 将导致消息存储提供程序返回的标准文件夹接口， [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="1b66b-123">Passing NULL causes the message store provider to return the standard folder interface, [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="1b66b-124">客户端必须传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="1b66b-124">Clients must pass NULL.</span></span> <span data-ttu-id="1b66b-125">其他呼叫者可以设置为 IID_IUnknown、 IID_IMAPIProp、 IID_IMAPIContainer 或 IID_IMAPIFolder _lpInterface_参数。</span><span class="sxs-lookup"><span data-stu-id="1b66b-125">Other callers can set the  _lpInterface_ parameter to IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, or IID_IMAPIFolder.</span></span> 
    
 <span data-ttu-id="1b66b-126">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1b66b-126">_ulFlags_</span></span>
  
> <span data-ttu-id="1b66b-127">[in]位掩码的标志，控制如何创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-127">[in] A bitmask of flags that controls how the folder is created.</span></span> <span data-ttu-id="1b66b-128">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="1b66b-128">The following flags can be set:</span></span>
    
<span data-ttu-id="1b66b-129">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="1b66b-129">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="1b66b-130">允许**CreateFolder**返回成功，原因可能是新文件夹之前调用客户端对完全可用。</span><span class="sxs-lookup"><span data-stu-id="1b66b-130">Allows **CreateFolder** to return successfully, possibly before the new folder is fully available to the calling client.</span></span> <span data-ttu-id="1b66b-131">如果新文件夹不可用，进行后续呼叫到它会导致出错。</span><span class="sxs-lookup"><span data-stu-id="1b66b-131">If the new folder is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="1b66b-132">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1b66b-132">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="1b66b-133">Unicode 格式的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="1b66b-133">The name of the folder is in Unicode format.</span></span> <span data-ttu-id="1b66b-134">如果未设置 MAPI_UNICODE 标志，文件夹名称是 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="1b66b-134">If the MAPI_UNICODE flag is not set, the folder name is in ANSI format.</span></span>
    
<span data-ttu-id="1b66b-135">OPEN_IF_EXISTS</span><span class="sxs-lookup"><span data-stu-id="1b66b-135">OPEN_IF_EXISTS</span></span> 
  
> <span data-ttu-id="1b66b-136">允许方法成功，即使已_lpszFolderName_参数中名为文件夹存在通过打开具有该名称的现有文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-136">Allows the method to succeed even if the folder named in the  _lpszFolderName_ parameter already exists by opening the existing folder that has that name.</span></span> <span data-ttu-id="1b66b-137">请注意，是否多个存在具有所提供的名称，允许同级文件夹具有相同名称的消息存储提供程序可能不打开现有文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-137">Note that message store providers that allow sibling folders to have the same name might not open an existing folder if more than one exists with the supplied name.</span></span> 
    
 <span data-ttu-id="1b66b-138">_lppFolder_</span><span class="sxs-lookup"><span data-stu-id="1b66b-138">_lppFolder_</span></span>
  
> <span data-ttu-id="1b66b-139">[输出]为指向新创建的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="1b66b-139">[out] A pointer to a pointer to the newly created folder.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1b66b-140">返回值</span><span class="sxs-lookup"><span data-stu-id="1b66b-140">Return value</span></span>

<span data-ttu-id="1b66b-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b66b-141">S_OK</span></span> 
  
> <span data-ttu-id="1b66b-142">已成功创建或打开，如果设置了 OPEN_IF_EXISTS 标志新文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-142">The new folder has been successfully created or opened, if the OPEN_IF_EXISTS flag is set.</span></span>
    
<span data-ttu-id="1b66b-143">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="1b66b-143">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="1b66b-144">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="1b66b-144">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="1b66b-145">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="1b66b-145">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="1b66b-146">存在具有已_lpszFolderName_参数中指定的名称的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-146">A folder that has the name given in the  _lpszFolderName_ parameter already exists.</span></span> <span data-ttu-id="1b66b-147">文件夹名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1b66b-147">Folder names must be unique.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1b66b-148">注解</span><span class="sxs-lookup"><span data-stu-id="1b66b-148">Remarks</span></span>

<span data-ttu-id="1b66b-149">**IMAPIFolder::CreateFolder**方法在当前文件夹中创建子文件夹，并将条目标识符分配给新文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-149">The **IMAPIFolder::CreateFolder** method creates a subfolder in the current folder and assigns an entry identifier to the new folder.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1b66b-150">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1b66b-150">Notes to callers</span></span>

<span data-ttu-id="1b66b-151">**CreateFolder**返回时，都可以识别新文件夹的条目标识符可能不可用。</span><span class="sxs-lookup"><span data-stu-id="1b66b-151">When **CreateFolder** returns, be aware that the entry identifier for the new folder might not be available.</span></span> <span data-ttu-id="1b66b-152">某些消息存储提供程序后，不要做出条目标识符可用直到以前呼叫过该新文件夹的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法，若要永久保存它。</span><span class="sxs-lookup"><span data-stu-id="1b66b-152">Some message store providers do not make entry identifiers available until after you have called the new folder's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to permanently save it.</span></span> <span data-ttu-id="1b66b-153">这是尤为如果您已设置 MAPI_DEFERRED_ERRORS 标志。</span><span class="sxs-lookup"><span data-stu-id="1b66b-153">This is especially true if you have set the MAPI_DEFERRED_ERRORS flag.</span></span> 
  
<span data-ttu-id="1b66b-154">请注意，某些消息存储提供程序始终指向_lppFolder_参数文件夹的标准接口，而不考虑为_lpInterface_参数中传递的值。</span><span class="sxs-lookup"><span data-stu-id="1b66b-154">Be aware that some message store providers always point the  _lppFolder_ parameter to the folder's standard interface, regardless of the value that you pass in for the  _lpInterface_ parameter.</span></span> <span data-ttu-id="1b66b-155">返回的接口指针可能不是您预期的类型，因为调用该新文件夹的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1b66b-155">Because the interface pointer that is returned might not be of the type that you expect, call the new folder's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) property.</span></span> <span data-ttu-id="1b66b-156">如有必要，进行其他呼叫之前强制转换该指针指向更适合的类型。</span><span class="sxs-lookup"><span data-stu-id="1b66b-156">If necessary, cast the pointer to a more appropriate type before you make other calls.</span></span>
  
<span data-ttu-id="1b66b-157">大多数消息存储提供程序需要是唯一的相对于其同级文件夹的名称的新文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="1b66b-157">Most message store providers require the name of the new folder to be unique with respect to the names of its sibling folders.</span></span> <span data-ttu-id="1b66b-158">能够处理 MAPI_E_COLLISION 错误值，如果不遵循此规则，则返回的。</span><span class="sxs-lookup"><span data-stu-id="1b66b-158">Be able to handle the MAPI_E_COLLISION error value, which is returned if this rule is not followed.</span></span> 
  
<span data-ttu-id="1b66b-159">若要确定新创建的文件夹的条目标识符，请调用新文件夹的**IMAPIProp::GetProps**方法来检索其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1b66b-159">To determine the entry identifier of the newly created folder, call the new folder's **IMAPIProp::GetProps** method to retrieve its **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1b66b-160">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1b66b-160">MFCMAPI reference</span></span>

<span data-ttu-id="1b66b-161">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1b66b-161">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1b66b-162">**文件**</span><span class="sxs-lookup"><span data-stu-id="1b66b-162">**File**</span></span>|<span data-ttu-id="1b66b-163">**函数**</span><span class="sxs-lookup"><span data-stu-id="1b66b-163">**Function**</span></span>|<span data-ttu-id="1b66b-164">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1b66b-164">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1b66b-165">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="1b66b-165">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="1b66b-166">CMsgStoreDlg::OnCreateSubFolder</span><span class="sxs-lookup"><span data-stu-id="1b66b-166">CMsgStoreDlg::OnCreateSubFolder</span></span>  <br/> |<span data-ttu-id="1b66b-167">MFCMAPI 使用**CMsgStoreDlg::OnCreateSubFolder**方法在 MFCMAPI 中创建新文件夹。</span><span class="sxs-lookup"><span data-stu-id="1b66b-167">MFCMAPI uses the **CMsgStoreDlg::OnCreateSubFolder** method to create new folders in MFCMAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1b66b-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b66b-168">See also</span></span>



[<span data-ttu-id="1b66b-169">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="1b66b-169">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="1b66b-170">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="1b66b-170">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="1b66b-171">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1b66b-171">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

