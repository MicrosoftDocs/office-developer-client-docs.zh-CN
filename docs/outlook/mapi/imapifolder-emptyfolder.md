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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7d8653b8f0cb2196319c4a9c2b4bca89c8be5a24
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775368"
---
# <a name="imapifolderemptyfolder"></a><span data-ttu-id="6d03b-103">IMAPIFolder::EmptyFolder</span><span class="sxs-lookup"><span data-stu-id="6d03b-103">IMAPIFolder::EmptyFolder</span></span>

  
  
<span data-ttu-id="6d03b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6d03b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6d03b-105">删除所有消息和子文件夹从文件夹而不删除该文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="6d03b-105">Deletes all messages and subfolders from a folder without deleting the folder itself.</span></span>
  
```cpp
HRESULT EmptyFolder(
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="6d03b-106">参数</span><span class="sxs-lookup"><span data-stu-id="6d03b-106">Parameters</span></span>

 <span data-ttu-id="6d03b-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="6d03b-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="6d03b-108">[in]进度指示器的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="6d03b-108">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="6d03b-109">除非 FOLDER_DIALOG 标志设置_ulFlags_参数中，将忽略该_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="6d03b-109">The  _ulUIParam_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="6d03b-110">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="6d03b-110">_lpProgress_</span></span>
  
> <span data-ttu-id="6d03b-111">[in]指向显示进度指示器进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="6d03b-111">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="6d03b-112">如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="6d03b-112">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="6d03b-113">除非 FOLDER_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="6d03b-113">The  _lpProgress_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="6d03b-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="6d03b-114">_ulFlags_</span></span>
  
> <span data-ttu-id="6d03b-115">[in]位掩码的标志，控制如何清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d03b-115">[in] A bitmask of flags that controls how the folder is emptied.</span></span> <span data-ttu-id="6d03b-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="6d03b-116">The following flags can be set:</span></span>
    
<span data-ttu-id="6d03b-117">DEL_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="6d03b-117">DEL_ASSOCIATED</span></span> 
  
> <span data-ttu-id="6d03b-118">删除所有子文件夹，包括子文件夹包含具有关联的内容的消息。</span><span class="sxs-lookup"><span data-stu-id="6d03b-118">Deletes all subfolders, including subfolders that contain messages with associated content.</span></span> <span data-ttu-id="6d03b-119">只对该呼叫会影响的顶级文件夹已 DEL_ASSOCIATED 标志。</span><span class="sxs-lookup"><span data-stu-id="6d03b-119">The DEL_ASSOCIATED flag has meaning only for the top-level folder the call acts on.</span></span>
    
<span data-ttu-id="6d03b-120">DELETE_HARD_DELETE</span><span class="sxs-lookup"><span data-stu-id="6d03b-120">DELETE_HARD_DELETE</span></span>
  
> <span data-ttu-id="6d03b-121">永久删除所有邮件，包括软删除的。</span><span class="sxs-lookup"><span data-stu-id="6d03b-121">Permanently removes all messages, including soft-deleted ones.</span></span>
    
<span data-ttu-id="6d03b-122">FOLDER_DIALOG</span><span class="sxs-lookup"><span data-stu-id="6d03b-122">FOLDER_DIALOG</span></span> 
  
> <span data-ttu-id="6d03b-123">时需执行的操作，则显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="6d03b-123">Displays a progress indicator while the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6d03b-124">返回值</span><span class="sxs-lookup"><span data-stu-id="6d03b-124">Return value</span></span>

<span data-ttu-id="6d03b-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d03b-125">S_OK</span></span> 
  
> <span data-ttu-id="6d03b-126">成功清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d03b-126">The folder was successfully emptied.</span></span>
    
<span data-ttu-id="6d03b-127">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="6d03b-127">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="6d03b-128">调用成功，但不是完全清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d03b-128">The call succeeded, but the folder was not completely emptied.</span></span> <span data-ttu-id="6d03b-129">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="6d03b-129">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="6d03b-130">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="6d03b-130">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="6d03b-131">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="6d03b-131">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6d03b-132">备注</span><span class="sxs-lookup"><span data-stu-id="6d03b-132">Remarks</span></span>

<span data-ttu-id="6d03b-133">**IMAPIFolder::EmptyFolder**方法将删除所有文件夹的内容而不删除该文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="6d03b-133">The **IMAPIFolder::EmptyFolder** method deletes all of a folder's contents without deleting the folder itself.</span></span> 
  
<span data-ttu-id="6d03b-134">**EmptyFolder**呼叫期间，不会删除提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="6d03b-134">During an **EmptyFolder** call, submitted messages are not deleted.</span></span> 
  
<span data-ttu-id="6d03b-135">文件夹关联的内容包括消息，用于描述视图、 规则、 自定义表单和自定义解决方案存储区，并且还可以包含表单定义。</span><span class="sxs-lookup"><span data-stu-id="6d03b-135">A folder's associated contents include messages that are used to describe views, rules, custom forms, and custom solution storage, and can also include form definitions.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="6d03b-136">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="6d03b-136">Notes to implementers</span></span>

<span data-ttu-id="6d03b-137">不要调用[IMsgStore::AbortSubmit](imsgstore-abortsubmit.md)方法的文件夹中的已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="6d03b-137">Do not call the [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) method for messages in the folder that have been submitted.</span></span> <span data-ttu-id="6d03b-138">不会删除提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="6d03b-138">Submitted messages are not deleted.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="6d03b-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="6d03b-139">Notes to callers</span></span>

<span data-ttu-id="6d03b-140">希望在下列情况下的这些返回值。</span><span class="sxs-lookup"><span data-stu-id="6d03b-140">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="6d03b-141">**条件**</span><span class="sxs-lookup"><span data-stu-id="6d03b-141">**Condition**</span></span>|<span data-ttu-id="6d03b-142">**返回值**</span><span class="sxs-lookup"><span data-stu-id="6d03b-142">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6d03b-143">**EmptyFolder**已成功清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d03b-143">**EmptyFolder** has successfully emptied the folder.</span></span>  <br/> |<span data-ttu-id="6d03b-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d03b-144">S_OK</span></span>  <br/> |
|<span data-ttu-id="6d03b-145">**EmptyFolder**无法完全清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d03b-145">**EmptyFolder** was unable to completely empty the folder.</span></span>  <br/> |<span data-ttu-id="6d03b-146">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="6d03b-146">MAPI_W_PARTIAL_COMPLETION</span></span>  <br/> |
|<span data-ttu-id="6d03b-147">**EmptyFolder**无法完成。</span><span class="sxs-lookup"><span data-stu-id="6d03b-147">**EmptyFolder** was unable to complete.</span></span>  <br/> |<span data-ttu-id="6d03b-148">任何错误值</span><span class="sxs-lookup"><span data-stu-id="6d03b-148">Any error value</span></span>  <br/> |
   
<span data-ttu-id="6d03b-149">无法完成**EmptyFolder**时，不假定任何工作已完成。</span><span class="sxs-lookup"><span data-stu-id="6d03b-149">When **EmptyFolder** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="6d03b-150">**EmptyFolder**可能已经能够删除该文件夹的内容的一些前遇到错误。</span><span class="sxs-lookup"><span data-stu-id="6d03b-150">**EmptyFolder** might have been able to delete some of the folder's contents before encountering the error.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="6d03b-151">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="6d03b-151">MFCMAPI reference</span></span>

<span data-ttu-id="6d03b-152">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6d03b-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6d03b-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="6d03b-153">**File**</span></span>|<span data-ttu-id="6d03b-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="6d03b-154">**Function**</span></span>|<span data-ttu-id="6d03b-155">**Comment**</span><span class="sxs-lookup"><span data-stu-id="6d03b-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d03b-156">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="6d03b-156">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="6d03b-157">CMsgStoreDlg::OnEmptyFolder</span><span class="sxs-lookup"><span data-stu-id="6d03b-157">CMsgStoreDlg::OnEmptyFolder</span></span>  <br/> |<span data-ttu-id="6d03b-158">MFCMAPI 使用**IMAPIFolder::EmptyFolder**方法删除指定的文件夹中的内容。</span><span class="sxs-lookup"><span data-stu-id="6d03b-158">MFCMAPI uses the **IMAPIFolder::EmptyFolder** method to delete the contents of the specified folder.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6d03b-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d03b-159">See also</span></span>



[<span data-ttu-id="6d03b-160">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="6d03b-160">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)
  
[<span data-ttu-id="6d03b-161">IMAPIFolder: IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="6d03b-161">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="6d03b-162">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="6d03b-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="6d03b-163">用于错误处理的宏</span><span class="sxs-lookup"><span data-stu-id="6d03b-163">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

