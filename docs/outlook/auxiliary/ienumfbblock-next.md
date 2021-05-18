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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422136"
---
# <a name="ienumfbblocknext"></a><span data-ttu-id="a76e8-103">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="a76e8-103">IEnumFBBlock::Next</span></span>

<span data-ttu-id="a76e8-104">获取枚举中的下一个指定数量的忙/闲数据块。</span><span class="sxs-lookup"><span data-stu-id="a76e8-104">Gets the next specified number of blocks of free/busy data in an enumeration.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="a76e8-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="a76e8-105">Quick info</span></span>

<span data-ttu-id="a76e8-106">请参阅 [IEnumFBBlock](ienumfbblock.md)。</span><span class="sxs-lookup"><span data-stu-id="a76e8-106">See [IEnumFBBlock](ienumfbblock.md).</span></span>
  
```cpp
HRESULT Next(  
        LONG celt,
        FBBlock_1 *pblk,
        LONG *pcfetch
);
```

## <a name="parameters"></a><span data-ttu-id="a76e8-107">参数</span><span class="sxs-lookup"><span data-stu-id="a76e8-107">Parameters</span></span>

<span data-ttu-id="a76e8-108">_celt_</span><span class="sxs-lookup"><span data-stu-id="a76e8-108">_celt_</span></span>
  
> <span data-ttu-id="a76e8-109">[in]pblk 中要检索的忙/闲  *数据块*  数。</span><span class="sxs-lookup"><span data-stu-id="a76e8-109">[in] The number of free/busy data blocks in  *pblk*  to retrieve.</span></span> 
    
<span data-ttu-id="a76e8-110">_pblk_</span><span class="sxs-lookup"><span data-stu-id="a76e8-110">_pblk_</span></span>
  
> <span data-ttu-id="a76e8-111">[in]指向忙/闲块数组的指针。</span><span class="sxs-lookup"><span data-stu-id="a76e8-111">[in] A pointer to an array of free/busy blocks.</span></span> <span data-ttu-id="a76e8-112">数组分配了大小  *为 celt*  。</span><span class="sxs-lookup"><span data-stu-id="a76e8-112">The array is allocated a size of  *celt*  .</span></span> <span data-ttu-id="a76e8-113">请求的忙/闲块将在此数组中返回。</span><span class="sxs-lookup"><span data-stu-id="a76e8-113">The requested free/busy blocks are returned in this array.</span></span> 
    
<span data-ttu-id="a76e8-114">_pcfetch_</span><span class="sxs-lookup"><span data-stu-id="a76e8-114">_pcfetch_</span></span>
  
> <span data-ttu-id="a76e8-115">[out]pblk 中实际返回的忙/闲块  *数*  。</span><span class="sxs-lookup"><span data-stu-id="a76e8-115">[out] The number of free/busy blocks actually returned in  *pblk*  .</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="a76e8-116">返回值</span><span class="sxs-lookup"><span data-stu-id="a76e8-116">Return values</span></span>

|<span data-ttu-id="a76e8-117">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="a76e8-117">**HRESULT**</span></span>|<span data-ttu-id="a76e8-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="a76e8-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a76e8-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a76e8-119">S_OK</span></span>  <br/> |<span data-ttu-id="a76e8-120">已返回请求的块数。</span><span class="sxs-lookup"><span data-stu-id="a76e8-120">The requested number of blocks has been returned.</span></span>  <br/> |
|<span data-ttu-id="a76e8-121">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a76e8-121">S_FALSE</span></span>  <br/> |<span data-ttu-id="a76e8-122">请求的块数尚未返回。</span><span class="sxs-lookup"><span data-stu-id="a76e8-122">The requested number of blocks has not been returned.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a76e8-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a76e8-123">See also</span></span>

- [<span data-ttu-id="a76e8-124">常量 (忙/闲 API) </span><span class="sxs-lookup"><span data-stu-id="a76e8-124">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)  
- [<span data-ttu-id="a76e8-125">FBBlock_1</span><span class="sxs-lookup"><span data-stu-id="a76e8-125">FBBlock_1</span></span>](fbblock_1.md)  
- [<span data-ttu-id="a76e8-126">IEnumFBBlock::Clone</span><span class="sxs-lookup"><span data-stu-id="a76e8-126">IEnumFBBlock::Clone</span></span>](ienumfbblock-clone.md)  
- [<span data-ttu-id="a76e8-127">IEnumFBBlock::Reset</span><span class="sxs-lookup"><span data-stu-id="a76e8-127">IEnumFBBlock::Reset</span></span>](ienumfbblock-reset.md)  
- [<span data-ttu-id="a76e8-128">IEnumFBBlock::Restrict</span><span class="sxs-lookup"><span data-stu-id="a76e8-128">IEnumFBBlock::Restrict</span></span>](ienumfbblock-restrict.md)  
- [<span data-ttu-id="a76e8-129">IEnumFBBlock::Skip</span><span class="sxs-lookup"><span data-stu-id="a76e8-129">IEnumFBBlock::Skip</span></span>](ienumfbblock-skip.md)

