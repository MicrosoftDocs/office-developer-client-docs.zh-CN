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
ms.openlocfilehash: 606d780aa59e363c30ddc7a5b562db64d845ccb0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436760"
---
# <a name="imapifoldercreatefolder"></a><span data-ttu-id="78075-103">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="78075-103">IMAPIFolder::CreateFolder</span></span>

  
  
<span data-ttu-id="78075-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="78075-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="78075-105">创建新的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="78075-105">Creates a new subfolder.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="78075-106">参数</span><span class="sxs-lookup"><span data-stu-id="78075-106">Parameters</span></span>

 <span data-ttu-id="78075-107">_ulFolderType_</span><span class="sxs-lookup"><span data-stu-id="78075-107">_ulFolderType_</span></span>
  
> <span data-ttu-id="78075-108">[in]要创建的文件夹的类型。</span><span class="sxs-lookup"><span data-stu-id="78075-108">[in] The type of folder to create.</span></span> <span data-ttu-id="78075-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="78075-109">The following flags can be set:</span></span>
    
<span data-ttu-id="78075-110">FOLDER_GENERIC</span><span class="sxs-lookup"><span data-stu-id="78075-110">FOLDER_GENERIC</span></span> 
  
> <span data-ttu-id="78075-111">应创建一个泛型文件夹。</span><span class="sxs-lookup"><span data-stu-id="78075-111">A generic folder should be created.</span></span>
    
<span data-ttu-id="78075-112">FOLDER_SEARCH</span><span class="sxs-lookup"><span data-stu-id="78075-112">FOLDER_SEARCH</span></span> 
  
> <span data-ttu-id="78075-113">应创建搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="78075-113">A search-results folder should be created.</span></span>
    
 <span data-ttu-id="78075-114">_lpszFolderName_</span><span class="sxs-lookup"><span data-stu-id="78075-114">_lpszFolderName_</span></span>
  
> <span data-ttu-id="78075-115">[in]指向包含新文件夹名称的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="78075-115">[in] A pointer to a string that contains the name for the new folder.</span></span> <span data-ttu-id="78075-116">此名称是新文件夹PR_DISPLAY_NAME ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的基础。 </span><span class="sxs-lookup"><span data-stu-id="78075-116">This name is the basis for the new folder's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="78075-117">_lpszFolderComment_</span><span class="sxs-lookup"><span data-stu-id="78075-117">_lpszFolderComment_</span></span>
  
> <span data-ttu-id="78075-118">[in]指向包含与新文件夹关联的注释的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="78075-118">[in] A pointer to a string that contains a comment associated with the new folder.</span></span> <span data-ttu-id="78075-119">此字符串将成为[PidTagComment](pidtagcomment-canonical-property.md) PR_COMMENT (新) 的值。 </span><span class="sxs-lookup"><span data-stu-id="78075-119">This string becomes the value of the new folder's **PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) property.</span></span> <span data-ttu-id="78075-120">如果传递 NULL，则文件夹没有初始注释。</span><span class="sxs-lookup"><span data-stu-id="78075-120">If NULL is passed, the folder has no initial comment.</span></span>
    
 <span data-ttu-id="78075-121">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="78075-121">_lpInterface_</span></span>
  
> <span data-ttu-id="78075-122">[in]指向接口标识符的指针 (IID) 表示用于访问新文件夹的接口。</span><span class="sxs-lookup"><span data-stu-id="78075-122">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the new folder.</span></span> <span data-ttu-id="78075-123">传递 NULL 会导致邮件存储提供程序返回标准文件夹接口 [IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="78075-123">Passing NULL causes the message store provider to return the standard folder interface, [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="78075-124">客户端必须传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="78075-124">Clients must pass NULL.</span></span> <span data-ttu-id="78075-125">其他调用方可以将  _lpInterface_ 参数设置为 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 或 IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="78075-125">Other callers can set the  _lpInterface_ parameter to IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, or IID_IMAPIFolder.</span></span> 
    
 <span data-ttu-id="78075-126">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="78075-126">_ulFlags_</span></span>
  
> <span data-ttu-id="78075-127">[in]控制如何创建文件夹的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="78075-127">[in] A bitmask of flags that controls how the folder is created.</span></span> <span data-ttu-id="78075-128">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="78075-128">The following flags can be set:</span></span>
    
<span data-ttu-id="78075-129">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="78075-129">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="78075-130">允许 **CreateFolder** 成功返回，可能在新文件夹对调用客户端完全可用之前。</span><span class="sxs-lookup"><span data-stu-id="78075-130">Allows **CreateFolder** to return successfully, possibly before the new folder is fully available to the calling client.</span></span> <span data-ttu-id="78075-131">如果新文件夹不可用，则后续调用它会导致错误。</span><span class="sxs-lookup"><span data-stu-id="78075-131">If the new folder is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="78075-132">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="78075-132">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="78075-133">文件夹的名称采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="78075-133">The name of the folder is in Unicode format.</span></span> <span data-ttu-id="78075-134">如果未MAPI_UNICODE，文件夹名称将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="78075-134">If the MAPI_UNICODE flag is not set, the folder name is in ANSI format.</span></span>
    
<span data-ttu-id="78075-135">OPEN_IF_EXISTS</span><span class="sxs-lookup"><span data-stu-id="78075-135">OPEN_IF_EXISTS</span></span> 
  
> <span data-ttu-id="78075-136">通过打开具有该名称的现有文件夹，即使  _lpszFolderName_ 参数中指定的文件夹已存在，也允许该方法成功。</span><span class="sxs-lookup"><span data-stu-id="78075-136">Allows the method to succeed even if the folder named in the  _lpszFolderName_ parameter already exists by opening the existing folder that has that name.</span></span> <span data-ttu-id="78075-137">请注意，如果具有提供的名称存在多个现有文件夹，则允许同级文件夹具有相同的名称的邮件存储提供程序可能无法打开现有文件夹。</span><span class="sxs-lookup"><span data-stu-id="78075-137">Note that message store providers that allow sibling folders to have the same name might not open an existing folder if more than one exists with the supplied name.</span></span> 
    
 <span data-ttu-id="78075-138">_lppFolder_</span><span class="sxs-lookup"><span data-stu-id="78075-138">_lppFolder_</span></span>
  
> <span data-ttu-id="78075-139">[out]指向指向新建文件夹的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="78075-139">[out] A pointer to a pointer to the newly created folder.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="78075-140">返回值</span><span class="sxs-lookup"><span data-stu-id="78075-140">Return value</span></span>

<span data-ttu-id="78075-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="78075-141">S_OK</span></span> 
  
> <span data-ttu-id="78075-142">如果设置了新文件夹标志，则已成功创建或打开OPEN_IF_EXISTS文件夹。</span><span class="sxs-lookup"><span data-stu-id="78075-142">The new folder has been successfully created or opened, if the OPEN_IF_EXISTS flag is set.</span></span>
    
<span data-ttu-id="78075-143">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="78075-143">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="78075-144">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="78075-144">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="78075-145">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="78075-145">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="78075-146">_lpszFolderName_ 参数中提供的名称的文件夹已存在。</span><span class="sxs-lookup"><span data-stu-id="78075-146">A folder that has the name given in the  _lpszFolderName_ parameter already exists.</span></span> <span data-ttu-id="78075-147">文件夹名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="78075-147">Folder names must be unique.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="78075-148">备注</span><span class="sxs-lookup"><span data-stu-id="78075-148">Remarks</span></span>

<span data-ttu-id="78075-149">**IMAPIFolder：：CreateFolder** 方法在当前文件夹中创建子文件夹，并将条目标识符分配给新文件夹。</span><span class="sxs-lookup"><span data-stu-id="78075-149">The **IMAPIFolder::CreateFolder** method creates a subfolder in the current folder and assigns an entry identifier to the new folder.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="78075-150">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="78075-150">Notes to callers</span></span>

<span data-ttu-id="78075-151">当 **CreateFolder** 返回时，请注意新文件夹的条目标识符可能不可用。</span><span class="sxs-lookup"><span data-stu-id="78075-151">When **CreateFolder** returns, be aware that the entry identifier for the new folder might not be available.</span></span> <span data-ttu-id="78075-152">一些邮件存储提供程序在调用新文件夹的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法以永久保存它之前，不会提供条目标识符。</span><span class="sxs-lookup"><span data-stu-id="78075-152">Some message store providers do not make entry identifiers available until after you have called the new folder's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to permanently save it.</span></span> <span data-ttu-id="78075-153">如果已设置值标志，MAPI_DEFERRED_ERRORS尤其如此。</span><span class="sxs-lookup"><span data-stu-id="78075-153">This is especially true if you have set the MAPI_DEFERRED_ERRORS flag.</span></span> 
  
<span data-ttu-id="78075-154">请注意，某些邮件存储提供程序始终将  _lppFolder_ 参数指向文件夹的标准接口，而不考虑为  _lpInterface_ 参数传递的值。</span><span class="sxs-lookup"><span data-stu-id="78075-154">Be aware that some message store providers always point the  _lppFolder_ parameter to the folder's standard interface, regardless of the value that you pass in for the  _lpInterface_ parameter.</span></span> <span data-ttu-id="78075-155">由于返回的接口指针可能不是您预期的类型，因此请调用新文件夹的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索 **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="78075-155">Because the interface pointer that is returned might not be of the type that you expect, call the new folder's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) property.</span></span> <span data-ttu-id="78075-156">如有必要，在进行其他调用之前，将指针强制转换到更合适的类型。</span><span class="sxs-lookup"><span data-stu-id="78075-156">If necessary, cast the pointer to a more appropriate type before you make other calls.</span></span>
  
<span data-ttu-id="78075-157">大多数邮件存储提供程序都要求新文件夹的名称对于同级文件夹的名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="78075-157">Most message store providers require the name of the new folder to be unique with respect to the names of its sibling folders.</span></span> <span data-ttu-id="78075-158">能够处理错误MAPI_E_COLLISION，如果未遵循此规则，则返回该错误值。</span><span class="sxs-lookup"><span data-stu-id="78075-158">Be able to handle the MAPI_E_COLLISION error value, which is returned if this rule is not followed.</span></span> 
  
<span data-ttu-id="78075-159">若要确定新创建的文件夹的条目标识符，请调用新文件夹的 **IMAPIProp：：GetProps** 方法来检索其 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="78075-159">To determine the entry identifier of the newly created folder, call the new folder's **IMAPIProp::GetProps** method to retrieve its **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="78075-160">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="78075-160">MFCMAPI reference</span></span>

<span data-ttu-id="78075-161">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="78075-161">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="78075-162">**文件**</span><span class="sxs-lookup"><span data-stu-id="78075-162">**File**</span></span>|<span data-ttu-id="78075-163">**函数**</span><span class="sxs-lookup"><span data-stu-id="78075-163">**Function**</span></span>|<span data-ttu-id="78075-164">**备注**</span><span class="sxs-lookup"><span data-stu-id="78075-164">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78075-165">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="78075-165">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="78075-166">CMsgStoreDlg：：OnCreateSubFolder</span><span class="sxs-lookup"><span data-stu-id="78075-166">CMsgStoreDlg::OnCreateSubFolder</span></span>  <br/> |<span data-ttu-id="78075-167">MFCMAPI 使用 **CMsgStoreDlg：：OnCreateSubFolder** 方法在 MFCMAPI 中创建新文件夹。</span><span class="sxs-lookup"><span data-stu-id="78075-167">MFCMAPI uses the **CMsgStoreDlg::OnCreateSubFolder** method to create new folders in MFCMAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="78075-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78075-168">See also</span></span>



[<span data-ttu-id="78075-169">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="78075-169">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="78075-170">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="78075-170">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="78075-171">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="78075-171">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

