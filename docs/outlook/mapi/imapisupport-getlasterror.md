---
title: IMAPISupportGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetLastError
api_type:
- COM
ms.assetid: 5b4290d9-230f-416a-9644-188578565c7b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c34c175c43ada03e982f08a27f675448ea24a567
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438545"
---
# <a name="imapisupportgetlasterror"></a><span data-ttu-id="3378f-103">IMAPISupport::GetLastError</span><span class="sxs-lookup"><span data-stu-id="3378f-103">IMAPISupport::GetLastError</span></span>

  
  
<span data-ttu-id="3378f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3378f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3378f-105">返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个支持对象错误的信息。</span><span class="sxs-lookup"><span data-stu-id="3378f-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous support object error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="3378f-106">参数</span><span class="sxs-lookup"><span data-stu-id="3378f-106">Parameters</span></span>

 <span data-ttu-id="3378f-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="3378f-107">_hResult_</span></span>
  
> <span data-ttu-id="3378f-108">[in]对在上一个方法调用中为支持对象生成的错误值的句柄。</span><span class="sxs-lookup"><span data-stu-id="3378f-108">[in] A handle to the error value generated in the previous method call for the support object.</span></span>
    
 <span data-ttu-id="3378f-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3378f-109">_ulFlags_</span></span>
  
> <span data-ttu-id="3378f-110">[in]控制返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="3378f-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="3378f-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="3378f-111">The following flag can be set:</span></span>
    
<span data-ttu-id="3378f-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3378f-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="3378f-113">_lppMAPIError_ 参数中返回的 **MAPIERROR** 结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="3378f-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="3378f-114">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="3378f-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="3378f-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="3378f-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="3378f-116">[out]指向指向 **MAPIERROR** 结构的指针的指针，该结构包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="3378f-116">[out] A pointer to a pointer to the **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="3378f-117">如果无法提供包含相应错误信息的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3378f-117">The  _lppMAPIError_ parameter can be set to NULL if a **MAPIERROR** structure with appropriate error information cannot be provided.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3378f-118">返回值</span><span class="sxs-lookup"><span data-stu-id="3378f-118">Return value</span></span>

<span data-ttu-id="3378f-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="3378f-119">S_OK</span></span> 
  
> <span data-ttu-id="3378f-120">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="3378f-120">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="3378f-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="3378f-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="3378f-122">设置MAPI_UNICODE MAPI 不支持 Unicode，或者未MAPI_UNICODE MAPI 仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="3378f-122">Either the MAPI_UNICODE flag was set and MAPI does not support Unicode, or MAPI_UNICODE was not set and MAPI supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3378f-123">备注</span><span class="sxs-lookup"><span data-stu-id="3378f-123">Remarks</span></span>

<span data-ttu-id="3378f-124">**IMAPISupport：：GetLastError** 方法针对所有支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="3378f-124">The **IMAPISupport::GetLastError** method is implemented for all support objects.</span></span> <span data-ttu-id="3378f-125">调用方可以通过在对话框中包含 **MAPIERROR** 结构的数据来为用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3378f-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3378f-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3378f-126">Notes to callers</span></span>

<span data-ttu-id="3378f-127">只有当 **GetLastError** 返回值时，才能在 _lppMAPIError_ 参数中使用指向 **MAPIERROR** 结构的指针（如果 MAPI 提供了S_OK）。</span><span class="sxs-lookup"><span data-stu-id="3378f-127">You can use the pointer to the **MAPIERROR** structure, if MAPI supplies one, in the  _lppMAPIError_ parameter only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="3378f-128">有时 MAPI 无法确定上一个错误是什么，或者它仅能报告有关该错误的信息。</span><span class="sxs-lookup"><span data-stu-id="3378f-128">Sometimes MAPI cannot determine what the last error was or it has nothing more to report about the error.</span></span> <span data-ttu-id="3378f-129">在这种情况下  _，lppMAPIError_ 会改为返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="3378f-129">In this situation,  _lppMAPIError_ returns a pointer to NULL instead.</span></span> 
  
<span data-ttu-id="3378f-130">有关 **GetLastError** 方法的详细信息，请参阅 [MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="3378f-130">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
<span data-ttu-id="3378f-131">若要释放 MAPI 分配的所有内存，请为返回的 **MAPIERROR** 结构调用 [MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="3378f-131">To release all the memory allocated by MAPI, call the [MAPIFreeBuffer](mapifreebuffer.md) function for the returned **MAPIERROR** structure.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3378f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3378f-132">See also</span></span>



[<span data-ttu-id="3378f-133">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="3378f-133">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="3378f-134">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="3378f-134">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="3378f-135">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3378f-135">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)


[<span data-ttu-id="3378f-136">MAPI 扩展错误</span><span class="sxs-lookup"><span data-stu-id="3378f-136">MAPI Extended Errors</span></span>](mapi-extended-errors.md)

