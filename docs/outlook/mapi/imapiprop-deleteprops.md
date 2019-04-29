---
title: IMAPIPropDeleteProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.DeleteProps
api_type:
- COM
ms.assetid: 5cc642de-21f0-4826-bf21-aac4bcfc1328
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5bfef87baa2dffa4605f9a7afa3833024f514430
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409235"
---
# <a name="imapipropdeleteprops"></a><span data-ttu-id="3728e-103">IMAPIProp::DeleteProps</span><span class="sxs-lookup"><span data-stu-id="3728e-103">IMAPIProp::DeleteProps</span></span>

  
  
<span data-ttu-id="3728e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3728e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3728e-105">从对象中删除一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="3728e-105">Deletes one or more properties from an object.</span></span> 
  
```cpp
HRESULT DeleteProps(
  LPSPropTagArray lpPropTagArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="3728e-106">参数</span><span class="sxs-lookup"><span data-stu-id="3728e-106">Parameters</span></span>

 <span data-ttu-id="3728e-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="3728e-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="3728e-108">实时指向指明要删除的属性的属性标记数组的指针。</span><span class="sxs-lookup"><span data-stu-id="3728e-108">[in] A pointer to an array of property tags that indicate the properties to delete.</span></span> <span data-ttu-id="3728e-109">由_lpPropTagArray_指向的[SPropTagArray](sproptagarray.md)结构的**cValues**成员不得为零, 并且_lpPropTagArray_参数本身不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3728e-109">The **cValues** member of the [SPropTagArray](sproptagarray.md) structure pointed to by  _lpPropTagArray_ must not be zero, and the  _lpPropTagArray_ parameter itself must not be NULL.</span></span> 
    
 <span data-ttu-id="3728e-110">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="3728e-110">_lppProblems_</span></span>
  
> <span data-ttu-id="3728e-111">[in, out]在输入时, 指向指向[SPropProblemArray](spropproblemarray.md)结构的指针的指针;否则为 NULL, 表示无需提供错误信息。</span><span class="sxs-lookup"><span data-stu-id="3728e-111">[in, out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, NULL, which indicates that there is no need for error information.</span></span> <span data-ttu-id="3728e-112">如果_lppProblems_是有效的输入指针, **DeleteProps**将返回有关删除一个或多个属性中的错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3728e-112">If  _lppProblems_ is a valid pointer on input, **DeleteProps** returns detailed information about errors in deleting one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3728e-113">返回值</span><span class="sxs-lookup"><span data-stu-id="3728e-113">Return value</span></span>

<span data-ttu-id="3728e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3728e-114">S_OK</span></span> 
  
> <span data-ttu-id="3728e-115">已成功删除属性。</span><span class="sxs-lookup"><span data-stu-id="3728e-115">Properties were successfully deleted.</span></span>
    
<span data-ttu-id="3728e-116">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="3728e-116">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="3728e-117">调用方权限不足, 无法删除属性。</span><span class="sxs-lookup"><span data-stu-id="3728e-117">The caller has insufficient permissions to delete properties.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3728e-118">说明</span><span class="sxs-lookup"><span data-stu-id="3728e-118">Remarks</span></span>

<span data-ttu-id="3728e-119">**IMAPIProp::D eleteprops**方法从当前对象中删除一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="3728e-119">The **IMAPIProp::DeleteProps** method removes one or more properties from the current object.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="3728e-120">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="3728e-120">Notes to implementers</span></span>

<span data-ttu-id="3728e-121">您无需允许从所有对象中删除属性。</span><span class="sxs-lookup"><span data-stu-id="3728e-121">You do not have to allow properties to be deleted from all objects.</span></span> <span data-ttu-id="3728e-122">如果对象是不可修改的, 请从**DeleteProps**方法返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="3728e-122">If the object is not modifiable, return MAPI_E_NO_ACCESS from the **DeleteProps** method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3728e-123">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3728e-123">Notes to callers</span></span>

<span data-ttu-id="3728e-124">您不必为由_lpPropTagArray_参数指向的属性标记数组中的每个属性标记设置属性类型。</span><span class="sxs-lookup"><span data-stu-id="3728e-124">You do not have to set the property type for each property tag in the property tag array pointed to by the  _lpPropTagArray_ parameter.</span></span> <span data-ttu-id="3728e-125">忽略属性类型;仅使用属性标识符。</span><span class="sxs-lookup"><span data-stu-id="3728e-125">Property types are ignored; only the property identifiers are used.</span></span> 
  
<span data-ttu-id="3728e-126">请注意, 某些对象不允许进行修改, 并且这些对象从**DeleteProps**方法返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="3728e-126">Be aware that some objects do not allow modification and that these objects return MAPI_E_NO_ACCESS from the **DeleteProps** method.</span></span> <span data-ttu-id="3728e-127">其他对象允许删除某些属性, 但不允许删除其他属性。</span><span class="sxs-lookup"><span data-stu-id="3728e-127">Other objects allow some properties to be deleted, but not others.</span></span> <span data-ttu-id="3728e-128">如果删除某些属性时出现问题, **DeleteProps**将返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="3728e-128">When there is a problem deleting only some of the properties, **DeleteProps** returns S_OK.</span></span> <span data-ttu-id="3728e-129">如果您在_lppProblems_参数中传递了一个有效的指针, 则**DeleteProps**会将指针设置为包含有关每个属性的问题的详细信息的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="3728e-129">If you have passed a valid pointer in the  _lppProblems_ parameter, **DeleteProps** will set the pointer to an **SPropProblemArray** structure that contains detailed information about the problems with each property.</span></span> <span data-ttu-id="3728e-130">例如, 如果您要删除邮件的所有属性, 并且其中一个或多个附件存在问题, 则**SPropProblemArray**结构将包含**PR_MESSAGE_ATTACHMENTS**的一个条目 ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="3728e-130">For example, if you are deleting all of the properties of a message and there is a problem with one or more of its attachments, the **SPropProblemArray** structure will contain an entry for the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="3728e-131">_lppProblems_所指向的结构仅当**DeleteProps**返回 S_OK 时才有效。</span><span class="sxs-lookup"><span data-stu-id="3728e-131">The structure pointed to by  _lppProblems_ is only valid if **DeleteProps** returns S_OK.</span></span> <span data-ttu-id="3728e-132">如果**DeleteProps**返回错误, 则不要尝试使用**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="3728e-132">If **DeleteProps** returns an error, do not attempt to use the **SPropProblemArray** structure.</span></span> <span data-ttu-id="3728e-133">相反, 请调用对象的[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法以获取有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3728e-133">Instead, call the object's [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method to obtain more information about the error.</span></span> 
  
<span data-ttu-id="3728e-134">通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="3728e-134">Free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3728e-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="3728e-135">MFCMAPI reference</span></span>

<span data-ttu-id="3728e-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3728e-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3728e-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="3728e-137">**File**</span></span>|<span data-ttu-id="3728e-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="3728e-138">**Function**</span></span>|<span data-ttu-id="3728e-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="3728e-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3728e-140">MAPIFunctions</span><span class="sxs-lookup"><span data-stu-id="3728e-140">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="3728e-141">DeleteProperty</span><span class="sxs-lookup"><span data-stu-id="3728e-141">DeleteProperty</span></span>  <br/> |<span data-ttu-id="3728e-142">MFCMAPI 使用**IMAPIProp::D eleteprops**方法从对象中删除属性。</span><span class="sxs-lookup"><span data-stu-id="3728e-142">MFCMAPI uses the **IMAPIProp::DeleteProps** method to delete a property from an object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3728e-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3728e-143">See also</span></span>



[<span data-ttu-id="3728e-144">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="3728e-144">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="3728e-145">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="3728e-145">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="3728e-146">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="3728e-146">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="3728e-147">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="3728e-147">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="3728e-148">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="3728e-148">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="3728e-149">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="3728e-149">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="3728e-150">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3728e-150">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="3728e-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="3728e-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

