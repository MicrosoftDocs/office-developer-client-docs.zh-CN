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
# <a name="imapifoldercreatefolder"></a><span data-ttu-id="1fe2b-103">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="1fe2b-103">IMAPIFolder::CreateFolder</span></span>

  
  
<span data-ttu-id="1fe2b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1fe2b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1fe2b-105">创建一个新的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-105">Creates a new subfolder.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="1fe2b-106">参数</span><span class="sxs-lookup"><span data-stu-id="1fe2b-106">Parameters</span></span>

 <span data-ttu-id="1fe2b-107">_ulFolderType_</span><span class="sxs-lookup"><span data-stu-id="1fe2b-107">_ulFolderType_</span></span>
  
> <span data-ttu-id="1fe2b-108">实时要创建的文件夹的类型。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-108">[in] The type of folder to create.</span></span> <span data-ttu-id="1fe2b-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="1fe2b-109">The following flags can be set:</span></span>
    
<span data-ttu-id="1fe2b-110">FOLDER_GENERIC</span><span class="sxs-lookup"><span data-stu-id="1fe2b-110">FOLDER_GENERIC</span></span> 
  
> <span data-ttu-id="1fe2b-111">应创建一个常规文件夹。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-111">A generic folder should be created.</span></span>
    
<span data-ttu-id="1fe2b-112">FOLDER_SEARCH</span><span class="sxs-lookup"><span data-stu-id="1fe2b-112">FOLDER_SEARCH</span></span> 
  
> <span data-ttu-id="1fe2b-113">应创建搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-113">A search-results folder should be created.</span></span>
    
 <span data-ttu-id="1fe2b-114">_lpszFolderName_</span><span class="sxs-lookup"><span data-stu-id="1fe2b-114">_lpszFolderName_</span></span>
  
> <span data-ttu-id="1fe2b-115">实时指向包含新文件夹名称的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-115">[in] A pointer to a string that contains the name for the new folder.</span></span> <span data-ttu-id="1fe2b-116">此名称是新文件夹的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的基础。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-116">This name is the basis for the new folder's **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="1fe2b-117">_lpszFolderComment_</span><span class="sxs-lookup"><span data-stu-id="1fe2b-117">_lpszFolderComment_</span></span>
  
> <span data-ttu-id="1fe2b-118">实时指向包含与新文件夹相关联的注释的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-118">[in] A pointer to a string that contains a comment associated with the new folder.</span></span> <span data-ttu-id="1fe2b-119">此字符串将成为新文件夹的**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-119">This string becomes the value of the new folder's **PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md)) property.</span></span> <span data-ttu-id="1fe2b-120">如果传递了 NULL, 则文件夹没有初始注释。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-120">If NULL is passed, the folder has no initial comment.</span></span>
    
 <span data-ttu-id="1fe2b-121">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="1fe2b-121">_lpInterface_</span></span>
  
> <span data-ttu-id="1fe2b-122">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问新文件夹的接口。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-122">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the new folder.</span></span> <span data-ttu-id="1fe2b-123">传递 NULL 将导致邮件存储提供程序返回标准文件夹接口[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-123">Passing NULL causes the message store provider to return the standard folder interface, [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md).</span></span> <span data-ttu-id="1fe2b-124">客户端必须传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-124">Clients must pass NULL.</span></span> <span data-ttu-id="1fe2b-125">其他调用方可以将_lpInterface_参数设置为 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 或 IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-125">Other callers can set the  _lpInterface_ parameter to IID_IUnknown, IID_IMAPIProp, IID_IMAPIContainer, or IID_IMAPIFolder.</span></span> 
    
 <span data-ttu-id="1fe2b-126">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1fe2b-126">_ulFlags_</span></span>
  
> <span data-ttu-id="1fe2b-127">实时用于控制文件夹创建方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-127">[in] A bitmask of flags that controls how the folder is created.</span></span> <span data-ttu-id="1fe2b-128">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="1fe2b-128">The following flags can be set:</span></span>
    
<span data-ttu-id="1fe2b-129">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="1fe2b-129">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="1fe2b-130">允许**CreateFolder**成功返回, 可能在新文件夹完全提供给呼叫客户端之前。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-130">Allows **CreateFolder** to return successfully, possibly before the new folder is fully available to the calling client.</span></span> <span data-ttu-id="1fe2b-131">如果新文件夹不可用, 则对其进行后续调用可能会导致出错。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-131">If the new folder is not available, making a subsequent call to it can cause an error.</span></span> 
    
<span data-ttu-id="1fe2b-132">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1fe2b-132">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="1fe2b-133">该文件夹的名称采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-133">The name of the folder is in Unicode format.</span></span> <span data-ttu-id="1fe2b-134">如果未设置 MAPI_UNICODE 标志, 则该文件夹名称为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-134">If the MAPI_UNICODE flag is not set, the folder name is in ANSI format.</span></span>
    
<span data-ttu-id="1fe2b-135">OPEN_IF_EXISTS</span><span class="sxs-lookup"><span data-stu-id="1fe2b-135">OPEN_IF_EXISTS</span></span> 
  
> <span data-ttu-id="1fe2b-136">通过打开具有该名称的现有文件夹, 允许该方法成功, 即使在_lpszFolderName_参数中指定的文件夹已经存在。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-136">Allows the method to succeed even if the folder named in the  _lpszFolderName_ parameter already exists by opening the existing folder that has that name.</span></span> <span data-ttu-id="1fe2b-137">请注意, 如果存在多个具有所提供名称的现有文件夹, 则允许同级文件夹具有相同名称的邮件存储提供程序可能无法打开现有文件夹。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-137">Note that message store providers that allow sibling folders to have the same name might not open an existing folder if more than one exists with the supplied name.</span></span> 
    
 <span data-ttu-id="1fe2b-138">_lppFolder_</span><span class="sxs-lookup"><span data-stu-id="1fe2b-138">_lppFolder_</span></span>
  
> <span data-ttu-id="1fe2b-139">排除指向新创建的文件夹的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-139">[out] A pointer to a pointer to the newly created folder.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1fe2b-140">返回值</span><span class="sxs-lookup"><span data-stu-id="1fe2b-140">Return value</span></span>

<span data-ttu-id="1fe2b-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="1fe2b-141">S_OK</span></span> 
  
> <span data-ttu-id="1fe2b-142">如果设置了 OPEN_IF_EXISTS 标志, 则已成功创建或打开新文件夹。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-142">The new folder has been successfully created or opened, if the OPEN_IF_EXISTS flag is set.</span></span>
    
<span data-ttu-id="1fe2b-143">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="1fe2b-143">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="1fe2b-144">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-144">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="1fe2b-145">MAPI_E_COLLISION</span><span class="sxs-lookup"><span data-stu-id="1fe2b-145">MAPI_E_COLLISION</span></span> 
  
> <span data-ttu-id="1fe2b-146">具有_lpszFolderName_参数中给定名称的文件夹已存在。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-146">A folder that has the name given in the  _lpszFolderName_ parameter already exists.</span></span> <span data-ttu-id="1fe2b-147">文件夹名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-147">Folder names must be unique.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1fe2b-148">说明</span><span class="sxs-lookup"><span data-stu-id="1fe2b-148">Remarks</span></span>

<span data-ttu-id="1fe2b-149">**IMAPIFolder:: CreateFolder**方法在当前文件夹中创建一个子文件夹, 并将条目标识符分配给新文件夹。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-149">The **IMAPIFolder::CreateFolder** method creates a subfolder in the current folder and assigns an entry identifier to the new folder.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1fe2b-150">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1fe2b-150">Notes to callers</span></span>

<span data-ttu-id="1fe2b-151">当**CreateFolder**返回时, 请注意新文件夹的条目标识符可能不可用。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-151">When **CreateFolder** returns, be aware that the entry identifier for the new folder might not be available.</span></span> <span data-ttu-id="1fe2b-152">在您调用了新文件夹的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以永久保存它之前, 某些邮件存储提供程序不会使条目标识符可用。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-152">Some message store providers do not make entry identifiers available until after you have called the new folder's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to permanently save it.</span></span> <span data-ttu-id="1fe2b-153">如果您已设置 MAPI_DEFERRED_ERRORS 标志, 则更是如此。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-153">This is especially true if you have set the MAPI_DEFERRED_ERRORS flag.</span></span> 
  
<span data-ttu-id="1fe2b-154">请注意, 某些邮件存储提供程序始终将_lppFolder_参数指向文件夹的标准接口, 而不考虑您传递给_lpInterface_参数的值。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-154">Be aware that some message store providers always point the  _lppFolder_ parameter to the folder's standard interface, regardless of the value that you pass in for the  _lpInterface_ parameter.</span></span> <span data-ttu-id="1fe2b-155">由于返回的接口指针可能不是您所需的类型, 因此请调用新文件夹的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-155">Because the interface pointer that is returned might not be of the type that you expect, call the new folder's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) property.</span></span> <span data-ttu-id="1fe2b-156">如有必要, 请在进行其他调用之前, 将指针转换为更合适的类型。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-156">If necessary, cast the pointer to a more appropriate type before you make other calls.</span></span>
  
<span data-ttu-id="1fe2b-157">大多数邮件存储提供程序要求新文件夹的名称相对于其同辈文件夹的名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-157">Most message store providers require the name of the new folder to be unique with respect to the names of its sibling folders.</span></span> <span data-ttu-id="1fe2b-158">能够处理 MAPI_E_COLLISION 错误值, 如果未遵循此规则, 将返回此值。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-158">Be able to handle the MAPI_E_COLLISION error value, which is returned if this rule is not followed.</span></span> 
  
<span data-ttu-id="1fe2b-159">若要确定新创建的文件夹的条目标识符, 请调用新文件夹的**IMAPIProp:: GetProps**方法以检索其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-159">To determine the entry identifier of the newly created folder, call the new folder's **IMAPIProp::GetProps** method to retrieve its **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1fe2b-160">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="1fe2b-160">MFCMAPI reference</span></span>

<span data-ttu-id="1fe2b-161">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-161">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1fe2b-162">**文件**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-162">**File**</span></span>|<span data-ttu-id="1fe2b-163">**函数**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-163">**Function**</span></span>|<span data-ttu-id="1fe2b-164">**备注**</span><span class="sxs-lookup"><span data-stu-id="1fe2b-164">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1fe2b-165">MsgStoreDlg</span><span class="sxs-lookup"><span data-stu-id="1fe2b-165">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="1fe2b-166">CMsgStoreDlg:: OnCreateSubFolder</span><span class="sxs-lookup"><span data-stu-id="1fe2b-166">CMsgStoreDlg::OnCreateSubFolder</span></span>  <br/> |<span data-ttu-id="1fe2b-167">MFCMAPI 使用**CMsgStoreDlg:: OnCreateSubFolder**方法在 MFCMAPI 中创建新文件夹。</span><span class="sxs-lookup"><span data-stu-id="1fe2b-167">MFCMAPI uses the **CMsgStoreDlg::OnCreateSubFolder** method to create new folders in MFCMAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1fe2b-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fe2b-168">See also</span></span>



[<span data-ttu-id="1fe2b-169">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="1fe2b-169">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="1fe2b-170">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="1fe2b-170">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="1fe2b-171">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1fe2b-171">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

