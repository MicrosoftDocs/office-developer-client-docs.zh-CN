---
title: IOlkErrorUnknownGetLastError
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3f332de3-470d-9bc2-0c65-684bb58bcd7a
description: 获取指定的错误消息字符串。
ms.openlocfilehash: 7b00392cdf65d1d4990f2231769e5126c9ae26dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774366"
---
# <a name="iolkerrorunknowngetlasterror"></a><span data-ttu-id="6adbc-103">IOlkErrorUnknown::GetLastError</span><span class="sxs-lookup"><span data-stu-id="6adbc-103">IOlkErrorUnknown::GetLastError</span></span>

<span data-ttu-id="6adbc-104">获取指定的错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="6adbc-104">Gets a message string for the specified error.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="6adbc-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="6adbc-105">Quick info</span></span>

<span data-ttu-id="6adbc-106">See [IOlkErrorUnknown](iolkerrorunknown.md).</span><span class="sxs-lookup"><span data-stu-id="6adbc-106">See [IOlkErrorUnknown](iolkerrorunknown.md).</span></span>
  
```cpp
HRESULT IOlkErrorUnknown::GetLastError(  
    HRESULT hr, 
    LPWSTR *ppwszError 
); 

```

## <a name="parameters"></a><span data-ttu-id="6adbc-107">参数</span><span class="sxs-lookup"><span data-stu-id="6adbc-107">Parameters</span></span>

<span data-ttu-id="6adbc-108">_hr_</span><span class="sxs-lookup"><span data-stu-id="6adbc-108">_hr_</span></span>
  
> <span data-ttu-id="6adbc-109">[] in要查找的错误代码。</span><span class="sxs-lookup"><span data-stu-id="6adbc-109">[in] The error code to look up.</span></span>
    
<span data-ttu-id="6adbc-110">_ppwszError_</span><span class="sxs-lookup"><span data-stu-id="6adbc-110">_ppwszError_</span></span>
  
> <span data-ttu-id="6adbc-111">[输出]错误消息对应 *人力资源部门*  。</span><span class="sxs-lookup"><span data-stu-id="6adbc-111">[out] The error message that corresponds to  *hr*  .</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="6adbc-112">返回值</span><span class="sxs-lookup"><span data-stu-id="6adbc-112">Return values</span></span>

|<span data-ttu-id="6adbc-113">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="6adbc-113">**HRESULT**</span></span>|<span data-ttu-id="6adbc-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="6adbc-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6adbc-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="6adbc-115">S_OK</span></span>  <br/> |<span data-ttu-id="6adbc-116">调用成功。</span><span class="sxs-lookup"><span data-stu-id="6adbc-116">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="6adbc-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6adbc-117">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="6adbc-118">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="6adbc-118">One or more arguments are invalid.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6adbc-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6adbc-119">See also</span></span>

- [<span data-ttu-id="6adbc-120">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="6adbc-120">Constants (Account management API)</span></span>](constants-account-management-api.md)

