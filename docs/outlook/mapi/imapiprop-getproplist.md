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
ms.openlocfilehash: f089fa2c608fb9fcb7deba2e061c5cf5886aa02f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414786"
---
# <a name="imapipropgetproplist"></a><span data-ttu-id="b4104-103">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="b4104-103">IMAPIProp::GetPropList</span></span>

  
  
<span data-ttu-id="b4104-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b4104-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b4104-105">返回所有属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="b4104-105">Returns property tags for all properties.</span></span> 
  
```cpp
HRESULT GetPropList(
  ULONG ulFlags,
  LPSPropTagArray FAR * lppPropTagArray
);
```

## <a name="parameters"></a><span data-ttu-id="b4104-106">参数</span><span class="sxs-lookup"><span data-stu-id="b4104-106">Parameters</span></span>

 <span data-ttu-id="b4104-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b4104-107">_ulFlags_</span></span>
  
> <span data-ttu-id="b4104-108">实时标志的位掩码, 用于控制返回的属性标记中的字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="b4104-108">[in] A bitmask of flags that controls the format for the strings in the returned property tags.</span></span> <span data-ttu-id="b4104-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="b4104-109">The following flag can be set:</span></span>
    
<span data-ttu-id="b4104-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b4104-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b4104-111">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b4104-111">The returned strings are in Unicode format.</span></span> <span data-ttu-id="b4104-112">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b4104-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="b4104-113">_lppPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="b4104-113">_lppPropTagArray_</span></span>
  
> <span data-ttu-id="b4104-114">排除指向包含对象所有属性的标记的属性标记数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b4104-114">[out] A pointer to a pointer to the property tag array that contains tags for all of the object's properties.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b4104-115">返回值</span><span class="sxs-lookup"><span data-stu-id="b4104-115">Return value</span></span>

<span data-ttu-id="b4104-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4104-116">S_OK</span></span> 
  
> <span data-ttu-id="b4104-117">成功返回所有属性标记。</span><span class="sxs-lookup"><span data-stu-id="b4104-117">All of the property tags were returned successfully.</span></span>
    
<span data-ttu-id="b4104-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="b4104-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="b4104-119">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="b4104-119">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b4104-120">说明</span><span class="sxs-lookup"><span data-stu-id="b4104-120">Remarks</span></span>

<span data-ttu-id="b4104-121">**IMAPIProp:: GetPropList**方法检索对象当前支持的每个属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="b4104-121">The **IMAPIProp::GetPropList** method retrieves the property tag for each property currently supported by an object.</span></span> <span data-ttu-id="b4104-122">如果该对象当前不支持任何属性, 则**GetPropList**将返回**cValues**成员设置为0的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="b4104-122">If the object does not currently support any properties, **GetPropList** returns a property tag array with the **cValues** member set to 0.</span></span> 
  
<span data-ttu-id="b4104-123">**GetPropList**返回的属性范围因提供程序而异。</span><span class="sxs-lookup"><span data-stu-id="b4104-123">The scope of properties returned by **GetPropList** varies from provider to provider.</span></span> <span data-ttu-id="b4104-124">某些服务提供程序排除了呼叫者无权访问的那些属性。</span><span class="sxs-lookup"><span data-stu-id="b4104-124">Some service providers exclude those properties for which the caller does not have access.</span></span> <span data-ttu-id="b4104-125">所有提供程序都返回**PT_OBJECT**类型的属性。</span><span class="sxs-lookup"><span data-stu-id="b4104-125">All providers return properties of type **PT_OBJECT**.</span></span>
  
<span data-ttu-id="b4104-126">如果该对象不支持 Unicode, **GetPropList**将返回 MAPI_E_BAD_CHARWIDTH, 即使没有为该对象定义任何字符串属性也是如此。</span><span class="sxs-lookup"><span data-stu-id="b4104-126">If the object does not support Unicode, **GetPropList** returns MAPI_E_BAD_CHARWIDTH, even if there are no string properties defined for the object.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="b4104-127">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="b4104-127">Notes to implementers</span></span>

<span data-ttu-id="b4104-128">远程传输提供程序完全按照此处指定的方式实现**GetPropList** 。</span><span class="sxs-lookup"><span data-stu-id="b4104-128">Remote transport providers implement **GetPropList** exactly as specified here.</span></span> <span data-ttu-id="b4104-129">没有特殊的顾虑。</span><span class="sxs-lookup"><span data-stu-id="b4104-129">There are no special concerns.</span></span> <span data-ttu-id="b4104-130">当然, 您的实现应返回与[IMAPIProp:: GetProps](imapiprop-getprops.md)方法支持的相同的属性列表。</span><span class="sxs-lookup"><span data-stu-id="b4104-130">Your implementation should, of course, return the same list of properties as supported by the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b4104-131">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b4104-131">Notes to callers</span></span>

<span data-ttu-id="b4104-132">调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放_lppPropTagArray_指向的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="b4104-132">Call the [MAPIFreeBuffer](mapifreebuffer.md) function to free the property tag array pointed to by  _lppPropTagArray_.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b4104-133">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="b4104-133">MFCMAPI reference</span></span>

<span data-ttu-id="b4104-134">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b4104-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b4104-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="b4104-135">**File**</span></span>|<span data-ttu-id="b4104-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="b4104-136">**Function**</span></span>|<span data-ttu-id="b4104-137">**备注**</span><span class="sxs-lookup"><span data-stu-id="b4104-137">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4104-138">MAPIFunctions</span><span class="sxs-lookup"><span data-stu-id="b4104-138">MAPIFunctions.cpp</span></span>  <br/> |<span data-ttu-id="b4104-139">GetPropsNULL</span><span class="sxs-lookup"><span data-stu-id="b4104-139">GetPropsNULL</span></span>  <br/> |<span data-ttu-id="b4104-140">MFCMAPI 使用**IMAPIProp:: GetPropList**方法获取要传递给**GetProps**的属性列表。</span><span class="sxs-lookup"><span data-stu-id="b4104-140">MFCMAPI uses the **IMAPIProp::GetPropList** method to get a property list to pass to **GetProps**.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b4104-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4104-141">See also</span></span>



[<span data-ttu-id="b4104-142">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="b4104-142">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="b4104-143">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="b4104-143">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="b4104-144">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b4104-144">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)


[<span data-ttu-id="b4104-145">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b4104-145">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

