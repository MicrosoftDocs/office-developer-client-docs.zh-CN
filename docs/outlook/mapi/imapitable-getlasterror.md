---
title: IMAPITableGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.GetLastError
api_type:
- COM
ms.assetid: 832e2c18-ddba-4d18-a391-710d21fe23e6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2444ea7e05367423e7920be3a871c2ab68aad76d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419000"
---
# <a name="imapitablegetlasterror"></a><span data-ttu-id="4ca3a-103">IMAPITable::GetLastError</span><span class="sxs-lookup"><span data-stu-id="4ca3a-103">IMAPITable::GetLastError</span></span>

  
  
<span data-ttu-id="4ca3a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4ca3a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4ca3a-105">返回一个[MAPIERROR](mapierror.md)结构, 其中包含有关表格上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-105">Returns a [MAPIERROR](mapierror.md) structure containing information about the previous error on the table.</span></span> 
  
```cpp
HRESULT GetLastError(
HRESULT hResult,
ULONG ulFlags,
LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="4ca3a-106">参数</span><span class="sxs-lookup"><span data-stu-id="4ca3a-106">Parameters</span></span>

 <span data-ttu-id="4ca3a-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="4ca3a-107">_hResult_</span></span>
  
> <span data-ttu-id="4ca3a-108">实时HRESULT 包含在上一方法调用中生成的错误。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-108">[in] HRESULT containing the error generated in the previous method call.</span></span>
    
 <span data-ttu-id="4ca3a-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="4ca3a-109">_ulFlags_</span></span>
  
> <span data-ttu-id="4ca3a-110">实时用于控制返回的字符串的类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-110">[in] Bitmask of flags that controls the type of the returned strings.</span></span> <span data-ttu-id="4ca3a-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="4ca3a-111">The following flag can be set:</span></span>
    
<span data-ttu-id="4ca3a-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4ca3a-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="4ca3a-113">在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="4ca3a-114">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="4ca3a-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="4ca3a-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="4ca3a-116">排除指向指向包含错误的版本、组件和上下文信息的返回的**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-116">[out] Pointer to a pointer to the returned **MAPIERROR** structure containing version, component, and context information for the error.</span></span> <span data-ttu-id="4ca3a-117">如果无法提供具有相应信息的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-117">The  _lppMAPIError_ parameter can be set to NULL if a **MAPIERROR** structure with appropriate information cannot be provided.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="4ca3a-118">返回值</span><span class="sxs-lookup"><span data-stu-id="4ca3a-118">Return value</span></span>

<span data-ttu-id="4ca3a-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ca3a-119">S_OK</span></span> 
  
> <span data-ttu-id="4ca3a-120">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="4ca3a-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="4ca3a-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="4ca3a-122">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation only supports Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4ca3a-123">说明</span><span class="sxs-lookup"><span data-stu-id="4ca3a-123">Remarks</span></span>

<span data-ttu-id="4ca3a-124">**IMAPITable:: GetLastError**方法返回有关以前的方法调用失败的详细信息 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-124">The **IMAPITable::GetLastError** method returns detailed information, if available, about a prior method call that failed.</span></span> <span data-ttu-id="4ca3a-125">此信息可以显示在邮件或对话框中。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-125">This information can be displayed in a message or a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="4ca3a-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="4ca3a-126">Notes to callers</span></span>

<span data-ttu-id="4ca3a-127">在需要向用户显示有关错误的信息时, 请调用**GetLastError** 。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-127">Call **GetLastError** whenever you need to display information about an error to the user.</span></span> 
  
<span data-ttu-id="4ca3a-128">如果 table 对象仅在**GetLastError**返回 S_OK 时仅提供一个 MAPIERROR 结构, 则可以使用_lppMAPIError_参数所指向的[](mapierror.md)结构。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-128">You can make use of the [MAPIERROR](mapierror.md) structure pointed to by the  _lppMAPIError_ parameter if the table object supplies one only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="4ca3a-129">有时, 表实现无法确定最后一个错误是什么, 或者对错误报告没有什么更多的报告。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-129">Sometimes the table implementation cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="4ca3a-130">在这种情况下, _lppMAPIError_中的指针设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-130">In this situation, the pointer at  _lppMAPIError_ is set to NULL.</span></span> 
  
<span data-ttu-id="4ca3a-131">若要释放为**MAPIERROR**结构分配的所有内存, 请调用[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-131">To release all the memory allocated for the **MAPIERROR** structure, call the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="4ca3a-132">有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="4ca3a-132">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4ca3a-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ca3a-133">See also</span></span>



[<span data-ttu-id="4ca3a-134">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="4ca3a-134">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="4ca3a-135">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="4ca3a-135">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="4ca3a-136">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4ca3a-136">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)

