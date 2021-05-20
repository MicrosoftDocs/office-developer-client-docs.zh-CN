---
title: IProviderAdminGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.GetLastError
api_type:
- COM
ms.assetid: 853ddee5-24d6-423d-b483-6a07a12de51f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4fc4867d5ca20f8e770afa239b0dffbd8ab1c480
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439847"
---
# <a name="iprovideradmingetlasterror"></a><span data-ttu-id="5af46-103">IProviderAdmin::GetLastError</span><span class="sxs-lookup"><span data-stu-id="5af46-103">IProviderAdmin::GetLastError</span></span>

  
  
<span data-ttu-id="5af46-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5af46-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5af46-105">返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关提供程序管理对象发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="5af46-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error that occurred to the provider administration object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="5af46-106">参数</span><span class="sxs-lookup"><span data-stu-id="5af46-106">Parameters</span></span>

 <span data-ttu-id="5af46-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="5af46-107">_hResult_</span></span>
  
> <span data-ttu-id="5af46-108">[in]HRESULT 数据类型，其中包含在上一个方法调用中生成的错误值。</span><span class="sxs-lookup"><span data-stu-id="5af46-108">[in] An HRESULT data type that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="5af46-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5af46-109">_ulFlags_</span></span>
  
> <span data-ttu-id="5af46-110">[in]控制返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="5af46-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="5af46-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="5af46-111">The following flag can be set:</span></span>
    
<span data-ttu-id="5af46-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5af46-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5af46-113">_lppMAPIError_ 参数中返回的 **MAPIERROR** 中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5af46-113">The strings in the **MAPIERROR** returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="5af46-114">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5af46-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="5af46-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="5af46-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="5af46-116">[out]指向返回的 **MAPIERROR** 结构的指针的指针，其中包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="5af46-116">[out] A pointer to a pointer to the returned **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="5af46-117">如果没有要返回的 **MAPIERROR，** 可以将 _lppMAPIError_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5af46-117">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5af46-118">返回值</span><span class="sxs-lookup"><span data-stu-id="5af46-118">Return value</span></span>

<span data-ttu-id="5af46-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="5af46-119">S_OK</span></span> 
  
> <span data-ttu-id="5af46-120">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="5af46-120">The call succeeded and returned the expected value or values.</span></span>
    
<span data-ttu-id="5af46-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="5af46-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="5af46-122">设置MAPI_UNICODE **GetLastError** 不支持 Unicode，或者未MAPI_UNICODE **GetLastError** 仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="5af46-122">Either the MAPI_UNICODE flag was set and **GetLastError** does not support Unicode, or MAPI_UNICODE was not set and **GetLastError** supports only Unicode.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="5af46-123">备注</span><span class="sxs-lookup"><span data-stu-id="5af46-123">Remarks</span></span>

<span data-ttu-id="5af46-124">**IProviderAdmin：：GetLastError** 方法提供有关失败之前的方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="5af46-124">The **IProviderAdmin::GetLastError** method supplies information about a prior method call that failed.</span></span> <span data-ttu-id="5af46-125">调用方可以通过在对话框中包含 **MAPIERROR** 结构的数据来为用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5af46-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5af46-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5af46-126">Notes to callers</span></span>

<span data-ttu-id="5af46-127">只有在 **GetLastError** 返回值时，才能使用 **MAPIERROR** 结构（如果 MAPI 提供了一个 MAPI S_OK）。 </span><span class="sxs-lookup"><span data-stu-id="5af46-127">You can use the **MAPIERROR** structure, if MAPI supplies one, that the  _lppMAPIError_ parameter points to only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="5af46-128">有时 MAPI 无法确定上一个错误是什么，或者没有更多关于错误的报告。</span><span class="sxs-lookup"><span data-stu-id="5af46-128">Sometimes MAPI cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="5af46-129">在这种情况下，将改为在  _lppMAPIError_ 中返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="5af46-129">In this situation, a pointer to NULL is returned in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="5af46-130">有关 **GetLastError** 方法的详细信息，请参阅 [使用扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="5af46-130">For more information about the **GetLastError** method, see [Using Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5af46-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5af46-131">See also</span></span>



[<span data-ttu-id="5af46-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="5af46-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="5af46-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="5af46-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="5af46-134">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5af46-134">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)

