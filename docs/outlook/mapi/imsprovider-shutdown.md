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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 77688f8a09c1d990201a247a3c4e3a11ba0963b3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438622"
---
# <a name="imsprovidershutdown"></a><span data-ttu-id="53090-103">IMSProvider::Shutdown</span><span class="sxs-lookup"><span data-stu-id="53090-103">IMSProvider::Shutdown</span></span>

  
  
<span data-ttu-id="53090-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53090-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53090-105">以有序方式关闭邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="53090-105">Closes a message store provider in an orderly fashion.</span></span>
  
```cpp
HRESULT Shutdown(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="53090-106">参数</span><span class="sxs-lookup"><span data-stu-id="53090-106">Parameters</span></span>

 <span data-ttu-id="53090-107">_lpulFlags_</span><span class="sxs-lookup"><span data-stu-id="53090-107">_lpulFlags_</span></span>
  
> <span data-ttu-id="53090-108">[in]保留;必须是指向零的指针。</span><span class="sxs-lookup"><span data-stu-id="53090-108">[in] Reserved; must be a pointer to zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="53090-109">返回值</span><span class="sxs-lookup"><span data-stu-id="53090-109">Return value</span></span>

<span data-ttu-id="53090-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="53090-110">S_OK</span></span> 
  
> <span data-ttu-id="53090-111">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="53090-111">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="53090-112">备注</span><span class="sxs-lookup"><span data-stu-id="53090-112">Remarks</span></span>

<span data-ttu-id="53090-113">MAPI 在释放消息存储提供程序对象之前调用 **IMSProvider：：Shutdown** 方法。</span><span class="sxs-lookup"><span data-stu-id="53090-113">MAPI calls the **IMSProvider::Shutdown** method just before releasing the message store provider object.</span></span> <span data-ttu-id="53090-114">MAPI 先释放提供程序的所有登录对象，然后再调用 **该提供程序的 Shutdown。**</span><span class="sxs-lookup"><span data-stu-id="53090-114">MAPI releases all logon objects for a provider before calling **Shutdown** for that provider.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="53090-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53090-115">See also</span></span>



[<span data-ttu-id="53090-116">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="53090-116">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

