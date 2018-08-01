---
title: IEnumFBBlockNext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b46358c-bcab-f097-8746-fabfd4722b3c
description: 获取枚举中的下一个指定的数量的忙/闲数据块。
ms.openlocfilehash: ec366cf102d3c75487f9485cfae7764d68695f10
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774203"
---
# <a name="ienumfbblocknext"></a><span data-ttu-id="0767b-103">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="0767b-103">IEnumFBBlock::Next</span></span>

<span data-ttu-id="0767b-104">获取枚举中的下一个指定的数量的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="0767b-104">Gets the next specified number of blocks of free/busy data in an enumeration.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="0767b-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="0767b-105">Quick info</span></span>

<span data-ttu-id="0767b-106">请参阅[IEnumFBBlock](ienumfbblock.md)。</span><span class="sxs-lookup"><span data-stu-id="0767b-106">See [IEnumFBBlock](ienumfbblock.md).</span></span>
  
```cpp
HRESULT Next(  
        LONG celt,
        FBBlock_1 *pblk,
        LONG *pcfetch
);
```

## <a name="parameters"></a><span data-ttu-id="0767b-107">参数</span><span class="sxs-lookup"><span data-stu-id="0767b-107">Parameters</span></span>

<span data-ttu-id="0767b-108">_celt_</span><span class="sxs-lookup"><span data-stu-id="0767b-108">_celt_</span></span>
  
> <span data-ttu-id="0767b-109">[in]中*pblk*检索块的忙/闲数据。</span><span class="sxs-lookup"><span data-stu-id="0767b-109">[in] The number of free/busy data blocks in  *pblk*  to retrieve.</span></span> 
    
<span data-ttu-id="0767b-110">_pblk_</span><span class="sxs-lookup"><span data-stu-id="0767b-110">_pblk_</span></span>
  
> <span data-ttu-id="0767b-111">[in]一个指向忙/闲块的数组。</span><span class="sxs-lookup"><span data-stu-id="0767b-111">[in] A pointer to an array of free/busy blocks.</span></span> <span data-ttu-id="0767b-112">该数组被分配*celt*的大小。</span><span class="sxs-lookup"><span data-stu-id="0767b-112">The array is allocated a size of  *celt*  .</span></span> <span data-ttu-id="0767b-113">该数组中返回的请求的忙/闲基块。</span><span class="sxs-lookup"><span data-stu-id="0767b-113">The requested free/busy blocks are returned in this array.</span></span> 
    
<span data-ttu-id="0767b-114">_pcfetch_</span><span class="sxs-lookup"><span data-stu-id="0767b-114">_pcfetch_</span></span>
  
> <span data-ttu-id="0767b-115">[输出]忙/闲块中*pblk*实际返回数。</span><span class="sxs-lookup"><span data-stu-id="0767b-115">[out] The number of free/busy blocks actually returned in  *pblk*  .</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="0767b-116">返回值</span><span class="sxs-lookup"><span data-stu-id="0767b-116">Return values</span></span>

|<span data-ttu-id="0767b-117">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="0767b-117">**HRESULT**</span></span>|<span data-ttu-id="0767b-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="0767b-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0767b-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="0767b-119">S_OK</span></span>  <br/> |<span data-ttu-id="0767b-120">已返回块的请求的数。</span><span class="sxs-lookup"><span data-stu-id="0767b-120">The requested number of blocks has been returned.</span></span>  <br/> |
|<span data-ttu-id="0767b-121">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0767b-121">S_FALSE</span></span>  <br/> |<span data-ttu-id="0767b-122">不返回了块的请求的数。</span><span class="sxs-lookup"><span data-stu-id="0767b-122">The requested number of blocks has not been returned.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0767b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0767b-123">See also</span></span>

- [<span data-ttu-id="0767b-124">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="0767b-124">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)  
- [<span data-ttu-id="0767b-125">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="0767b-125">FBBlock_1</span></span>](fbblock_1.md)  
- [<span data-ttu-id="0767b-126">IEnumFBBlock::Clone</span><span class="sxs-lookup"><span data-stu-id="0767b-126">IEnumFBBlock::Clone</span></span>](ienumfbblock-clone.md)  
- [<span data-ttu-id="0767b-127">IEnumFBBlock::Reset</span><span class="sxs-lookup"><span data-stu-id="0767b-127">IEnumFBBlock::Reset</span></span>](ienumfbblock-reset.md)  
- [<span data-ttu-id="0767b-128">IEnumFBBlock::Restrict</span><span class="sxs-lookup"><span data-stu-id="0767b-128">IEnumFBBlock::Restrict</span></span>](ienumfbblock-restrict.md)  
- [<span data-ttu-id="0767b-129">IEnumFBBlock::Skip</span><span class="sxs-lookup"><span data-stu-id="0767b-129">IEnumFBBlock::Skip</span></span>](ienumfbblock-skip.md)

