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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a865a751f3e274008c7004315906d6705ba55161
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775936"
---
# <a name="imslogongetlasterror"></a><span data-ttu-id="ee77e-103">IMSLogon::GetLastError</span><span class="sxs-lookup"><span data-stu-id="ee77e-103">IMSLogon::GetLastError</span></span>

  
  
<span data-ttu-id="ee77e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ee77e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ee77e-105">返回一个[MAPIERROR](mapierror.md)结构，其中包含上次消息存储对象发生的错误有关的信息。</span><span class="sxs-lookup"><span data-stu-id="ee77e-105">Returns a [MAPIERROR](mapierror.md) structure that contains information about the last error that occurred for the message store object.</span></span> 
  
```cpp
HRESULT GetLastError(
  HRESULT hResult,
  ULONG ulFlags,
  LPMAPIERROR FAR * lppMAPIError
);
```

## <a name="parameters"></a><span data-ttu-id="ee77e-106">参数</span><span class="sxs-lookup"><span data-stu-id="ee77e-106">Parameters</span></span>

 <span data-ttu-id="ee77e-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="ee77e-107">_hResult_</span></span>
  
> <span data-ttu-id="ee77e-108">[in]包含消息存储对象的上一个方法调用中生成的错误值 HRESULT 数据类型。</span><span class="sxs-lookup"><span data-stu-id="ee77e-108">[in] An HRESULT data type that contains the error value generated in the previous method call for the message store object.</span></span>
    
 <span data-ttu-id="ee77e-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ee77e-109">_ulFlags_</span></span>
  
> <span data-ttu-id="ee77e-110">[in]返回控制的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="ee77e-110">[in] A bitmask of flags that controls the type of strings returned.</span></span> <span data-ttu-id="ee77e-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="ee77e-111">The following flag can be set:</span></span>
    
<span data-ttu-id="ee77e-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ee77e-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="ee77e-113">返回_lppMAPIError_参数中的**MAPIERROR**结构中的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="ee77e-113">The strings in the **MAPIERROR** structure returned in the  _lppMAPIError_ parameter are in Unicode format.</span></span> <span data-ttu-id="ee77e-114">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="ee77e-114">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span> 
    
 <span data-ttu-id="ee77e-115">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="ee77e-115">_lppMAPIError_</span></span>
  
> <span data-ttu-id="ee77e-116">[输出]指向包含错误的版本、 组件及上下文信息返回**MAPIERROR**结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ee77e-116">[out] A pointer to a pointer to the returned **MAPIERROR** structure that contains version, component, and context information for the error.</span></span> <span data-ttu-id="ee77e-117">如果不没有返回任何**MAPIERROR** ， _lppMAPIError_参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ee77e-117">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** to return.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ee77e-118">返回值</span><span class="sxs-lookup"><span data-stu-id="ee77e-118">Return value</span></span>

<span data-ttu-id="ee77e-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee77e-119">S_OK</span></span> 
  
> <span data-ttu-id="ee77e-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="ee77e-120">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="ee77e-121">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="ee77e-121">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="ee77e-122">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="ee77e-122">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ee77e-123">说明</span><span class="sxs-lookup"><span data-stu-id="ee77e-123">Remarks</span></span>

<span data-ttu-id="ee77e-124">**IMSLogon::GetLastError**方法用于检索要显示给用户有关从方法调用该消息存储对象返回的最后一个错误消息中的信息。</span><span class="sxs-lookup"><span data-stu-id="ee77e-124">Use the **IMSLogon::GetLastError** method to retrieve information to display in a message to the user regarding the last error returned from a method call for the message store object.</span></span> 
  
<span data-ttu-id="ee77e-125">若要释放所有 MAPI 返回**MAPIERROR**结构所分配的内存，客户端应用程序需要调用仅[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="ee77e-125">To release all the memory allocated by MAPI for the returned **MAPIERROR** structure, client applications need to call only the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="ee77e-126">从**GetLastError**返回的值必须是应用程序使用**MAPIERROR**S_OK。</span><span class="sxs-lookup"><span data-stu-id="ee77e-126">The return value from **GetLastError** must be S_OK for an application to use the **MAPIERROR**.</span></span> <span data-ttu-id="ee77e-127">即使的返回值是 S_OK，可能不会返回**MAPIERROR** 。</span><span class="sxs-lookup"><span data-stu-id="ee77e-127">Even if the return value is S_OK, a **MAPIERROR** might not be returned.</span></span> <span data-ttu-id="ee77e-128">如果实现无法确定最后一个错误是什么，或者**MAPIERROR**不用于该错误， **GetLastError**返回一个指针为 NULL 中_lppMAPIError_改为。</span><span class="sxs-lookup"><span data-stu-id="ee77e-128">If the implementation cannot determine what the last error was, or if a **MAPIERROR** is not available for that error, **GetLastError** returns a pointer to NULL in  _lppMAPIError_ instead.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ee77e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee77e-129">See also</span></span>



[<span data-ttu-id="ee77e-130">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="ee77e-130">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="ee77e-131">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="ee77e-131">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="ee77e-132">IMSLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ee77e-132">IMSLogon : IUnknown</span></span>](imslogoniunknown.md)

