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
ms.openlocfilehash: 0457007334ad8cc69dade3abd5859dd0d5f7af7f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775521"
---
# <a name="imapipropgetproplist"></a><span data-ttu-id="87273-103">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="87273-103">IMAPIProp::GetPropList</span></span>

  
  
<span data-ttu-id="87273-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="87273-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="87273-105">返回所有属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="87273-105">Returns property tags for all properties.</span></span> 
  
```cpp
HRESULT GetPropList(
  ULONG ulFlags,
  LPSPropTagArray FAR * lppPropTagArray
);
```

## <a name="parameters"></a><span data-ttu-id="87273-106">参数</span><span class="sxs-lookup"><span data-stu-id="87273-106">Parameters</span></span>

 <span data-ttu-id="87273-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="87273-107">_ulFlags_</span></span>
  
> <span data-ttu-id="87273-108">[in]位掩码的标志的控件中返回的属性标记的字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="87273-108">[in] A bitmask of flags that controls the format for the strings in the returned property tags.</span></span> <span data-ttu-id="87273-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="87273-109">The following flag can be set:</span></span>
    
<span data-ttu-id="87273-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="87273-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="87273-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="87273-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="87273-112">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="87273-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="87273-113">_lppPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="87273-113">_lppPropTagArray_</span></span>
  
> <span data-ttu-id="87273-114">[输出]指向包含对象的属性的所有标记属性标记数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="87273-114">[out] A pointer to a pointer to the property tag array that contains tags for all of the object's properties.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="87273-115">返回值</span><span class="sxs-lookup"><span data-stu-id="87273-115">Return value</span></span>

<span data-ttu-id="87273-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="87273-116">S_OK</span></span> 
  
> <span data-ttu-id="87273-117">成功返回所有属性标记。</span><span class="sxs-lookup"><span data-stu-id="87273-117">All of the property tags were returned successfully.</span></span>
    
<span data-ttu-id="87273-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="87273-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="87273-119">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="87273-119">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="87273-120">说明</span><span class="sxs-lookup"><span data-stu-id="87273-120">Remarks</span></span>

<span data-ttu-id="87273-121">**IMAPIProp::GetPropList**方法检索当前对象支持的每个属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="87273-121">The **IMAPIProp::GetPropList** method retrieves the property tag for each property currently supported by an object.</span></span> <span data-ttu-id="87273-122">如果对象当前不支持任何属性， **GetPropList**将返回与设置为 0 的**cValues**成员属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="87273-122">If the object does not currently support any properties, **GetPropList** returns a property tag array with the **cValues** member set to 0.</span></span> 
  
<span data-ttu-id="87273-123">返回由**GetPropList**属性的范围而有所不同商的。</span><span class="sxs-lookup"><span data-stu-id="87273-123">The scope of properties returned by **GetPropList** varies from provider to provider.</span></span> <span data-ttu-id="87273-124">某些服务提供商不包括呼叫者不具有访问这些属性。</span><span class="sxs-lookup"><span data-stu-id="87273-124">Some service providers exclude those properties for which the caller does not have access.</span></span> <span data-ttu-id="87273-125">所有提供程序返回类型**PT_OBJECT**的属性。</span><span class="sxs-lookup"><span data-stu-id="87273-125">All providers return properties of type **PT_OBJECT**.</span></span>
  
<span data-ttu-id="87273-126">如果对象不支持 Unicode， **GetPropList**将返回 MAPI_E_BAD_CHARWIDTH，即使没有为对象定义的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="87273-126">If the object does not support Unicode, **GetPropList** returns MAPI_E_BAD_CHARWIDTH, even if there are no string properties defined for the object.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="87273-127">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="87273-127">Notes to implementers</span></span>

<span data-ttu-id="87273-128">远程传输提供程序就完全等同于指定此处实现**GetPropList** 。</span><span class="sxs-lookup"><span data-stu-id="87273-128">Remote transport providers implement **GetPropList** exactly as specified here.</span></span> <span data-ttu-id="87273-129">没有任何特殊的问题。</span><span class="sxs-lookup"><span data-stu-id="87273-129">There are no special concerns.</span></span> <span data-ttu-id="87273-130">您的实现应，当然，返回相同的属性所支持的[IMAPIProp::GetProps](imapiprop-getprops.md)方法的列表。</span><span class="sxs-lookup"><span data-stu-id="87273-130">Your implementation should, of course, return the same list of properties as supported by the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="87273-131">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="87273-131">Notes to callers</span></span>

<span data-ttu-id="87273-132">调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放所指的_lppPropTagArray_属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="87273-132">Call the [MAPIFreeBuffer](mapifreebuffer.md) function to free the property tag array pointed to by  _lppPropTagArray_.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="87273-133">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="87273-133">MFCMAPI reference</span></span>

<span data-ttu-id="87273-134">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="87273-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="87273-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="87273-135">**File**</span></span>|<span data-ttu-id="87273-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="87273-136">**Function**</span></span>|<span data-ttu-id="87273-137">**Comment**</span><span class="sxs-lookup"><span data-stu-id="87273-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="87273-138">MAPIFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="87273-138">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="87273-139">GetPropsNULL</span><span class="sxs-lookup"><span data-stu-id="87273-139">GetPropsNULL</span></span>  <br/> |<span data-ttu-id="87273-140">MFCMAPI 使用**IMAPIProp::GetPropList**方法来获取要传递给**GetProps**属性列表。</span><span class="sxs-lookup"><span data-stu-id="87273-140">MFCMAPI uses the **IMAPIProp::GetPropList** method to get a property list to pass to **GetProps**.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="87273-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87273-141">See also</span></span>



[<span data-ttu-id="87273-142">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="87273-142">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="87273-143">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="87273-143">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="87273-144">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="87273-144">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="87273-145">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="87273-145">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

