---
title: IOlkEnumSkip
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e83e409c-f201-df9d-5e30-879adf15318d
description: 在枚举数中跳过指定数量的帐户。
ms.openlocfilehash: d4063b0ff4852e6932cf50789eea3caa81d4d586
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321985"
---
# <a name="iolkenumskip"></a><span data-ttu-id="a9575-103">IOlkEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="a9575-103">IOlkEnum::Skip</span></span>

<span data-ttu-id="a9575-104">在枚举数中跳过指定数量的帐户。</span><span class="sxs-lookup"><span data-stu-id="a9575-104">Skips a specified number of accounts in the enumerator.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="a9575-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="a9575-105">Quick info</span></span>

<span data-ttu-id="a9575-106">请参阅[IOlkEnum](iolkenum.md)。</span><span class="sxs-lookup"><span data-stu-id="a9575-106">See [IOlkEnum](iolkenum.md).</span></span>
  
```cpp
HRESULT IOlkEnum::Skip(  
    DWORD cSkip 
);
```

## <a name="parameters"></a><span data-ttu-id="a9575-107">参数</span><span class="sxs-lookup"><span data-stu-id="a9575-107">Parameters</span></span>

<span data-ttu-id="a9575-108">_cSkip_</span><span class="sxs-lookup"><span data-stu-id="a9575-108">_cSkip_</span></span>
  
> <span data-ttu-id="a9575-109">实时要跳过的帐户数。</span><span class="sxs-lookup"><span data-stu-id="a9575-109">[in] The number of accounts to be skipped.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="a9575-110">返回值</span><span class="sxs-lookup"><span data-stu-id="a9575-110">Return values</span></span>

<span data-ttu-id="a9575-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="a9575-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a9575-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9575-112">See also</span></span>

- [<span data-ttu-id="a9575-113">IOlkEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="a9575-113">IOlkEnum::GetCount</span></span>](iolkenum-getcount.md) 
- [<span data-ttu-id="a9575-114">IOlkEnum::GetNext</span><span class="sxs-lookup"><span data-stu-id="a9575-114">IOlkEnum::GetNext</span></span>](iolkenum-getnext.md)  
- [<span data-ttu-id="a9575-115">IOlkEnum::Reset</span><span class="sxs-lookup"><span data-stu-id="a9575-115">IOlkEnum::Reset</span></span>](iolkenum-reset.md)

