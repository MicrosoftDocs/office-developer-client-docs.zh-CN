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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280104"
---
# <a name="imapifolderemptyfolder"></a><span data-ttu-id="5c4e5-103">IMAPIFolder::EmptyFolder</span><span class="sxs-lookup"><span data-stu-id="5c4e5-103">IMAPIFolder::EmptyFolder</span></span>

  
  
<span data-ttu-id="5c4e5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5c4e5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5c4e5-105">删除文件夹中的所有邮件和子文件夹, 而不删除该文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-105">Deletes all messages and subfolders from a folder without deleting the folder itself.</span></span>
  
```cpp
HRESULT EmptyFolder(
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="5c4e5-106">参数</span><span class="sxs-lookup"><span data-stu-id="5c4e5-106">Parameters</span></span>

 <span data-ttu-id="5c4e5-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="5c4e5-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="5c4e5-108">实时进度指示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-108">[in] A handle to the parent window of the progress indicator.</span></span> <span data-ttu-id="5c4e5-109">除非在_ulFlags_参数中设置了 FOLDER_DIALOG 标志, 否则将忽略_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-109">The  _ulUIParam_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="5c4e5-110">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="5c4e5-110">_lpProgress_</span></span>
  
> <span data-ttu-id="5c4e5-111">实时指向显示进度指示器的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-111">[in] A pointer to a progress object that displays a progress indicator.</span></span> <span data-ttu-id="5c4e5-112">如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-112">If NULL is passed in  _lpProgress_, the message store provider displays a progress indicator by using the MAPI progress object implementation.</span></span> <span data-ttu-id="5c4e5-113">除非在_ulFlags_参数中设置了 FOLDER_DIALOG 标志, 否则将忽略_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-113">The  _lpProgress_ parameter is ignored unless the FOLDER_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="5c4e5-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5c4e5-114">_ulFlags_</span></span>
  
> <span data-ttu-id="5c4e5-115">实时用于控制文件夹如何清空的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-115">[in] A bitmask of flags that controls how the folder is emptied.</span></span> <span data-ttu-id="5c4e5-116">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="5c4e5-116">The following flags can be set:</span></span>
    
<span data-ttu-id="5c4e5-117">DEL_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="5c4e5-117">DEL_ASSOCIATED</span></span> 
  
> <span data-ttu-id="5c4e5-118">删除所有子文件夹, 包括包含相关内容的邮件的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-118">Deletes all subfolders, including subfolders that contain messages with associated content.</span></span> <span data-ttu-id="5c4e5-119">DEL_ASSOCIATED 标志仅对调用操作所针对的顶级文件夹有意义。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-119">The DEL_ASSOCIATED flag has meaning only for the top-level folder the call acts on.</span></span>
    
<span data-ttu-id="5c4e5-120">DELETE_HARD_DELETE</span><span class="sxs-lookup"><span data-stu-id="5c4e5-120">DELETE_HARD_DELETE</span></span>
  
> <span data-ttu-id="5c4e5-121">永久删除所有邮件, 包括软删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-121">Permanently removes all messages, including soft-deleted ones.</span></span>
    
<span data-ttu-id="5c4e5-122">FOLDER_DIALOG</span><span class="sxs-lookup"><span data-stu-id="5c4e5-122">FOLDER_DIALOG</span></span> 
  
> <span data-ttu-id="5c4e5-123">在操作继续时显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-123">Displays a progress indicator while the operation proceeds.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5c4e5-124">返回值</span><span class="sxs-lookup"><span data-stu-id="5c4e5-124">Return value</span></span>

<span data-ttu-id="5c4e5-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c4e5-125">S_OK</span></span> 
  
> <span data-ttu-id="5c4e5-126">已成功清空该文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-126">The folder was successfully emptied.</span></span>
    
<span data-ttu-id="5c4e5-127">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="5c4e5-127">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="5c4e5-128">调用成功, 但未完全清空该文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-128">The call succeeded, but the folder was not completely emptied.</span></span> <span data-ttu-id="5c4e5-129">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-129">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="5c4e5-130">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-130">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="5c4e5-131">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-131">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5c4e5-132">注解</span><span class="sxs-lookup"><span data-stu-id="5c4e5-132">Remarks</span></span>

<span data-ttu-id="5c4e5-133">**IMAPIFolder:: EmptyFolder**方法删除文件夹中的所有内容, 而不删除文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-133">The **IMAPIFolder::EmptyFolder** method deletes all of a folder's contents without deleting the folder itself.</span></span> 
  
<span data-ttu-id="5c4e5-134">在**EmptyFolder**呼叫过程中, 不会删除已提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-134">During an **EmptyFolder** call, submitted messages are not deleted.</span></span> 
  
<span data-ttu-id="5c4e5-135">文件夹的关联内容包括用于描述视图、规则、自定义表单和自定义解决方案存储的邮件, 还可以包括表单定义。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-135">A folder's associated contents include messages that are used to describe views, rules, custom forms, and custom solution storage, and can also include form definitions.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="5c4e5-136">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="5c4e5-136">Notes to implementers</span></span>

<span data-ttu-id="5c4e5-137">请勿为已提交的文件夹中的邮件调用[IMsgStore:: AbortSubmit](imsgstore-abortsubmit.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-137">Do not call the [IMsgStore::AbortSubmit](imsgstore-abortsubmit.md) method for messages in the folder that have been submitted.</span></span> <span data-ttu-id="5c4e5-138">已提交的邮件不会被删除。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-138">Submitted messages are not deleted.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5c4e5-139">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5c4e5-139">Notes to callers</span></span>

<span data-ttu-id="5c4e5-140">在下列情况下, 需要这些返回值。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-140">Expect these return values under the following conditions.</span></span>
  
|<span data-ttu-id="5c4e5-141">**Condition**</span><span class="sxs-lookup"><span data-stu-id="5c4e5-141">**Condition**</span></span>|<span data-ttu-id="5c4e5-142">**返回值**</span><span class="sxs-lookup"><span data-stu-id="5c4e5-142">**Return value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c4e5-143">**EmptyFolder**已成功清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-143">**EmptyFolder** has successfully emptied the folder.</span></span>  <br/> |<span data-ttu-id="5c4e5-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c4e5-144">S_OK</span></span>  <br/> |
|<span data-ttu-id="5c4e5-145">**EmptyFolder**无法完全清空文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-145">**EmptyFolder** was unable to completely empty the folder.</span></span>  <br/> |<span data-ttu-id="5c4e5-146">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="5c4e5-146">MAPI_W_PARTIAL_COMPLETION</span></span>  <br/> |
|<span data-ttu-id="5c4e5-147">**EmptyFolder**无法完成。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-147">**EmptyFolder** was unable to complete.</span></span>  <br/> |<span data-ttu-id="5c4e5-148">任何错误值</span><span class="sxs-lookup"><span data-stu-id="5c4e5-148">Any error value</span></span>  <br/> |
   
<span data-ttu-id="5c4e5-149">当**EmptyFolder**无法完成时, 请不要假定没有任何工作已完成。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-149">When **EmptyFolder** is unable to complete, do not assume that no work was done.</span></span> <span data-ttu-id="5c4e5-150">**EmptyFolder**可能已能够在遇到此错误之前删除部分文件夹内容。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-150">**EmptyFolder** might have been able to delete some of the folder's contents before encountering the error.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="5c4e5-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="5c4e5-151">MFCMAPI reference</span></span>

<span data-ttu-id="5c4e5-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="5c4e5-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="5c4e5-153">**File**</span></span>|<span data-ttu-id="5c4e5-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="5c4e5-154">**Function**</span></span>|<span data-ttu-id="5c4e5-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="5c4e5-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c4e5-156">MsgStoreDlg</span><span class="sxs-lookup"><span data-stu-id="5c4e5-156">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="5c4e5-157">CMsgStoreDlg:: OnEmptyFolder</span><span class="sxs-lookup"><span data-stu-id="5c4e5-157">CMsgStoreDlg::OnEmptyFolder</span></span>  <br/> |<span data-ttu-id="5c4e5-158">MFCMAPI 使用**IMAPIFolder:: EmptyFolder**方法删除指定文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="5c4e5-158">MFCMAPI uses the **IMAPIFolder::EmptyFolder** method to delete the contents of the specified folder.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5c4e5-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c4e5-159">See also</span></span>



[<span data-ttu-id="5c4e5-160">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="5c4e5-160">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)
  
[<span data-ttu-id="5c4e5-161">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="5c4e5-161">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)


[<span data-ttu-id="5c4e5-162">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="5c4e5-162">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="5c4e5-163">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="5c4e5-163">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

