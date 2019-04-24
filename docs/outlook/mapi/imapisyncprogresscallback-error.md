---
title: IMAPISyncProgressCallbackError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISyncProgressCallback.Error
api_type:
- COM
ms.assetid: 4860992d-65d7-4cb0-a874-ceccb153dbac
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 80010ca19999ba519f051e914f02f240abb524e2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341333"
---
# <a name="imapisyncprogresscallbackerror"></a><span data-ttu-id="a356c-103">IMAPISyncProgressCallback::Error</span><span class="sxs-lookup"><span data-stu-id="a356c-103">IMAPISyncProgressCallback::Error</span></span>

  
  
<span data-ttu-id="a356c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a356c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a356c-105">提供在 "发送/接收" 对话框中显示的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a356c-105">Provides details that are displayed in the Send/Receive dialog.</span></span> <span data-ttu-id="a356c-106">如果在同步过程中遇到错误, 则存储提供程序将调用此函数。</span><span class="sxs-lookup"><span data-stu-id="a356c-106">If errors are encountered during synchronization, the store provider calls this function.</span></span>
  
```cpp
HRESULT Error(
  HRESULT hResult,
  const WCHAR *pwcszErrorStr
);
```

## <a name="parameters"></a><span data-ttu-id="a356c-107">参数</span><span class="sxs-lookup"><span data-stu-id="a356c-107">Parameters</span></span>

 <span data-ttu-id="a356c-108">**hResult**</span><span class="sxs-lookup"><span data-stu-id="a356c-108">**hResult**</span></span>
  
> <span data-ttu-id="a356c-109">错误或警告的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a356c-109">The HRESULT of the error or warning.</span></span>
    
 <span data-ttu-id="a356c-110">**pwcszErrorStr**</span><span class="sxs-lookup"><span data-stu-id="a356c-110">**pwcszErrorStr**</span></span>
  
> <span data-ttu-id="a356c-111">指向与要显示的错误关联的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="a356c-111">A pointer to the string associated with the error to be displayed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a356c-112">返回值</span><span class="sxs-lookup"><span data-stu-id="a356c-112">Return value</span></span>

<span data-ttu-id="a356c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a356c-113">S_OK</span></span> 
  
> <span data-ttu-id="a356c-114">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="a356c-114">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a356c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a356c-115">See also</span></span>



[<span data-ttu-id="a356c-116">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a356c-116">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)

