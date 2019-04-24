---
title: IOlkEnumGetCount
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dd7a7e62-4cf2-bdd3-8a00-4fff5ac575d3
description: 获取枚举数中的帐户数。
ms.openlocfilehash: 8571d5ff01501d980c8b6543607a658ad99085ca
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322013"
---
# <a name="iolkenumgetcount"></a><span data-ttu-id="adf53-103">IOlkEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="adf53-103">IOlkEnum::GetCount</span></span>

<span data-ttu-id="adf53-104">获取枚举数中的帐户数。</span><span class="sxs-lookup"><span data-stu-id="adf53-104">Gets the number of accounts in the enumerator.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="adf53-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="adf53-105">Quick info</span></span>

<span data-ttu-id="adf53-106">请参阅[IOlkEnum](iolkenum.md)。</span><span class="sxs-lookup"><span data-stu-id="adf53-106">See [IOlkEnum](iolkenum.md).</span></span>
  
```cpp
HRESULT IOlkEnum::GetCount ( 
    DWORD *pulCount 
);

```

## <a name="parameters"></a><span data-ttu-id="adf53-107">参数</span><span class="sxs-lookup"><span data-stu-id="adf53-107">Parameters</span></span>

<span data-ttu-id="adf53-108">_pulCount_</span><span class="sxs-lookup"><span data-stu-id="adf53-108">_pulCount_</span></span>
  
> <span data-ttu-id="adf53-109">排除一个指针, 指向要枚举的对象的数目。</span><span class="sxs-lookup"><span data-stu-id="adf53-109">[out] A pointer to the number of objects being enumerated.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="adf53-110">返回值</span><span class="sxs-lookup"><span data-stu-id="adf53-110">Return values</span></span>

<span data-ttu-id="adf53-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="adf53-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="adf53-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adf53-112">See also</span></span>

- [<span data-ttu-id="adf53-113">IOlkEnum::GetNext</span><span class="sxs-lookup"><span data-stu-id="adf53-113">IOlkEnum::GetNext</span></span>](iolkenum-getnext.md)  
- [<span data-ttu-id="adf53-114">IOlkEnum::Reset</span><span class="sxs-lookup"><span data-stu-id="adf53-114">IOlkEnum::Reset</span></span>](iolkenum-reset.md) 
- [<span data-ttu-id="adf53-115">IOlkEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="adf53-115">IOlkEnum::Skip</span></span>](iolkenum-skip.md)

