---
title: IMAPIFolderEmptyFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.EmptyFolder
api_type:
- COM
ms.assetid: 4cfcb498-9182-4906-bd6f-d9bc387bc88b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4ca828c3e03cbff886230f2af63485f7b15e8b35
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416781"
---
# <a name="imapifolderemptyfolder"></a><span data-ttu-id="5544e-103">IMAPIFolder::EmptyFolder</span><span class="sxs-lookup"><span data-stu-id="5544e-103">IMAPIFolder::EmptyFolder</span></span>

  
  
<span data-ttu-id="5544e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5544e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5544e-105">从文件夹中删除所有邮件和子文件夹，而不删除文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="5544e-105">Deletes all messages and subfolders from a folder without deleting the folder itself.</span></span>
  
```cpp
HRESULT EmptyFolder(
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="5544e-106">参数</span><span class="sxs-lookup"><span data-stu-id="5544e-106">Parameters</span></span>

 <span data-ttu-id="5544e-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="5544e-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="5544e-108">[in]进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="5544e-108">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="5544e-109">除非  _在 ulFlags_ 参数中设置了 FOLDER_DIALOG 标志，否则将忽略  _ulUIParam_ 参数。</span><span class="sxs-lookup"><span data-stu-id="5544e-109">The  _ulUIParam_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="5544e-110">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="5544e-110">_lpProgress_</span></span>
  
> <span data-ttu-id="5544e-111">[in]指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="5544e-111">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="5544e-112">如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="5544e-112">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="5544e-113">除非在 _ulFlags_ 参数中设置了 FOLDER_DIALOG 标志，否则将忽略 _lpProgress_ 参数。</span><span class="sxs-lookup"><span data-stu-id="5544e-113">The  _lpProgress_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="5544e-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5544e-114">_ulFlags_</span></span>
  
> <span data-ttu-id="5544e-115">[in]控制如何清空文件夹的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5544e-115">[in] A bitmask of flags that controls how the folder is emptied.</span></span> <span data-ttu-id="5544e-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5544e-116">The following flags can be set:</span></span>
    
<span data-ttu-id="5544e-117">DEL_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="5544e-117">DEL_ASSOCIATED</span></span> 
  
> <span data-ttu-id="5544e-118">删除所有子文件夹，包括包含具有关联内容的邮件的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="5544e-118">Deletes all subfolders, including subfolders that contain messages with associated content.</span></span> <span data-ttu-id="5544e-119">the DEL_ASSOCIATED flag has meaning only for the top-level folder the call acts on.</span><span class="sxs-lookup"><span data-stu-id="5544e-119">The DEL_ASSOCIATED flag has meaning only for the top-level folder the call acts on.</span></span>
    
<span data-ttu-id="5544e-120">DELETE_HARD_DELETE</span><span class="sxs-lookup"><span data-stu-id="5544e-120">DELETE_HARD_DELETE</span></span>
  
> <span data-ttu-id="5544e-121">永久删除所有邮件，包括软删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="5544e-121">Permanently removes all messages, including soft-deleted ones.</span></span>
    
<span data-ttu-id="5544e-122">FOLDER_DIALOG</span><span class="sxs-lookup"><span data-stu-id="5544e-122">FOLDER_DIALOG</span></span> 
  
> <span data-ttu-id="5544e-123">在操作进行时显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="5544e-123">Displays a progress indicator while the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5544e-124">返回值</span><span class="sxs-lookup"><span data-stu-id="5544e-124">Return value</span></span>

<span data-ttu-id="5544e-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="5544e-125">S_OK</span></span> 
  
> <span data-ttu-id="5544e-126">已成功清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="5544e-126">The folder was successfully emptied.</span></span>
    
<span data-ttu-id="5544e-127">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="5544e-127">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="5544e-128">调用成功，但文件夹并未完全清空。</span><span class="sxs-lookup"><span data-stu-id="5544e-128">The call succeeded, but the folder was not completely emptied.</span></span> <span data-ttu-id="5544e-129">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="5544e-129">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="5544e-130">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="5544e-130">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="5544e-131">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="5544e-131">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5544e-132">备注</span><span class="sxs-lookup"><span data-stu-id="5544e-132">Remarks</span></span>

<span data-ttu-id="5544e-133">**IMAPIFolder：：EmptyFolder** 方法在不删除文件夹本身的情况下删除文件夹的所有内容。</span><span class="sxs-lookup"><span data-stu-id="5544e-133">The **IMAPIFolder::EmptyFolder** method deletes all of a folder's contents without deleting the folder itself.</span></span> 
  
<span data-ttu-id="5544e-134">在 **EmptyFolder 调用** 期间，不会删除提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="5544e-134">During an **EmptyFolder** call, submitted messages are not deleted.</span></span> 
  
<span data-ttu-id="5544e-135">文件夹的关联内容包括用于描述视图、规则、自定义表单和自定义解决方案存储的邮件，还可以包括表单定义。</span><span class="sxs-lookup"><span data-stu-id="5544e-135">A folder's associated contents include messages that are used to describe views, rules, custom forms, and custom solution storage, and can also include form definitions.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="5544e-136">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="5544e-136">Notes to implementers</span></span>

<span data-ttu-id="5544e-137">不要对文件夹中已提交的邮件调用 [IMsgStore：：AbortSubmit](imsgstore-abortsubmit.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="5544e-137">Do not call the [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) method for messages in the folder that have been submitted.</span></span> <span data-ttu-id="5544e-138">不会删除提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="5544e-138">Submitted messages are not deleted.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5544e-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5544e-139">Notes to callers</span></span>

<span data-ttu-id="5544e-140">预计以下情况下会返回这些值。</span><span class="sxs-lookup"><span data-stu-id="5544e-140">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="5544e-141">**Condition**</span><span class="sxs-lookup"><span data-stu-id="5544e-141">**Condition**</span></span>|<span data-ttu-id="5544e-142">**返回值**</span><span class="sxs-lookup"><span data-stu-id="5544e-142">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5544e-143">**EmptyFolder** 已成功清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="5544e-143">**EmptyFolder** has successfully emptied the folder.</span></span>  <br/> |<span data-ttu-id="5544e-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="5544e-144">S_OK</span></span>  <br/> |
|<span data-ttu-id="5544e-145">**EmptyFolder** 无法完全清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="5544e-145">**EmptyFolder** was unable to completely empty the folder.</span></span>  <br/> |<span data-ttu-id="5544e-146">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="5544e-146">MAPI_W_PARTIAL_COMPLETION</span></span>  <br/> |
|<span data-ttu-id="5544e-147">**EmptyFolder** 无法完成。</span><span class="sxs-lookup"><span data-stu-id="5544e-147">**EmptyFolder** was unable to complete.</span></span>  <br/> |<span data-ttu-id="5544e-148">任何错误值</span><span class="sxs-lookup"><span data-stu-id="5544e-148">Any error value</span></span>  <br/> |
   
<span data-ttu-id="5544e-149">当 **EmptyFolder** 无法完成时，不要假定未完成任何工作。</span><span class="sxs-lookup"><span data-stu-id="5544e-149">When **EmptyFolder** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="5544e-150">**EmptyFolder** 可能能够在遇到错误之前删除文件夹的一些内容。</span><span class="sxs-lookup"><span data-stu-id="5544e-150">**EmptyFolder** might have been able to delete some of the folder's contents before encountering the error.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="5544e-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="5544e-151">MFCMAPI reference</span></span>

<span data-ttu-id="5544e-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5544e-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="5544e-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="5544e-153">**File**</span></span>|<span data-ttu-id="5544e-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="5544e-154">**Function**</span></span>|<span data-ttu-id="5544e-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="5544e-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5544e-156">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="5544e-156">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="5544e-157">CMsgStoreDlg：：OnEmptyFolder</span><span class="sxs-lookup"><span data-stu-id="5544e-157">CMsgStoreDlg::OnEmptyFolder</span></span>  <br/> |<span data-ttu-id="5544e-158">MFCMAPI 使用 **IMAPIFolder：：EmptyFolder** 方法删除指定文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="5544e-158">MFCMAPI uses the **IMAPIFolder::EmptyFolder** method to delete the contents of the specified folder.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5544e-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5544e-159">See also</span></span>



[<span data-ttu-id="5544e-160">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="5544e-160">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)
  
[<span data-ttu-id="5544e-161">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="5544e-161">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="5544e-162">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="5544e-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="5544e-163">使用宏处理错误</span><span class="sxs-lookup"><span data-stu-id="5544e-163">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

