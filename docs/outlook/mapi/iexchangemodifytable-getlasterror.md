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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f0d2ad118346dd06788af972b64b10d6f6f6d0fc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594290"
---
# <a name="iexchangemodifytablegetlasterror"></a><span data-ttu-id="f0eb8-103">IExchangeModifyTable::GetLastError</span><span class="sxs-lookup"><span data-stu-id="f0eb8-103">IExchangeModifyTable::GetLastError</span></span>

  
  
<span data-ttu-id="f0eb8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f0eb8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f0eb8-105">返回一个 table 对象中上次发生的错误有关的信息。</span><span class="sxs-lookup"><span data-stu-id="f0eb8-105">Returns information about the last error that occurred in a table object.</span></span>
  
```cpp
HRESULT GetLastError( 
  HRESULT hResult, 
  ULONG ulFlags, 
  LPMAPIERROR FAR * lppMAPIError 
); 
```

## <a name="parameters"></a><span data-ttu-id="f0eb8-106">参数</span><span class="sxs-lookup"><span data-stu-id="f0eb8-106">Parameters</span></span>

 <span data-ttu-id="f0eb8-107">_hResult_</span><span class="sxs-lookup"><span data-stu-id="f0eb8-107">_hResult_</span></span>
  
> <span data-ttu-id="f0eb8-108">[in]从失败的方法返回的值。</span><span class="sxs-lookup"><span data-stu-id="f0eb8-108">[in] The return value from the method that failed.</span></span>
    
 <span data-ttu-id="f0eb8-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f0eb8-109">_ulFlags_</span></span>
  
> <span data-ttu-id="f0eb8-110">[in]未使用，设置为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="f0eb8-110">[in] Not used, set to 0 (zero).</span></span>
    
 <span data-ttu-id="f0eb8-111">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="f0eb8-111">_lppMAPIError_</span></span>
  
> <span data-ttu-id="f0eb8-112">[输出]指向 MAPI [MAPIERROR](mapierror.md)结构，其中包含有关最后一个 table 对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="f0eb8-112">[out] Points to a MAPI [MAPIERROR](mapierror.md) structure that contains information about the last error that occurred for a table object.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="f0eb8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0eb8-113">See also</span></span>



[<span data-ttu-id="f0eb8-114">IExchangeModifyTable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f0eb8-114">IExchangeModifyTable : IUnknown</span></span>](iexchangemodifytableiunknown.md)
  
[<span data-ttu-id="f0eb8-115">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="f0eb8-115">MAPIERROR</span></span>](mapierror.md)


[<span data-ttu-id="f0eb8-116">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f0eb8-116">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

