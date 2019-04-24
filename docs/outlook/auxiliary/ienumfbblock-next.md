---
title: IEnumFBBlockNext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b46358c-bcab-f097-8746-fabfd4722b3c
description: 获取枚举中的下一个指定数量的忙/闲数据块。
ms.openlocfilehash: f6ec49a9bac6bcf4fff67991d55c7656f6c8cce2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319591"
---
# <a name="ienumfbblocknext"></a><span data-ttu-id="b319b-103">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="b319b-103">IEnumFBBlock::Next</span></span>

<span data-ttu-id="b319b-104">获取枚举中的下一个指定数量的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="b319b-104">Gets the next specified number of blocks of free/busy data in an enumeration.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b319b-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="b319b-105">Quick info</span></span>

<span data-ttu-id="b319b-106">请参阅[IEnumFBBlock](ienumfbblock.md)。</span><span class="sxs-lookup"><span data-stu-id="b319b-106">See [IEnumFBBlock](ienumfbblock.md).</span></span>
  
```cpp
HRESULT Next(  
        LONG celt,
        FBBlock_1 *pblk,
        LONG *pcfetch
);
```

## <a name="parameters"></a><span data-ttu-id="b319b-107">参数</span><span class="sxs-lookup"><span data-stu-id="b319b-107">Parameters</span></span>

<span data-ttu-id="b319b-108">_celt_</span><span class="sxs-lookup"><span data-stu-id="b319b-108">_celt_</span></span>
  
> <span data-ttu-id="b319b-109">实时*pblk*中要检索的忙/闲数据块的数量。</span><span class="sxs-lookup"><span data-stu-id="b319b-109">[in] The number of free/busy data blocks in  *pblk*  to retrieve.</span></span> 
    
<span data-ttu-id="b319b-110">_pblk_</span><span class="sxs-lookup"><span data-stu-id="b319b-110">_pblk_</span></span>
  
> <span data-ttu-id="b319b-111">实时指向一组空闲/忙碌块的指针。</span><span class="sxs-lookup"><span data-stu-id="b319b-111">[in] A pointer to an array of free/busy blocks.</span></span> <span data-ttu-id="b319b-112">数组分配的大小为*celt* 。</span><span class="sxs-lookup"><span data-stu-id="b319b-112">The array is allocated a size of  *celt*  .</span></span> <span data-ttu-id="b319b-113">在此数组中返回请求的忙/闲块。</span><span class="sxs-lookup"><span data-stu-id="b319b-113">The requested free/busy blocks are returned in this array.</span></span> 
    
<span data-ttu-id="b319b-114">_pcfetch_</span><span class="sxs-lookup"><span data-stu-id="b319b-114">_pcfetch_</span></span>
  
> <span data-ttu-id="b319b-115">排除*pblk*中实际返回的忙/闲块的数量。</span><span class="sxs-lookup"><span data-stu-id="b319b-115">[out] The number of free/busy blocks actually returned in  *pblk*  .</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="b319b-116">返回值</span><span class="sxs-lookup"><span data-stu-id="b319b-116">Return values</span></span>

|<span data-ttu-id="b319b-117">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="b319b-117">**HRESULT**</span></span>|<span data-ttu-id="b319b-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="b319b-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b319b-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="b319b-119">S_OK</span></span>  <br/> |<span data-ttu-id="b319b-120">已返回请求的块数。</span><span class="sxs-lookup"><span data-stu-id="b319b-120">The requested number of blocks has been returned.</span></span>  <br/> |
|<span data-ttu-id="b319b-121">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b319b-121">S_FALSE</span></span>  <br/> |<span data-ttu-id="b319b-122">尚未返回请求数量的块数。</span><span class="sxs-lookup"><span data-stu-id="b319b-122">The requested number of blocks has not been returned.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b319b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b319b-123">See also</span></span>

- [<span data-ttu-id="b319b-124">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="b319b-124">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)  
- [<span data-ttu-id="b319b-125">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="b319b-125">FBBlock_1</span></span>](fbblock_1.md)  
- [<span data-ttu-id="b319b-126">IEnumFBBlock::Clone</span><span class="sxs-lookup"><span data-stu-id="b319b-126">IEnumFBBlock::Clone</span></span>](ienumfbblock-clone.md)  
- [<span data-ttu-id="b319b-127">IEnumFBBlock::Reset</span><span class="sxs-lookup"><span data-stu-id="b319b-127">IEnumFBBlock::Reset</span></span>](ienumfbblock-reset.md)  
- [<span data-ttu-id="b319b-128">IEnumFBBlock::Restrict</span><span class="sxs-lookup"><span data-stu-id="b319b-128">IEnumFBBlock::Restrict</span></span>](ienumfbblock-restrict.md)  
- [<span data-ttu-id="b319b-129">IEnumFBBlock::Skip</span><span class="sxs-lookup"><span data-stu-id="b319b-129">IEnumFBBlock::Skip</span></span>](ienumfbblock-skip.md)

