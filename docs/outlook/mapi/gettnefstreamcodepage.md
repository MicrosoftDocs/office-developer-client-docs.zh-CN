---
title: GetTnefStreamCodepage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0f22ccf2-1004-4731-9d68-f66c01b4588b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1e3d384f35726ff28bb47f3d537c8a7a1dda6dce
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399653"
---
# <a name="gettnefstreamcodepage"></a><span data-ttu-id="72ca3-103">GetTnefStreamCodepage</span><span class="sxs-lookup"><span data-stu-id="72ca3-103">GetTnefStreamCodepage</span></span>

  
  
<span data-ttu-id="72ca3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="72ca3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="72ca3-105">确定传输中性封装格式 (TNEF) 流的代码页。</span><span class="sxs-lookup"><span data-stu-id="72ca3-105">Determines the code page for a Transport-Neutral Encapsulation Format (TNEF) stream.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="72ca3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="72ca3-106">Header file:</span></span>  <br/> |<span data-ttu-id="72ca3-107">tnef.h</span><span class="sxs-lookup"><span data-stu-id="72ca3-107">tnef.h</span></span>  <br/> |
|<span data-ttu-id="72ca3-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="72ca3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="72ca3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="72ca3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="72ca3-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="72ca3-110">Called by:</span></span>  <br/> |<span data-ttu-id="72ca3-111">客户端应用程序和服务提供商。</span><span class="sxs-lookup"><span data-stu-id="72ca3-111">Client applications and service providers.</span></span>  <br/> |
   
```cpp
HRESULT GetTnefStreamCodepage(
  LPSTREAM lpStream,
  ULONG FAR * lpulCodepage,
  ULONG FAR * lpulSubCodepage
);
```

## <a name="parameters"></a><span data-ttu-id="72ca3-112">参数</span><span class="sxs-lookup"><span data-stu-id="72ca3-112">Parameters</span></span>

 <span data-ttu-id="72ca3-113">_lpStream_</span><span class="sxs-lookup"><span data-stu-id="72ca3-113">_lpStream_</span></span>
  
> <span data-ttu-id="72ca3-114">[in]指向提供源 TNEF 流邮件存储 stream 对象 OLE **IStream**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="72ca3-114">[in] Pointer to a storage stream object OLE **IStream** interface providing a source for a TNEF stream message.</span></span> 
    
 <span data-ttu-id="72ca3-115">_lpulCodepage_</span><span class="sxs-lookup"><span data-stu-id="72ca3-115">_lpulCodepage_</span></span>
  
> <span data-ttu-id="72ca3-116">[输出]到流的代码页的指针。</span><span class="sxs-lookup"><span data-stu-id="72ca3-116">[out] Pointer to the code page of the stream.</span></span>
    
 <span data-ttu-id="72ca3-117">_lpulSubCodepage_</span><span class="sxs-lookup"><span data-stu-id="72ca3-117">_lpulSubCodepage_</span></span>
  
> <span data-ttu-id="72ca3-118">[输出]到的流 subcode 页的指针。</span><span class="sxs-lookup"><span data-stu-id="72ca3-118">[out] Pointer to the subcode page of the stream.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="72ca3-119">返回值</span><span class="sxs-lookup"><span data-stu-id="72ca3-119">Return value</span></span>

 <span data-ttu-id="72ca3-120">**S_OK**</span><span class="sxs-lookup"><span data-stu-id="72ca3-120">**S_OK**</span></span>
  
> <span data-ttu-id="72ca3-121">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="72ca3-121">The call succeeded and has returned the expected value or values.</span></span>
    
 <span data-ttu-id="72ca3-122">**MAPI_E_NOT_ENOUGH_DISK**</span><span class="sxs-lookup"><span data-stu-id="72ca3-122">**MAPI_E_NOT_ENOUGH_DISK**</span></span>
  
> <span data-ttu-id="72ca3-123">读取流中的 TNEF 属性时出错。</span><span class="sxs-lookup"><span data-stu-id="72ca3-123">There was an error reading an attribute in the TNEF stream.</span></span>
    
 <span data-ttu-id="72ca3-124">**MAPI_E_CORRUPT_DATA**</span><span class="sxs-lookup"><span data-stu-id="72ca3-124">**MAPI_E_CORRUPT_DATA**</span></span>
  
> <span data-ttu-id="72ca3-125">流未 TNEF 流，或时出错读取 attOemCodepage 属性。</span><span class="sxs-lookup"><span data-stu-id="72ca3-125">Either the stream was not a TNEF stream or there was an error reading the attOemCodepage attribute.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="72ca3-126">说明</span><span class="sxs-lookup"><span data-stu-id="72ca3-126">Remarks</span></span>

<span data-ttu-id="72ca3-127">使用**GetTnefStreamCodepage**函数读取 TNEF 流来确定的代码页和子代码页的**attOemCodepage**属性。</span><span class="sxs-lookup"><span data-stu-id="72ca3-127">Use the **GetTnefStreamCodepage** function to read the **attOemCodepage** attribute of the TNEF stream to determine the code page and subcode page.</span></span> <span data-ttu-id="72ca3-128">如果找不到**attOemCodepage** ， **GetTnefStreamCodepage**返回 437 代码页和 subcode 页为 0。</span><span class="sxs-lookup"><span data-stu-id="72ca3-128">If **attOemCodepage** is not found, **GetTnefStreamCodepage** returns a code page of 437 and a subcode page of 0.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="72ca3-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72ca3-129">See also</span></span>



[<span data-ttu-id="72ca3-130">attOemCodepage</span><span class="sxs-lookup"><span data-stu-id="72ca3-130">attOemCodepage</span></span>](https://msdn.microsoft.com/library/ee158667%28EXCHG.80%29.aspx)
