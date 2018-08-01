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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 16f091f4d9527cd82ebc1d1eadee2fb55b481929
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775984"
---
# <a name="ipersistmessagegetlasterror"></a><span data-ttu-id="0cd32-103">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="0cd32-103">IPersistMessage::GetLastError</span></span>

  
  
<span data-ttu-id="0cd32-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0cd32-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0cd32-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关表单对象中前面的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="0cd32-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error in the form object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="0cd32-106">参数</span><span class="sxs-lookup"><span data-stu-id="0cd32-106">Parameters</span></span>

 <span data-ttu-id="0cd32-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="0cd32-107">_hResult_</span></span>
  
> <span data-ttu-id="0cd32-108">[in]包含上一方法调用中生成的错误值 HRESULT 数据类型。</span><span class="sxs-lookup"><span data-stu-id="0cd32-108">[in] An HRESULT data type that contains the error value generated in the previous method call.</span></span>
    
 <span data-ttu-id="0cd32-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0cd32-109">_ulFlags_</span></span>
  
> <span data-ttu-id="0cd32-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="0cd32-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="0cd32-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="0cd32-111">The following flag can be set:</span></span>
    
<span data-ttu-id="0cd32-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0cd32-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="0cd32-113">返回_lppMAPIError_参数中的[MAPIERROR](mapierror.md)结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="0cd32-113">The strings in the [MAPIERROR](mapierror.md) structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="0cd32-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="0cd32-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="0cd32-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="0cd32-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="0cd32-116">[输出]指向包含错误的版本、 组件及上下文信息**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="0cd32-116">[out] A pointer to a pointer to a **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="0cd32-117">_LppMAPIError_参数可以设置为 NULL，如果窗体不能提供相应**MAPIERROR**结构的信息。</span><span class="sxs-lookup"><span data-stu-id="0cd32-117">The  _lppMAPIError_ parameter can be set to NULL if the form cannot supply appropriate information for a **MAPIERROR** structure.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0cd32-118">返回值</span><span class="sxs-lookup"><span data-stu-id="0cd32-118">Return value</span></span>

<span data-ttu-id="0cd32-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="0cd32-119">S_OK</span></span> 
  
> <span data-ttu-id="0cd32-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="0cd32-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="0cd32-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="0cd32-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="0cd32-122">既设置了 MAPI_UNICODE 标志通讯簿提供程序不支持 Unicode，或未设置 MAPI_UNICODE 和通讯簿提供程序支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="0cd32-122">Either the MAPI_UNICODE flag was set and the address book provider does not support Unicode, or MAPI_UNICODE was not set and the address book provider supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0cd32-123">说明</span><span class="sxs-lookup"><span data-stu-id="0cd32-123">Remarks</span></span>

<span data-ttu-id="0cd32-124">表单对象实现**IPersistMessage::GetLastError**方法以提供有关失败的前一个方法调用的信息。</span><span class="sxs-lookup"><span data-stu-id="0cd32-124">Form objects implement the **IPersistMessage::GetLastError** method to supply information about a prior method call that failed.</span></span> <span data-ttu-id="0cd32-125">窗体查看者可以通过在对话框中包含的数据从[MAPIERROR](mapierror.md)结构为其用户提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0cd32-125">Form viewers can provide their users with detailed information about the error by including the data from the [MAPIERROR](mapierror.md) structure in a dialog box.</span></span> 
  
<span data-ttu-id="0cd32-126">调用**GetLastError**不会影响表单的状态。</span><span class="sxs-lookup"><span data-stu-id="0cd32-126">A call to **GetLastError** does not affect the state of the form.</span></span> <span data-ttu-id="0cd32-127">**GetLastError**返回时，窗体将保持之前拨打电话的状态。</span><span class="sxs-lookup"><span data-stu-id="0cd32-127">When **GetLastError** returns, the form remains in the state that it was in before the call was made.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0cd32-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0cd32-128">Notes to callers</span></span>

<span data-ttu-id="0cd32-129">如果表单提供一个指向_lppMAPIError_参数**时出错**，则返回 S_OK 时，才可以使用**MAPIERROR**结构。</span><span class="sxs-lookup"><span data-stu-id="0cd32-129">You can use the **MAPIERROR** structure, if the form supplies one, that is pointed to by the  _lppMAPIError_ parameter only if **GetLastError** returns S_OK.</span></span> <span data-ttu-id="0cd32-130">有时表单无法确定最后一个错误已或某种更多有关错误报告。</span><span class="sxs-lookup"><span data-stu-id="0cd32-130">Sometimes the form cannot determine what the last error was or has nothing more to report about the error.</span></span> <span data-ttu-id="0cd32-131">在此情况下，窗体返回一个指针为 NULL 中_lppMAPIError_相反。</span><span class="sxs-lookup"><span data-stu-id="0cd32-131">In this situation, the form returns a pointer to NULL in  _lppMAPIError_ instead.</span></span> 
  
<span data-ttu-id="0cd32-132">有关**GetLastError**方法的详细信息，请参阅[MAPI 扩展错误](mapi-extended-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="0cd32-132">For more information about the **GetLastError** method, see [MAPI Extended Errors](mapi-extended-errors.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0cd32-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cd32-133">See also</span></span>



[<span data-ttu-id="0cd32-134">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="0cd32-134">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="0cd32-135">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="0cd32-135">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="0cd32-136">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0cd32-136">IPersistMessage : IUnknown</span></span>](ipersistmessageiunknown.md)

