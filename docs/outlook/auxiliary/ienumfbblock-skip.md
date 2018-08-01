---
title: IEnumFBBlockSkip
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 70fbdb41-46ea-d016-25a2-37e94962095d
description: 跳过指定的数量的忙/闲数据块。
ms.openlocfilehash: 63f699d09e143a879702e8dc76beb8a969a77b82
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774196"
---
# <a name="ienumfbblockskip"></a><span data-ttu-id="d0f98-103">IEnumFBBlock::Skip</span><span class="sxs-lookup"><span data-stu-id="d0f98-103">IEnumFBBlock::Skip</span></span>

<span data-ttu-id="d0f98-104">跳过指定的数量的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="d0f98-104">Skips a specified number of blocks of free/busy data.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d0f98-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="d0f98-105">Quick info</span></span>

<span data-ttu-id="d0f98-106">请参阅[IEnumFBBlock](ienumfbblock.md)。</span><span class="sxs-lookup"><span data-stu-id="d0f98-106">See [IEnumFBBlock](ienumfbblock.md).</span></span>
  
```cpp
HRESULT Skip(  
    LONG celt 
);
```

## <a name="parameters"></a><span data-ttu-id="d0f98-107">参数</span><span class="sxs-lookup"><span data-stu-id="d0f98-107">Parameters</span></span>

<span data-ttu-id="d0f98-108">_celt_</span><span class="sxs-lookup"><span data-stu-id="d0f98-108">_celt_</span></span>
  
>  <span data-ttu-id="d0f98-109">[in]忙/闲块，以跳过数。</span><span class="sxs-lookup"><span data-stu-id="d0f98-109">[in] The number of free/busy blocks to skip.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="d0f98-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d0f98-110">Return values</span></span>

<span data-ttu-id="d0f98-111">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="d0f98-111">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d0f98-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0f98-112">See also</span></span>

- [<span data-ttu-id="d0f98-113">IEnumFBBlock::Clone</span><span class="sxs-lookup"><span data-stu-id="d0f98-113">IEnumFBBlock::Clone</span></span>](ienumfbblock-clone.md)  
- [<span data-ttu-id="d0f98-114">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="d0f98-114">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)  
- [<span data-ttu-id="d0f98-115">IEnumFBBlock::Reset</span><span class="sxs-lookup"><span data-stu-id="d0f98-115">IEnumFBBlock::Reset</span></span>](ienumfbblock-reset.md)  
- [<span data-ttu-id="d0f98-116">IEnumFBBlock::Restrict</span><span class="sxs-lookup"><span data-stu-id="d0f98-116">IEnumFBBlock::Restrict</span></span>](ienumfbblock-restrict.md)

