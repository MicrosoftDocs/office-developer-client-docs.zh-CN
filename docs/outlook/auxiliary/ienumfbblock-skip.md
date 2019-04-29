---
title: IEnumFBBlockSkip
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 70fbdb41-46ea-d016-25a2-37e94962095d
description: 跳过指定数量的忙/闲数据块。
ms.openlocfilehash: cf8ae18b5ed2c24a48d44d9e8d461da7d95054d2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425720"
---
# <a name="ienumfbblockskip"></a><span data-ttu-id="84ef5-103">IEnumFBBlock::Skip</span><span class="sxs-lookup"><span data-stu-id="84ef5-103">IEnumFBBlock::Skip</span></span>

<span data-ttu-id="84ef5-104">跳过指定数量的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="84ef5-104">Skips a specified number of blocks of free/busy data.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="84ef5-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="84ef5-105">Quick info</span></span>

<span data-ttu-id="84ef5-106">请参阅[IEnumFBBlock](ienumfbblock.md)。</span><span class="sxs-lookup"><span data-stu-id="84ef5-106">See [IEnumFBBlock](ienumfbblock.md).</span></span>
  
```cpp
HRESULT Skip(  
    LONG celt 
);
```

## <a name="parameters"></a><span data-ttu-id="84ef5-107">参数</span><span class="sxs-lookup"><span data-stu-id="84ef5-107">Parameters</span></span>

<span data-ttu-id="84ef5-108">_celt_</span><span class="sxs-lookup"><span data-stu-id="84ef5-108">_celt_</span></span>
  
>  <span data-ttu-id="84ef5-109">实时要跳过的忙/闲块的数量。</span><span class="sxs-lookup"><span data-stu-id="84ef5-109">[in] The number of free/busy blocks to skip.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="84ef5-110">返回值</span><span class="sxs-lookup"><span data-stu-id="84ef5-110">Return values</span></span>

<span data-ttu-id="84ef5-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="84ef5-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="84ef5-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84ef5-112">See also</span></span>

- [<span data-ttu-id="84ef5-113">IEnumFBBlock::Clone</span><span class="sxs-lookup"><span data-stu-id="84ef5-113">IEnumFBBlock::Clone</span></span>](ienumfbblock-clone.md)  
- [<span data-ttu-id="84ef5-114">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="84ef5-114">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)  
- [<span data-ttu-id="84ef5-115">IEnumFBBlock::Reset</span><span class="sxs-lookup"><span data-stu-id="84ef5-115">IEnumFBBlock::Reset</span></span>](ienumfbblock-reset.md)  
- [<span data-ttu-id="84ef5-116">IEnumFBBlock::Restrict</span><span class="sxs-lookup"><span data-stu-id="84ef5-116">IEnumFBBlock::Restrict</span></span>](ienumfbblock-restrict.md)

