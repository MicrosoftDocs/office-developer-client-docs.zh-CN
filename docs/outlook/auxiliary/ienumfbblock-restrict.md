---
title: IEnumFBBlockRestrict
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 887cea55-8f1c-45ec-3100-d03e1213d7c9
description: 限制到指定的时间段枚举。
ms.openlocfilehash: 6b07fe52a84d6a808ab7400ff3e8982b1cce51ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774194"
---
# <a name="ienumfbblockrestrict"></a><span data-ttu-id="a4008-103">IEnumFBBlock::Restrict</span><span class="sxs-lookup"><span data-stu-id="a4008-103">IEnumFBBlock::Restrict</span></span>

<span data-ttu-id="a4008-104">限制到指定的时间段枚举。</span><span class="sxs-lookup"><span data-stu-id="a4008-104">Restricts the enumeration to a specified time period.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="a4008-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="a4008-105">Quick info</span></span>

<span data-ttu-id="a4008-106">请参阅[IEnumFBBlock](ienumfbblock.md)。</span><span class="sxs-lookup"><span data-stu-id="a4008-106">See [IEnumFBBlock](ienumfbblock.md).</span></span>
  
```cpp
HRESULT Restrict(  
    FILETIME ftmStart, 
    FILETIME ftmEnd 
);

```

## <a name="parameters"></a><span data-ttu-id="a4008-107">参数</span><span class="sxs-lookup"><span data-stu-id="a4008-107">Parameters</span></span>

<span data-ttu-id="a4008-108">_ftmStart_</span><span class="sxs-lookup"><span data-stu-id="a4008-108">_ftmStart_</span></span>
  
>  <span data-ttu-id="a4008-109">[in]若要限制枚举的开始时间。</span><span class="sxs-lookup"><span data-stu-id="a4008-109">[in] The start time to restrict the enumeration.</span></span> 
    
<span data-ttu-id="a4008-110">_ftmEnd_</span><span class="sxs-lookup"><span data-stu-id="a4008-110">_ftmEnd_</span></span>
  
> <span data-ttu-id="a4008-111">[in]若要限制枚举的结束时间。</span><span class="sxs-lookup"><span data-stu-id="a4008-111">[in] The end time to restrict the enumeration.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="a4008-112">返回值</span><span class="sxs-lookup"><span data-stu-id="a4008-112">Return values</span></span>

<span data-ttu-id="a4008-113">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="a4008-113">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a4008-114">注释</span><span class="sxs-lookup"><span data-stu-id="a4008-114">Remarks</span></span>

<span data-ttu-id="a4008-115">此方法还重置枚举。</span><span class="sxs-lookup"><span data-stu-id="a4008-115">This method also resets the enumeration.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4008-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4008-116">See also</span></span>

- [<span data-ttu-id="a4008-117">IEnumFBBlock::Clone</span><span class="sxs-lookup"><span data-stu-id="a4008-117">IEnumFBBlock::Clone</span></span>](ienumfbblock-clone.md)  
- [<span data-ttu-id="a4008-118">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="a4008-118">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)  
- [<span data-ttu-id="a4008-119">IEnumFBBlock::Reset</span><span class="sxs-lookup"><span data-stu-id="a4008-119">IEnumFBBlock::Reset</span></span>](ienumfbblock-reset.md)  
- [<span data-ttu-id="a4008-120">IEnumFBBlock::Skip</span><span class="sxs-lookup"><span data-stu-id="a4008-120">IEnumFBBlock::Skip</span></span>](ienumfbblock-skip.md)  
- [<span data-ttu-id="a4008-121">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="a4008-121">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

