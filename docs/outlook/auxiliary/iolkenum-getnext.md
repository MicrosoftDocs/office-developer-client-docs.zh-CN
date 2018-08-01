---
title: IOlkEnumGetNext
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b387f896-c213-fc07-a12a-33917e620837
description: 获取枚举中的下一个帐户。
ms.openlocfilehash: 496a4d787916d051c051b3a19a7113d9d50c6fe7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774376"
---
# <a name="iolkenumgetnext"></a><span data-ttu-id="da910-103">IOlkEnum::GetNext</span><span class="sxs-lookup"><span data-stu-id="da910-103">IOlkEnum::GetNext</span></span>

<span data-ttu-id="da910-104">获取枚举中的下一个帐户。</span><span class="sxs-lookup"><span data-stu-id="da910-104">Gets the next account in the enumerator.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="da910-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="da910-105">Quick info</span></span>

<span data-ttu-id="da910-106">请参阅[IOlkEnum](iolkenum.md)。</span><span class="sxs-lookup"><span data-stu-id="da910-106">See [IOlkEnum](iolkenum.md).</span></span>
  
```cpp
HRESULT IOlkEnum:: GetNext( 
    LPUNKNOWN *ppunk 
);

```

## <a name="parameters"></a><span data-ttu-id="da910-107">参数</span><span class="sxs-lookup"><span data-stu-id="da910-107">Parameters</span></span>

<span data-ttu-id="da910-108">_ppunk_</span><span class="sxs-lookup"><span data-stu-id="da910-108">_ppunk_</span></span>
  
> <span data-ttu-id="da910-109">[in]指向客户端可以查询以获取[IOlkAccount](iolkaccount.md)接口的**IUnknown**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="da910-109">[in] A pointer to an **IUnknown** interface that the client can query to obtain an [IOlkAccount](iolkaccount.md) interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="da910-110">返回值</span><span class="sxs-lookup"><span data-stu-id="da910-110">Return values</span></span>

|<span data-ttu-id="da910-111">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="da910-111">**HRESULT**</span></span>|<span data-ttu-id="da910-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="da910-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da910-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="da910-113">S_OK</span></span>  <br/> |<span data-ttu-id="da910-114">调用成功。</span><span class="sxs-lookup"><span data-stu-id="da910-114">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="da910-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="da910-115">S_FALSE</span></span>  <br/> |<span data-ttu-id="da910-116">将枚举器重已达到结束。</span><span class="sxs-lookup"><span data-stu-id="da910-116">The enumerator has reached the end.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="da910-117">说明</span><span class="sxs-lookup"><span data-stu-id="da910-117">Remarks</span></span>

<span data-ttu-id="da910-118">从**IUnknown**继承*ppunk*由指定的接口。</span><span class="sxs-lookup"><span data-stu-id="da910-118">The interface specified by  *ppunk*  inherits from **IUnknown**.</span></span> <span data-ttu-id="da910-119">客户端可以查询此接口 （使用**IUnknown::QueryInterface**） 以获取指向**IOlkAccount**接口，并获取或设置为此帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="da910-119">The client can query this interface (using **IUnknown::QueryInterface**) to obtain a pointer to an **IOlkAccount** interface, and get or set information for this account.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="da910-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da910-120">See also</span></span>

- [<span data-ttu-id="da910-121">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="da910-121">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="da910-122">IOlkEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="da910-122">IOlkEnum::GetCount</span></span>](iolkenum-getcount.md)  
- [<span data-ttu-id="da910-123">IOlkEnum::Reset</span><span class="sxs-lookup"><span data-stu-id="da910-123">IOlkEnum::Reset</span></span>](iolkenum-reset.md) 
- [<span data-ttu-id="da910-124">IOlkEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="da910-124">IOlkEnum::Skip</span></span>](iolkenum-skip.md)

