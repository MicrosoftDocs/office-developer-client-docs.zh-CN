---
title: IEnumFBBlockClone
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5af36a87-e782-df63-4190-a608758fef50
description: 使用相同的时间限制创建枚举器的副本，但将光标设置为枚举器开头。
ms.openlocfilehash: 1a279430bf6a29611fa223bebbf8023c34967139
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413400"
---
# <a name="ienumfbblockclone"></a><span data-ttu-id="1474c-103">IEnumFBBlock::Clone</span><span class="sxs-lookup"><span data-stu-id="1474c-103">IEnumFBBlock::Clone</span></span>

<span data-ttu-id="1474c-104">使用相同的时间限制创建枚举器的副本，但将光标设置为枚举器开头。</span><span class="sxs-lookup"><span data-stu-id="1474c-104">Creates a copy of the enumerator, using the same time restriction but setting the cursor to the beginning of the enumerator.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="1474c-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="1474c-105">Quick info</span></span>

<span data-ttu-id="1474c-106">请参阅 [IEnumFBBlock](ienumfbblock.md)。</span><span class="sxs-lookup"><span data-stu-id="1474c-106">See [IEnumFBBlock](ienumfbblock.md).</span></span>
  
```cpp
HRESULT Clone(  
     IEnumFBBlock **ppclone 
); 
```

## <a name="parameters"></a><span data-ttu-id="1474c-107">参数</span><span class="sxs-lookup"><span data-stu-id="1474c-107">Parameters</span></span>

<span data-ttu-id="1474c-108">_ppclone_</span><span class="sxs-lookup"><span data-stu-id="1474c-108">_ppclone_</span></span>
  
> <span data-ttu-id="1474c-109">[out]指向指向 [IEnumFBBlock 接口副本的指针](ienumfbblock.md) 的指针。</span><span class="sxs-lookup"><span data-stu-id="1474c-109">[out] A pointer to pointer to the copy of [IEnumFBBlock](ienumfbblock.md) interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="1474c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="1474c-110">Return values</span></span>

|<span data-ttu-id="1474c-111">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="1474c-111">**HRESULT**</span></span>|<span data-ttu-id="1474c-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="1474c-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1474c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1474c-113">S_OK</span></span>  <br/> |<span data-ttu-id="1474c-114">调用成功。</span><span class="sxs-lookup"><span data-stu-id="1474c-114">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="1474c-115">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1474c-115">E_OUTOFMEMORY</span></span>  <br/> |<span data-ttu-id="1474c-116">内存不足，无法进行复制。</span><span class="sxs-lookup"><span data-stu-id="1474c-116">There is insufficient memory for making the copy.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1474c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1474c-117">See also</span></span>

- [<span data-ttu-id="1474c-118">常量 (忙/闲 API) </span><span class="sxs-lookup"><span data-stu-id="1474c-118">Constants (Free/busy API)</span></span>](constants-free-busy-api.md)
- [<span data-ttu-id="1474c-119">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="1474c-119">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)  
- [<span data-ttu-id="1474c-120">IEnumFBBlock::Reset</span><span class="sxs-lookup"><span data-stu-id="1474c-120">IEnumFBBlock::Reset</span></span>](ienumfbblock-reset.md)  
- [<span data-ttu-id="1474c-121">IEnumFBBlock::Restrict</span><span class="sxs-lookup"><span data-stu-id="1474c-121">IEnumFBBlock::Restrict</span></span>](ienumfbblock-restrict.md)  
- [<span data-ttu-id="1474c-122">IEnumFBBlock::Skip</span><span class="sxs-lookup"><span data-stu-id="1474c-122">IEnumFBBlock::Skip</span></span>](ienumfbblock-skip.md)

