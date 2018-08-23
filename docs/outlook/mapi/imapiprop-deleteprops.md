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
ms.openlocfilehash: a0d86b9b0342beea6b33db0219cb5889d2e63f03
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592071"
---
# <a name="imapipropdeleteprops"></a><span data-ttu-id="85968-103">IMAPIProp::DeleteProps</span><span class="sxs-lookup"><span data-stu-id="85968-103">IMAPIProp::DeleteProps</span></span>

  
  
<span data-ttu-id="85968-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="85968-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="85968-105">从对象中删除一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="85968-105">Deletes one or more properties from an object.</span></span> 
  
```cpp
HRESULT DeleteProps(
  LPSPropTagArray lpPropTagArray,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a><span data-ttu-id="85968-106">参数</span><span class="sxs-lookup"><span data-stu-id="85968-106">Parameters</span></span>

 <span data-ttu-id="85968-107">_lpPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="85968-107">_lpPropTagArray_</span></span>
  
> <span data-ttu-id="85968-108">[in]一个指向数组属性标记，指示要删除的属性。</span><span class="sxs-lookup"><span data-stu-id="85968-108">[in] A pointer to an array of property tags that indicate the properties to delete.</span></span> <span data-ttu-id="85968-109">指向_lpPropTagArray_ [SPropTagArray](sproptagarray.md)结构的**cValues**成员必须不为零，和_lpPropTagArray_参数本身不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="85968-109">The **cValues** member of the [SPropTagArray](sproptagarray.md) structure pointed to by  _lpPropTagArray_ must not be zero, and the  _lpPropTagArray_ parameter itself must not be NULL.</span></span> 
    
 <span data-ttu-id="85968-110">_lppProblems_</span><span class="sxs-lookup"><span data-stu-id="85968-110">_lppProblems_</span></span>
  
> <span data-ttu-id="85968-111">[传入、 传出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则，为 NULL，指示存在错误信息不需要。</span><span class="sxs-lookup"><span data-stu-id="85968-111">[in, out] On input, a pointer to a pointer to an [SPropProblemArray](spropproblemarray.md) structure; otherwise, NULL, which indicates that there is no need for error information.</span></span> <span data-ttu-id="85968-112">如果_lppProblems_上输入, 的有效指针**DeleteProps**将返回错误的详细的信息中删除一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="85968-112">If  _lppProblems_ is a valid pointer on input, **DeleteProps** returns detailed information about errors in deleting one or more properties.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="85968-113">返回值</span><span class="sxs-lookup"><span data-stu-id="85968-113">Return value</span></span>

<span data-ttu-id="85968-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="85968-114">S_OK</span></span> 
  
> <span data-ttu-id="85968-115">已成功删除属性。</span><span class="sxs-lookup"><span data-stu-id="85968-115">Properties were successfully deleted.</span></span>
    
<span data-ttu-id="85968-116">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="85968-116">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="85968-117">呼叫者具有权限不足，无法删除属性。</span><span class="sxs-lookup"><span data-stu-id="85968-117">The caller has insufficient permissions to delete properties.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="85968-118">注解</span><span class="sxs-lookup"><span data-stu-id="85968-118">Remarks</span></span>

<span data-ttu-id="85968-119">**IMAPIProp::DeleteProps**方法删除当前对象的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="85968-119">The **IMAPIProp::DeleteProps** method removes one or more properties from the current object.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="85968-120">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="85968-120">Notes to implementers</span></span>

<span data-ttu-id="85968-121">不需要允许从所有对象中删除的属性。</span><span class="sxs-lookup"><span data-stu-id="85968-121">You do not have to allow properties to be deleted from all objects.</span></span> <span data-ttu-id="85968-122">如果对象不是可修改， **DeleteProps**方法返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="85968-122">If the object is not modifiable, return MAPI_E_NO_ACCESS from the **DeleteProps** method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="85968-123">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="85968-123">Notes to callers</span></span>

<span data-ttu-id="85968-124">您不必设置_lpPropTagArray_参数指向该属性标记数组中的每个属性标记的属性类型。</span><span class="sxs-lookup"><span data-stu-id="85968-124">You do not have to set the property type for each property tag in the property tag array pointed to by the  _lpPropTagArray_ parameter.</span></span> <span data-ttu-id="85968-125">属性类型将被忽略;使用仅属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="85968-125">Property types are ignored; only the property identifiers are used.</span></span> 
  
<span data-ttu-id="85968-126">请注意，某些对象不允许修改，这些对象从**DeleteProps**方法返回 MAPI_E_NO_ACCESS。</span><span class="sxs-lookup"><span data-stu-id="85968-126">Be aware that some objects do not allow modification and that these objects return MAPI_E_NO_ACCESS from the **DeleteProps** method.</span></span> <span data-ttu-id="85968-127">允许其他对象的某些属性被删除，但不是其他人。</span><span class="sxs-lookup"><span data-stu-id="85968-127">Other objects allow some properties to be deleted, but not others.</span></span> <span data-ttu-id="85968-128">当没有问题删除只将某些属性时， **DeleteProps** ，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="85968-128">When there is a problem deleting only some of the properties, **DeleteProps** returns S_OK.</span></span> <span data-ttu-id="85968-129">如果您具有_lppProblems_参数中传递有效的指针， **DeleteProps**将设置为**SPropProblemArray**结构，其中包含与每个属性的问题的详细的信息的指针。</span><span class="sxs-lookup"><span data-stu-id="85968-129">If you have passed a valid pointer in the  _lppProblems_ parameter, **DeleteProps** will set the pointer to an **SPropProblemArray** structure that contains detailed information about the problems with each property.</span></span> <span data-ttu-id="85968-130">例如，如果您要删除的所有邮件的属性，并且有一个或多个附件的问题， **SPropProblemArray**结构将包含的条目的**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="85968-130">For example, if you are deleting all of the properties of a message and there is a problem with one or more of its attachments, the **SPropProblemArray** structure will contain an entry for the **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="85968-131">指向_lppProblems_结构才有效**DeleteProps** ，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="85968-131">The structure pointed to by  _lppProblems_ is only valid if **DeleteProps** returns S_OK.</span></span> <span data-ttu-id="85968-132">如果**DeleteProps**将返回错误，不尝试使用**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="85968-132">If **DeleteProps** returns an error, do not attempt to use the **SPropProblemArray** structure.</span></span> <span data-ttu-id="85968-133">相反，调用对象的[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法以获取有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="85968-133">Instead, call the object's [IMAPIProp::GetLastError](imapiprop-getlasterror.md) method to obtain more information about the error.</span></span> 
  
<span data-ttu-id="85968-134">通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。</span><span class="sxs-lookup"><span data-stu-id="85968-134">Free the returned **SPropProblemArray** structure by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="85968-135">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="85968-135">MFCMAPI reference</span></span>

<span data-ttu-id="85968-136">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="85968-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="85968-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="85968-137">**File**</span></span>|<span data-ttu-id="85968-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="85968-138">**Function**</span></span>|<span data-ttu-id="85968-139">**Comment**</span><span class="sxs-lookup"><span data-stu-id="85968-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85968-140">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="85968-140">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="85968-141">DeleteProperty</span><span class="sxs-lookup"><span data-stu-id="85968-141">DeleteProperty</span></span>  <br/> |<span data-ttu-id="85968-142">MFCMAPI 使用**IMAPIProp::DeleteProps**方法从对象中删除属性。</span><span class="sxs-lookup"><span data-stu-id="85968-142">MFCMAPI uses the **IMAPIProp::DeleteProps** method to delete a property from an object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="85968-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85968-143">See also</span></span>



[<span data-ttu-id="85968-144">IMAPIProp::GetLastError</span><span class="sxs-lookup"><span data-stu-id="85968-144">IMAPIProp::GetLastError</span></span>](imapiprop-getlasterror.md)
  
[<span data-ttu-id="85968-145">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="85968-145">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="85968-146">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="85968-146">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="85968-147">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="85968-147">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="85968-148">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="85968-148">SPropProblemArray</span></span>](spropproblemarray.md)
  
[<span data-ttu-id="85968-149">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="85968-149">SPropTagArray</span></span>](sproptagarray.md)
  
[<span data-ttu-id="85968-150">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="85968-150">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="85968-151">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="85968-151">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

