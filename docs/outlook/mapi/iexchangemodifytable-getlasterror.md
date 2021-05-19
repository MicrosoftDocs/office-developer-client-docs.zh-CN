---
title: IExchangeModifyTableGetLastError
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IExchangeModifyTable.GetLastError
api_type:
- COM
ms.assetid: b850dc08-73c3-4b19-ae29-1892d6a2ff2f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8d5d4895e4440945896ee4f2212c5fca6da8610d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424509"
---
# <a name="iexchangemodifytablegetlasterror"></a><span data-ttu-id="9c10c-103">IExchangeModifyTable::GetLastError</span><span class="sxs-lookup"><span data-stu-id="9c10c-103">IExchangeModifyTable::GetLastError</span></span>

  
  
<span data-ttu-id="9c10c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c10c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9c10c-105">返回有关 table 对象中发生的最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="9c10c-105">Returns information about the last error that occurred in a table object.</span></span>
  
```cpp
HRESULT GetLastError( 
  HRESULT hResult, 
  ULONG ulFlags, 
  LPMAPIERROR FAR * lppMAPIError 
); 
```

## <a name="parameters"></a><span data-ttu-id="9c10c-106">参数</span><span class="sxs-lookup"><span data-stu-id="9c10c-106">Parameters</span></span>

 <span data-ttu-id="9c10c-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="9c10c-107">_hResult_</span></span>
  
> <span data-ttu-id="9c10c-108">[in]失败的方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="9c10c-108">[in] The return value from the method that failed.</span></span>
    
 <span data-ttu-id="9c10c-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9c10c-109">_ulFlags_</span></span>
  
> <span data-ttu-id="9c10c-110">[in]未使用，设置为 0 (零) 。</span><span class="sxs-lookup"><span data-stu-id="9c10c-110">[in] Not used, set to 0 (zero).</span></span>
    
 <span data-ttu-id="9c10c-111">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="9c10c-111">_lppMAPIError_</span></span>
  
> <span data-ttu-id="9c10c-112">[out]指向 MAPI [MAPIERROR](mapierror.md) 结构，其中包含有关表对象发生的最后一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="9c10c-112">[out] Points to a MAPI [MAPIERROR](mapierror.md) structure that contains information about the last error that occurred for a table object.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="9c10c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c10c-113">See also</span></span>



[<span data-ttu-id="9c10c-114">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9c10c-114">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
  
[<span data-ttu-id="9c10c-115">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="9c10c-115">MAPIERROR</span></span>](mapierror.md)


[<span data-ttu-id="9c10c-116">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9c10c-116">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

