---
title: IEnumFBBlockRestrict
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 887cea55-8f1c-45ec-3100-d03e1213d7c9
description: 将枚举限制为指定的时间段。
ms.openlocfilehash: e7f7a5d846d13422f9ed79ef26f1b9b0008463f6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431944"
---
# <a name="ienumfbblockrestrict"></a><span data-ttu-id="b841f-103">IEnumFBBlock::Restrict</span><span class="sxs-lookup"><span data-stu-id="b841f-103">IEnumFBBlock::Restrict</span></span>

<span data-ttu-id="b841f-104">将枚举限制为指定的时间段。</span><span class="sxs-lookup"><span data-stu-id="b841f-104">Restricts the enumeration to a specified time period.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b841f-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="b841f-105">Quick info</span></span>

<span data-ttu-id="b841f-106">请参阅 [IEnumFBBlock](ienumfbblock.md)。</span><span class="sxs-lookup"><span data-stu-id="b841f-106">See [IEnumFBBlock](ienumfbblock.md).</span></span>
  
```cpp
HRESULT Restrict(  
    FILETIME ftmStart, 
    FILETIME ftmEnd 
);

```

## <a name="parameters"></a><span data-ttu-id="b841f-107">参数</span><span class="sxs-lookup"><span data-stu-id="b841f-107">Parameters</span></span>

<span data-ttu-id="b841f-108">_ftmStart_</span><span class="sxs-lookup"><span data-stu-id="b841f-108">_ftmStart_</span></span>
  
>  <span data-ttu-id="b841f-109">[in]限制枚举的开始时间。</span><span class="sxs-lookup"><span data-stu-id="b841f-109">[in] The start time to restrict the enumeration.</span></span> 
    
<span data-ttu-id="b841f-110">_ftmEnd_</span><span class="sxs-lookup"><span data-stu-id="b841f-110">_ftmEnd_</span></span>
  
> <span data-ttu-id="b841f-111">[in]限制枚举的结束时间。</span><span class="sxs-lookup"><span data-stu-id="b841f-111">[in] The end time to restrict the enumeration.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="b841f-112">返回值</span><span class="sxs-lookup"><span data-stu-id="b841f-112">Return values</span></span>

<span data-ttu-id="b841f-113">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="b841f-113">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b841f-114">备注</span><span class="sxs-lookup"><span data-stu-id="b841f-114">Remarks</span></span>

<span data-ttu-id="b841f-115">此方法还重置枚举。</span><span class="sxs-lookup"><span data-stu-id="b841f-115">This method also resets the enumeration.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b841f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b841f-116">See also</span></span>

- [<span data-ttu-id="b841f-117">IEnumFBBlock::Clone</span><span class="sxs-lookup"><span data-stu-id="b841f-117">IEnumFBBlock::Clone</span></span>](ienumfbblock-clone.md)  
- [<span data-ttu-id="b841f-118">IEnumFBBlock::Next</span><span class="sxs-lookup"><span data-stu-id="b841f-118">IEnumFBBlock::Next</span></span>](ienumfbblock-next.md)  
- [<span data-ttu-id="b841f-119">IEnumFBBlock::Reset</span><span class="sxs-lookup"><span data-stu-id="b841f-119">IEnumFBBlock::Reset</span></span>](ienumfbblock-reset.md)  
- [<span data-ttu-id="b841f-120">IEnumFBBlock::Skip</span><span class="sxs-lookup"><span data-stu-id="b841f-120">IEnumFBBlock::Skip</span></span>](ienumfbblock-skip.md)  
- [<span data-ttu-id="b841f-121">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="b841f-121">Use relative time to access free/busy data</span></span>](how-to-use-relative-time-to-access-free-busy-data.md)

