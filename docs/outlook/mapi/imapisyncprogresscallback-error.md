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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424929"
---
# <a name="imapisyncprogresscallbackerror"></a><span data-ttu-id="e5f2d-103">IMAPISyncProgressCallback::Error</span><span class="sxs-lookup"><span data-stu-id="e5f2d-103">IMAPISyncProgressCallback::Error</span></span>

  
  
<span data-ttu-id="e5f2d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e5f2d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e5f2d-105">提供在"发送/接收"对话框中显示的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5f2d-105">Provides details that are displayed in the Send/Receive dialog.</span></span> <span data-ttu-id="e5f2d-106">如果在同步过程中遇到错误，存储提供程序将调用此函数。</span><span class="sxs-lookup"><span data-stu-id="e5f2d-106">If errors are encountered during synchronization, the store provider calls this function.</span></span>
  
```cpp
HRESULT Error(
  HRESULT hResult,
  const WCHAR *pwcszErrorStr
);
```

## <a name="parameters"></a><span data-ttu-id="e5f2d-107">参数</span><span class="sxs-lookup"><span data-stu-id="e5f2d-107">Parameters</span></span>

 <span data-ttu-id="e5f2d-108">**hResult**</span><span class="sxs-lookup"><span data-stu-id="e5f2d-108">**hResult**</span></span>
  
> <span data-ttu-id="e5f2d-109">错误或警告的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="e5f2d-109">The HRESULT of the error or warning.</span></span>
    
 <span data-ttu-id="e5f2d-110">**pwcszErrorStr**</span><span class="sxs-lookup"><span data-stu-id="e5f2d-110">**pwcszErrorStr**</span></span>
  
> <span data-ttu-id="e5f2d-111">指向与要显示的错误相关联的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="e5f2d-111">A pointer to the string associated with the error to be displayed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e5f2d-112">返回值</span><span class="sxs-lookup"><span data-stu-id="e5f2d-112">Return value</span></span>

<span data-ttu-id="e5f2d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5f2d-113">S_OK</span></span> 
  
> <span data-ttu-id="e5f2d-114">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="e5f2d-114">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e5f2d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5f2d-115">See also</span></span>



[<span data-ttu-id="e5f2d-116">IMAPISyncProgressCallback : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e5f2d-116">IMAPISyncProgressCallback : IUnknown</span></span>](imapisyncprogresscallbackiunknown.md)

