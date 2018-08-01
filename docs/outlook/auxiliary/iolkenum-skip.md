---
title: IOlkEnumSkip
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e83e409c-f201-df9d-5e30-879adf15318d
description: 跳过指定的数量的枚举中的帐户。
ms.openlocfilehash: 2791f1204cedf5e91d13923e50dfc45b981b7e26
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774355"
---
# <a name="iolkenumskip"></a><span data-ttu-id="d678c-103">IOlkEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="d678c-103">IOlkEnum::Skip</span></span>

<span data-ttu-id="d678c-104">跳过指定的数量的枚举中的帐户。</span><span class="sxs-lookup"><span data-stu-id="d678c-104">Skips a specified number of accounts in the enumerator.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d678c-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d678c-105">Quick info</span></span>

<span data-ttu-id="d678c-106">请参阅[IOlkEnum](iolkenum.md)。</span><span class="sxs-lookup"><span data-stu-id="d678c-106">See [IOlkEnum](iolkenum.md).</span></span>
  
```cpp
HRESULT IOlkEnum::Skip(  
    DWORD cSkip 
);
```

## <a name="parameters"></a><span data-ttu-id="d678c-107">参数</span><span class="sxs-lookup"><span data-stu-id="d678c-107">Parameters</span></span>

<span data-ttu-id="d678c-108">_cSkip_</span><span class="sxs-lookup"><span data-stu-id="d678c-108">_cSkip_</span></span>
  
> <span data-ttu-id="d678c-109">[in]要跳过的帐户数。</span><span class="sxs-lookup"><span data-stu-id="d678c-109">[in] The number of accounts to be skipped.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="d678c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d678c-110">Return values</span></span>

<span data-ttu-id="d678c-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="d678c-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d678c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d678c-112">See also</span></span>

- [<span data-ttu-id="d678c-113">IOlkEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="d678c-113">IOlkEnum::GetCount</span></span>](iolkenum-getcount.md) 
- [<span data-ttu-id="d678c-114">IOlkEnum::GetNext</span><span class="sxs-lookup"><span data-stu-id="d678c-114">IOlkEnum::GetNext</span></span>](iolkenum-getnext.md)  
- [<span data-ttu-id="d678c-115">IOlkEnum::Reset</span><span class="sxs-lookup"><span data-stu-id="d678c-115">IOlkEnum::Reset</span></span>](iolkenum-reset.md)

