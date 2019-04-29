---
title: IPersistMessageGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.GetLastError
api_type:
- COM
ms.assetid: 32cc3a1f-1310-4788-b0f4-93c1e4940f37
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2189a39e115236e6c2ec9de8a263ce3982d8b8e0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426707"
---
# <a name="ipersistmessagegetlasterror"></a><span data-ttu-id="d11c0-103">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="d11c0-103">IPersistMessage::GetLastError</span></span>

  
  
<span data-ttu-id="d11c0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d11c0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d11c0-105">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关 form 对象中的前一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d11c0-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error in the form object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="d11c0-106">参数</span><span class="sxs-lookup"><span data-stu-id="d11c0-106">Parameters</span></span>

 <span data-ttu-id="d11c0-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="d11c0-107">_hResult_</span></span>
  
> <span data-ttu-id="d11c0-108">实时一个 HRESULT 数据类型, 其中包含在上一方法调用中生成的错误值。</span><span class="sxs-lookup"><span data-stu-id="d11c0-108">[in] An HRESULT data type that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="d11c0-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d11c0-109">_ulFlags_</span></span>
  
> <span data-ttu-id="d11c0-110">实时用于控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="d11c0-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="d11c0-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="d11c0-111">The following flag can be set:</span></span>
    
<span data-ttu-id="d11c0-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d11c0-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="d11c0-113">在_lppMAPIError_参数中返回的[MAPIERROR](mapierror.md)结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="d11c0-113">The strings in the [MAPIERROR](mapierror.md) structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="d11c0-114">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="d11c0-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="d11c0-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="d11c0-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="d11c0-116">排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="d11c0-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="d11c0-117">如果窗体无法为**MAPIERROR**结构提供适当的信息, 则可以将_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d11c0-117">The  _lppMAPIError_ parameter can be set to NULL if the form cannot supply appropriate information for a **MAPIERROR** structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d11c0-118">返回值</span><span class="sxs-lookup"><span data-stu-id="d11c0-118">Return value</span></span>

<span data-ttu-id="d11c0-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="d11c0-119">S_OK</span></span> 
  
> <span data-ttu-id="d11c0-120">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="d11c0-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="d11c0-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="d11c0-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="d11c0-122">设置了 MAPI_UNICODE 标志, 且通讯簿提供程序不支持 unicode, 或者未设置 MAPI_UNICODE, 并且通讯簿提供程序仅支持 unicode。</span><span class="sxs-lookup"><span data-stu-id="d11c0-122">Either the MAPI_UNICODE flag was set and the address book provider does not support Unicode, or MAPI_UNICODE was not set and the address book provider supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d11c0-123">说明</span><span class="sxs-lookup"><span data-stu-id="d11c0-123">Remarks</span></span>

<span data-ttu-id="d11c0-124">Form 对象实现**IPersistMessage:: GetLastError**方法, 以提供有关失败的上一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="d11c0-124">Form objects implement the **IPersistMessage::GetLastError** method to supply information about a prior method call that failed.</span></span> <span data-ttu-id="d11c0-125">通过在对话框中包含[MAPIERROR](mapierror.md)结构中的数据, 表单查看者可以向其用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d11c0-125">Form viewers can provide their users with detailed information about the error by including the data from the [MAPIERROR](mapierror.md) structure in a dialog box.</span></span> 
  
<span data-ttu-id="d11c0-126">对**GetLastError**的调用不会影响窗体的状态。</span><span class="sxs-lookup"><span data-stu-id="d11c0-126">A call to **GetLastError** does not affect the state of the form.</span></span> <span data-ttu-id="d11c0-127">当返回**GetLastError**时, 窗体将保持在进行调用之前的状态。</span><span class="sxs-lookup"><span data-stu-id="d11c0-127">When **GetLastError** returns, the form remains in the state that it was in before the call was made.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="d11c0-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="d11c0-128">Notes to callers</span></span>

<span data-ttu-id="d11c0-129">如果窗体提供了**MAPIERROR**结构, 则只有当**GetLastError**返回 S_OK 时, 才能使用_lppMAPIError_参数所指向的结构。</span><span class="sxs-lookup"><span data-stu-id="d11c0-129">You can use the **MAPIERROR** structure, if the form supplies one, that is pointed to by the  _lppMAPIError_ parameter only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="d11c0-130">有时, 窗体无法确定最后一个错误是什么, 或者对错误报告没有更多的信息。</span><span class="sxs-lookup"><span data-stu-id="d11c0-130">Sometimes the form cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="d11c0-131">在这种情况下, 表单将在_lppMAPIError_中返回指向 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="d11c0-131">In this situation, the form returns a pointer to NULL in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="d11c0-132">有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="d11c0-132">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d11c0-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d11c0-133">See also</span></span>



[<span data-ttu-id="d11c0-134">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="d11c0-134">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="d11c0-135">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="d11c0-135">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="d11c0-136">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d11c0-136">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

