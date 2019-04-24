---
title: IABLogonGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.GetLastError
api_type:
- COM
ms.assetid: d157e29e-7731-4e47-b4a7-e8622b223001
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 311299b00143667b3f2fb22bd7be6c3a52c7141d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349026"
---
# <a name="iablogongetlasterror"></a><span data-ttu-id="55a9e-103">IABLogon::GetLastError</span><span class="sxs-lookup"><span data-stu-id="55a9e-103">IABLogon::GetLastError</span></span>

  
  
<span data-ttu-id="55a9e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="55a9e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="55a9e-105">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含以前的通讯簿提供程序错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="55a9e-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous address book provider error.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="55a9e-106">参数</span><span class="sxs-lookup"><span data-stu-id="55a9e-106">Parameters</span></span>

 <span data-ttu-id="55a9e-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="55a9e-107">_hResult_</span></span>
  
> <span data-ttu-id="55a9e-108">实时在上一方法调用中生成的错误值的句柄。</span><span class="sxs-lookup"><span data-stu-id="55a9e-108">[in] A handle to the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="55a9e-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="55a9e-109">_ulFlags_</span></span>
  
> <span data-ttu-id="55a9e-110">实时用于控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="55a9e-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="55a9e-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="55a9e-111">The following flag can be set:</span></span>
    
<span data-ttu-id="55a9e-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="55a9e-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="55a9e-113">在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="55a9e-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="55a9e-114">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="55a9e-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="55a9e-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="55a9e-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="55a9e-116">排除指向包含错误的版本、组件和上下文信息的**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="55a9e-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="55a9e-117">如果提供程序无法提供具有相应信息的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="55a9e-117">The  _lppMAPIError_ parameter can be set to NULL if the provider cannot supply a **MAPIERROR** structure with appropriate information.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="55a9e-118">返回值</span><span class="sxs-lookup"><span data-stu-id="55a9e-118">Return value</span></span>

<span data-ttu-id="55a9e-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="55a9e-119">S_OK</span></span> 
  
> <span data-ttu-id="55a9e-120">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="55a9e-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="55a9e-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="55a9e-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="55a9e-122">设置了 MAPI_UNICODE 标志, 且通讯簿提供程序不支持 unicode, 或者未设置 MAPI_UNICODE, 并且通讯簿提供程序仅支持 unicode。</span><span class="sxs-lookup"><span data-stu-id="55a9e-122">Either the MAPI_UNICODE flag was set and the address book provider does not support Unicode, or MAPI_UNICODE was not set and the address book provider supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="55a9e-123">注解</span><span class="sxs-lookup"><span data-stu-id="55a9e-123">Remarks</span></span>

<span data-ttu-id="55a9e-124">通讯簿提供程序实现了**GetLastError**方法, 以提供有关失败的上一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="55a9e-124">Address book providers implement the **GetLastError** method to supply information about a prior method call that failed.</span></span> <span data-ttu-id="55a9e-125">通过在对话框中包含**MAPIERROR**结构中的数据, 呼叫者可以向其用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="55a9e-125">Callers can provide their users with detailed information about the error by including the data from the **MAPIERROR** structure in a dialog box.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="55a9e-126">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="55a9e-126">Notes to callers</span></span>

<span data-ttu-id="55a9e-127">如果通讯簿提供程序提供结构, 并且只有在**GetLastError**返回 S_OK 时, 您可以使用_lppMAPIError_参数指向的**MAPIERROR**结构。</span><span class="sxs-lookup"><span data-stu-id="55a9e-127">You can use the **MAPIERROR** structure pointed to by the  _lppMAPIError_ parameter if the address book provider supplies the structure and only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="55a9e-128">有时通讯簿提供程序无法确定最后一个错误是什么, 或者对错误报告没有什么更多的报告。</span><span class="sxs-lookup"><span data-stu-id="55a9e-128">Sometimes the address book provider cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="55a9e-129">在这种情况下, 通讯簿提供程序将返回指向_lppMAPIError_中的 NULL 的指针。</span><span class="sxs-lookup"><span data-stu-id="55a9e-129">In this situation, the address book provider returns a pointer to NULL in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="55a9e-130">有关**GetLastError**方法的详细信息, 请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="55a9e-130">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="55a9e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55a9e-131">See also</span></span>



[<span data-ttu-id="55a9e-132">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="55a9e-132">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="55a9e-133">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="55a9e-133">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="55a9e-134">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="55a9e-134">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

