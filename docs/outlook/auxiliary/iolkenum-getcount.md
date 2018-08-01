---
title: IOlkEnumGetCount
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dd7a7e62-4cf2-bdd3-8a00-4fff5ac575d3
description: 获取枚举中的帐户数。
ms.openlocfilehash: dd4152a898bdaa96883bcd27ab3ec0d94e80fd90
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774362"
---
# <a name="iolkenumgetcount"></a><span data-ttu-id="1ffb3-103">IOlkEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="1ffb3-103">IOlkEnum::GetCount</span></span>

<span data-ttu-id="1ffb3-104">获取枚举中的帐户数。</span><span class="sxs-lookup"><span data-stu-id="1ffb3-104">Gets the number of accounts in the enumerator.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="1ffb3-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="1ffb3-105">Quick info</span></span>

<span data-ttu-id="1ffb3-106">请参阅[IOlkEnum](iolkenum.md)。</span><span class="sxs-lookup"><span data-stu-id="1ffb3-106">See [IOlkEnum](iolkenum.md).</span></span>
  
```cpp
HRESULT IOlkEnum::GetCount ( 
    DWORD *pulCount 
);

```

## <a name="parameters"></a><span data-ttu-id="1ffb3-107">参数</span><span class="sxs-lookup"><span data-stu-id="1ffb3-107">Parameters</span></span>

<span data-ttu-id="1ffb3-108">_pulCount_</span><span class="sxs-lookup"><span data-stu-id="1ffb3-108">_pulCount_</span></span>
  
> <span data-ttu-id="1ffb3-109">[输出]一个指向枚举的对象的数目。</span><span class="sxs-lookup"><span data-stu-id="1ffb3-109">[out] A pointer to the number of objects being enumerated.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="1ffb3-110">返回值</span><span class="sxs-lookup"><span data-stu-id="1ffb3-110">Return values</span></span>

<span data-ttu-id="1ffb3-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="1ffb3-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ffb3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ffb3-112">See also</span></span>

- [<span data-ttu-id="1ffb3-113">IOlkEnum::GetNext</span><span class="sxs-lookup"><span data-stu-id="1ffb3-113">IOlkEnum::GetNext</span></span>](iolkenum-getnext.md)  
- [<span data-ttu-id="1ffb3-114">IOlkEnum::Reset</span><span class="sxs-lookup"><span data-stu-id="1ffb3-114">IOlkEnum::Reset</span></span>](iolkenum-reset.md) 
- [<span data-ttu-id="1ffb3-115">IOlkEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="1ffb3-115">IOlkEnum::Skip</span></span>](iolkenum-skip.md)

