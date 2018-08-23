---
title: IMAPIPropGetPropList
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.GetPropList
api_type:
- COM
ms.assetid: 0069c223-32bb-4286-b763-39fd45dc263b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5417853dbb1fa87d2beead2f73ca57329e17b044
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571120"
---
# <a name="imapipropgetproplist"></a><span data-ttu-id="a4eee-103">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="a4eee-103">IMAPIProp::GetPropList</span></span>

  
  
<span data-ttu-id="a4eee-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a4eee-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a4eee-105">返回所有属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="a4eee-105">Returns property tags for all properties.</span></span> 
  
```cpp
HRESULT GetPropList(
  ULONG ulFlags,
  LPSPropTagArray FAR * lppPropTagArray
);
```

## <a name="parameters"></a><span data-ttu-id="a4eee-106">参数</span><span class="sxs-lookup"><span data-stu-id="a4eee-106">Parameters</span></span>

 <span data-ttu-id="a4eee-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a4eee-107">_ulFlags_</span></span>
  
> <span data-ttu-id="a4eee-108">[in]位掩码的标志的控件中返回的属性标记的字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="a4eee-108">[in] A bitmask of flags that controls the format for the strings in the returned property tags.</span></span> <span data-ttu-id="a4eee-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="a4eee-109">The following flag can be set:</span></span>
    
<span data-ttu-id="a4eee-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a4eee-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a4eee-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a4eee-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="a4eee-112">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a4eee-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="a4eee-113">_lppPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="a4eee-113">_lppPropTagArray_</span></span>
  
> <span data-ttu-id="a4eee-114">[输出]指向包含对象的属性的所有标记属性标记数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a4eee-114">[out] A pointer to a pointer to the property tag array that contains tags for all of the object's properties.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a4eee-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a4eee-115">Return value</span></span>

<span data-ttu-id="a4eee-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4eee-116">S_OK</span></span> 
  
> <span data-ttu-id="a4eee-117">成功返回所有属性标记。</span><span class="sxs-lookup"><span data-stu-id="a4eee-117">All of the property tags were returned successfully.</span></span>
    
<span data-ttu-id="a4eee-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="a4eee-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="a4eee-119">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="a4eee-119">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a4eee-120">注解</span><span class="sxs-lookup"><span data-stu-id="a4eee-120">Remarks</span></span>

<span data-ttu-id="a4eee-121">**IMAPIProp::GetPropList**方法检索当前对象支持的每个属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="a4eee-121">The **IMAPIProp::GetPropList** method retrieves the property tag for each property currently supported by an object.</span></span> <span data-ttu-id="a4eee-122">如果对象当前不支持任何属性， **GetPropList**将返回与设置为 0 的**cValues**成员属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="a4eee-122">If the object does not currently support any properties, **GetPropList** returns a property tag array with the **cValues** member set to 0.</span></span> 
  
<span data-ttu-id="a4eee-123">返回由**GetPropList**属性的范围而有所不同商的。</span><span class="sxs-lookup"><span data-stu-id="a4eee-123">The scope of properties returned by **GetPropList** varies from provider to provider.</span></span> <span data-ttu-id="a4eee-124">某些服务提供商不包括呼叫者不具有访问这些属性。</span><span class="sxs-lookup"><span data-stu-id="a4eee-124">Some service providers exclude those properties for which the caller does not have access.</span></span> <span data-ttu-id="a4eee-125">所有提供程序返回类型**PT_OBJECT**的属性。</span><span class="sxs-lookup"><span data-stu-id="a4eee-125">All providers return properties of type **PT_OBJECT**.</span></span>
  
<span data-ttu-id="a4eee-126">如果对象不支持 Unicode， **GetPropList**将返回 MAPI_E_BAD_CHARWIDTH，即使没有为对象定义的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="a4eee-126">If the object does not support Unicode, **GetPropList** returns MAPI_E_BAD_CHARWIDTH, even if there are no string properties defined for the object.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a4eee-127">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="a4eee-127">Notes to implementers</span></span>

<span data-ttu-id="a4eee-128">远程传输提供程序就完全等同于指定此处实现**GetPropList** 。</span><span class="sxs-lookup"><span data-stu-id="a4eee-128">Remote transport providers implement **GetPropList** exactly as specified here.</span></span> <span data-ttu-id="a4eee-129">没有任何特殊的问题。</span><span class="sxs-lookup"><span data-stu-id="a4eee-129">There are no special concerns.</span></span> <span data-ttu-id="a4eee-130">您的实现应，当然，返回相同的属性所支持的[IMAPIProp::GetProps](imapiprop-getprops.md)方法的列表。</span><span class="sxs-lookup"><span data-stu-id="a4eee-130">Your implementation should, of course, return the same list of properties as supported by the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="a4eee-131">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a4eee-131">Notes to callers</span></span>

<span data-ttu-id="a4eee-132">调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放所指的_lppPropTagArray_属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="a4eee-132">Call the [MAPIFreeBuffer](mapifreebuffer.md) function to free the property tag array pointed to by  _lppPropTagArray_.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a4eee-133">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="a4eee-133">MFCMAPI reference</span></span>

<span data-ttu-id="a4eee-134">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a4eee-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a4eee-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="a4eee-135">**File**</span></span>|<span data-ttu-id="a4eee-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="a4eee-136">**Function**</span></span>|<span data-ttu-id="a4eee-137">**Comment**</span><span class="sxs-lookup"><span data-stu-id="a4eee-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4eee-138">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="a4eee-138">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="a4eee-139">GetPropsNULL</span><span class="sxs-lookup"><span data-stu-id="a4eee-139">GetPropsNULL</span></span>  <br/> |<span data-ttu-id="a4eee-140">MFCMAPI 使用**IMAPIProp::GetPropList**方法来获取要传递给**GetProps**属性列表。</span><span class="sxs-lookup"><span data-stu-id="a4eee-140">MFCMAPI uses the **IMAPIProp::GetPropList** method to get a property list to pass to **GetProps**.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a4eee-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4eee-141">See also</span></span>



[<span data-ttu-id="a4eee-142">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="a4eee-142">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="a4eee-143">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="a4eee-143">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="a4eee-144">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a4eee-144">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="a4eee-145">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a4eee-145">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

