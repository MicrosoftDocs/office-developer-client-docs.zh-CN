---
title: IMSLogonGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.GetLastError
api_type:
- COM
ms.assetid: 3e296f6d-4833-4c68-9b84-df0b09878474
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 472502d0f033370b06a69596944350152ab794f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425874"
---
# <a name="imslogongetlasterror"></a><span data-ttu-id="5982d-103">IMSLogon::GetLastError</span><span class="sxs-lookup"><span data-stu-id="5982d-103">IMSLogon::GetLastError</span></span>

  
  
<span data-ttu-id="5982d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5982d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5982d-105">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关邮件存储对象的最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="5982d-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the last error that occurred for the message store object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="5982d-106">参数</span><span class="sxs-lookup"><span data-stu-id="5982d-106">Parameters</span></span>

 <span data-ttu-id="5982d-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="5982d-107">_hResult_</span></span>
  
> <span data-ttu-id="5982d-108">实时一个 HRESULT 数据类型, 其中包含在以前的方法调用中为邮件存储对象生成的错误值。</span><span class="sxs-lookup"><span data-stu-id="5982d-108">[in] An HRESULT data type that contains the error value generated in the previous method call for the message store object.</span></span>
    
 <span data-ttu-id="5982d-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5982d-109">_ulFlags_</span></span>
  
> <span data-ttu-id="5982d-110">实时用于控制返回的字符串类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="5982d-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="5982d-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="5982d-111">The following flag can be set:</span></span>
    
<span data-ttu-id="5982d-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5982d-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5982d-113">在_lppMAPIError_参数中返回的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5982d-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="5982d-114">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5982d-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="5982d-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="5982d-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="5982d-116">排除指向包含错误的版本、组件和上下文信息的返回的**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="5982d-116">[out] A pointer to a pointer to the returned **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="5982d-117">如果没有要返回的**MAPIERROR** , 则可以将_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5982d-117">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5982d-118">返回值</span><span class="sxs-lookup"><span data-stu-id="5982d-118">Return value</span></span>

<span data-ttu-id="5982d-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="5982d-119">S_OK</span></span> 
  
> <span data-ttu-id="5982d-120">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="5982d-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="5982d-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="5982d-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="5982d-122">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="5982d-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5982d-123">说明</span><span class="sxs-lookup"><span data-stu-id="5982d-123">Remarks</span></span>

<span data-ttu-id="5982d-124">使用**IMSLogon:: GetLastError**方法检索信息, 以供用户显示在邮件中, 以便与邮件存储对象的方法调用中返回的最后一个错误有关。</span><span class="sxs-lookup"><span data-stu-id="5982d-124">Use the **IMSLogon::GetLastError** method to retrieve information to display in a message to the user regarding the last error returned from a method call for the message store object.</span></span> 
  
<span data-ttu-id="5982d-125">若要释放 MAPI 为返回的**MAPIERROR**结构分配的所有内存, 客户端应用程序只需调用[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="5982d-125">To release all the memory allocated by MAPI for the returned **MAPIERROR** structure, client applications need to call only the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="5982d-126">对于要使用**MAPIERROR**的应用程序, 从**GetLastError**返回的值必须为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="5982d-126">The return value from **GetLastError** must be S_OK for an application to use the **MAPIERROR**.</span></span> <span data-ttu-id="5982d-127">即使返回值为 S_OK, 也可能不会返回**MAPIERROR** 。</span><span class="sxs-lookup"><span data-stu-id="5982d-127">Even if the return value is S_OK, a **MAPIERROR** might not be returned.</span></span> <span data-ttu-id="5982d-128">如果实现无法确定上一个错误是什么, 或者**MAPIERROR**不能用于该错误, 则**GetLastError**将返回指向_lppMAPIError_中的 NULL 的指针而不是。</span><span class="sxs-lookup"><span data-stu-id="5982d-128">If the implementation cannot determine what the last error was, or if a **MAPIERROR** is not available for that error, **GetLastError** returns a pointer to NULL in  _lppMAPIError_ instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5982d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5982d-129">See also</span></span>



[<span data-ttu-id="5982d-130">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="5982d-130">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="5982d-131">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="5982d-131">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="5982d-132">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5982d-132">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

