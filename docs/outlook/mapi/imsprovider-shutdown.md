---
title: IMSProviderShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider.Shutdown
api_type:
- COM
ms.assetid: 9ca1861d-9bc9-485a-9807-a598b869e5a2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 342b87a3a8f0349631e64600e294d4f19ab1099c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589089"
---
# <a name="imsprovidershutdown"></a><span data-ttu-id="720dd-103">IMSProvider::Shutdown</span><span class="sxs-lookup"><span data-stu-id="720dd-103">IMSProvider::Shutdown</span></span>

  
  
<span data-ttu-id="720dd-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="720dd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="720dd-105">关闭中有序的方式的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="720dd-105">Closes a message store provider in an orderly fashion.</span></span>
  
```cpp
HRESULT Shutdown(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="720dd-106">参数</span><span class="sxs-lookup"><span data-stu-id="720dd-106">Parameters</span></span>

 <span data-ttu-id="720dd-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="720dd-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="720dd-108">[in]保留;必须为零的指针。</span><span class="sxs-lookup"><span data-stu-id="720dd-108">[in] Reserved; must be a pointer to zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="720dd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="720dd-109">Return value</span></span>

<span data-ttu-id="720dd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="720dd-110">S_OK</span></span> 
  
> <span data-ttu-id="720dd-111">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="720dd-111">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="720dd-112">注解</span><span class="sxs-lookup"><span data-stu-id="720dd-112">Remarks</span></span>

<span data-ttu-id="720dd-113">MAPI 释放消息存储提供程序对象之前调用**IMSProvider::Shutdown**方法。</span><span class="sxs-lookup"><span data-stu-id="720dd-113">MAPI calls the **IMSProvider::Shutdown** method just before releasing the message store provider object.</span></span> <span data-ttu-id="720dd-114">MAPI 的提供程序调用**关闭**之前释放提供程序的所有登录对象。</span><span class="sxs-lookup"><span data-stu-id="720dd-114">MAPI releases all logon objects for a provider before calling **Shutdown** for that provider.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="720dd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="720dd-115">See also</span></span>



[<span data-ttu-id="720dd-116">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="720dd-116">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

