---
title: IEnumFBBlockClone
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5af36a87-e782-df63-4190-a608758fef50
description: 创建一份枚举数，使用相同的时间限制，但设置光标到枚举的开头。
ms.openlocfilehash: 51503be2091fa01da6f636bf6944274068617f05
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774197"
---
# <a name="ienumfbblockclone"></a><span data-ttu-id="72ab8-103">IEnumFBBlock::Clone</span><span class="sxs-lookup"><span data-stu-id="72ab8-103">IEnumFBBlock::Clone</span></span>

<span data-ttu-id="72ab8-104">创建一份枚举数，使用相同的时间限制，但设置光标到枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="72ab8-104">Creates a copy of the enumerator, using the same time restriction but setting the cursor to the beginning of the enumerator.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="72ab8-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="72ab8-105">Quick info</span></span>

<span data-ttu-id="72ab8-106">请参阅[IEnumFBBlock](ienumfbblock.md)。</span><span class="sxs-lookup"><span data-stu-id="72ab8-106">See [IEnumFBBlock](ienumfbblock.md).</span></span>
  
```cpp
HRESULT Clone(  
     IEnumFBBlock **ppclone 
); 
```

## <a name="parameters"></a><span data-ttu-id="72ab8-107">参数</span><span class="sxs-lookup"><span data-stu-id="72ab8-107">Parameters</span></span>

<span data-ttu-id="72ab8-108">_ppclone_</span><span class="sxs-lookup"><span data-stu-id="72ab8-108">_ppclone_</span></span>
  
> <span data-ttu-id="72ab8-109">[输出]A 到指针的指针到[IEnumFBBlock](ienumfbblock.md)接口的副本。</span><span class="sxs-lookup"><span data-stu-id="72ab8-109">[out] A pointer to pointer to the copy of [IEnumFBBlock](ienumfbblock.md) interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="72ab8-110">返回值</span><span class="sxs-lookup"><span data-stu-id="72ab8-110">Return values</span></span>

|<span data-ttu-id="72ab8-111">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="72ab8-111">**HRESULT**</span></span>|<span data-ttu-id="72ab8-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="72ab8-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="72ab8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="72ab8-113">S_OK</span></span>  <br/> |<span data-ttu-id="72ab8-114">调用成功。</span><span class="sxs-lookup"><span data-stu-id="72ab8-114">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="72ab8-115">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="72ab8-115">E_OUTOFMEMORY</span></span>  <br/> |<span data-ttu-id="72ab8-116">没有进行复制的内存不足。</span><span class="sxs-lookup"><span data-stu-id="72ab8-116">There is insufficient memory for making the copy.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="72ab8-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72ab8-117">See also</span></span>

- [<span data-ttu-id="72ab8-118">常量 (忙/闲 API)</span><span class="sxs-lookup"><span data-stu-id="72ab8-118">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)
- [<span data-ttu-id="72ab8-119">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="72ab8-119">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)  
- [<span data-ttu-id="72ab8-120">IEnumFBBlock::Reset</span><span class="sxs-lookup"><span data-stu-id="72ab8-120">IEnumFBBlock::Reset</span></span>](ienumfbblock-reset.md)  
- [<span data-ttu-id="72ab8-121">IEnumFBBlock::Restrict</span><span class="sxs-lookup"><span data-stu-id="72ab8-121">IEnumFBBlock::Restrict</span></span>](ienumfbblock-restrict.md)  
- [<span data-ttu-id="72ab8-122">IEnumFBBlock::Skip</span><span class="sxs-lookup"><span data-stu-id="72ab8-122">IEnumFBBlock::Skip</span></span>](ienumfbblock-skip.md)
