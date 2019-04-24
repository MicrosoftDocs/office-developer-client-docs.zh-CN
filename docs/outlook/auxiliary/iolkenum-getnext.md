---
title: IOlkEnumGetNext
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b387f896-c213-fc07-a12a-33917e620837
description: 获取枚举数中的下一个帐户。
ms.openlocfilehash: e2ad98f7d7e71bd91d48b3824423e305baab429a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321894"
---
# <a name="iolkenumgetnext"></a><span data-ttu-id="a06d2-103">IOlkEnum::GetNext</span><span class="sxs-lookup"><span data-stu-id="a06d2-103">IOlkEnum::GetNext</span></span>

<span data-ttu-id="a06d2-104">获取枚举数中的下一个帐户。</span><span class="sxs-lookup"><span data-stu-id="a06d2-104">Gets the next account in the enumerator.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="a06d2-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="a06d2-105">Quick info</span></span>

<span data-ttu-id="a06d2-106">请参阅[IOlkEnum](iolkenum.md)。</span><span class="sxs-lookup"><span data-stu-id="a06d2-106">See [IOlkEnum](iolkenum.md).</span></span>
  
```cpp
HRESULT IOlkEnum:: GetNext( 
    LPUNKNOWN *ppunk 
);

```

## <a name="parameters"></a><span data-ttu-id="a06d2-107">参数</span><span class="sxs-lookup"><span data-stu-id="a06d2-107">Parameters</span></span>

<span data-ttu-id="a06d2-108">_ppunk_</span><span class="sxs-lookup"><span data-stu-id="a06d2-108">_ppunk_</span></span>
  
> <span data-ttu-id="a06d2-109">实时指向**IUnknown**接口的指针, 客户端可以查询该接口以获取[IOlkAccount](iolkaccount.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a06d2-109">[in] A pointer to an **IUnknown** interface that the client can query to obtain an [IOlkAccount](iolkaccount.md) interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="a06d2-110">返回值</span><span class="sxs-lookup"><span data-stu-id="a06d2-110">Return values</span></span>

|<span data-ttu-id="a06d2-111">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="a06d2-111">**HRESULT**</span></span>|<span data-ttu-id="a06d2-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="a06d2-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a06d2-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a06d2-113">S_OK</span></span>  <br/> |<span data-ttu-id="a06d2-114">调用成功。</span><span class="sxs-lookup"><span data-stu-id="a06d2-114">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="a06d2-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a06d2-115">S_FALSE</span></span>  <br/> |<span data-ttu-id="a06d2-116">枚举器已达到结尾。</span><span class="sxs-lookup"><span data-stu-id="a06d2-116">The enumerator has reached the end.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a06d2-117">注解</span><span class="sxs-lookup"><span data-stu-id="a06d2-117">Remarks</span></span>

<span data-ttu-id="a06d2-118">由*ppunk*指定的接口继承自**IUnknown**。</span><span class="sxs-lookup"><span data-stu-id="a06d2-118">The interface specified by  *ppunk*  inherits from **IUnknown**.</span></span> <span data-ttu-id="a06d2-119">客户端可以查询此接口 (使用**IUnknown:: QueryInterface**) 获取指向**IOlkAccount**接口的指针, 并获取或设置此帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="a06d2-119">The client can query this interface (using **IUnknown::QueryInterface**) to obtain a pointer to an **IOlkAccount** interface, and get or set information for this account.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a06d2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a06d2-120">See also</span></span>

- [<span data-ttu-id="a06d2-121">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="a06d2-121">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="a06d2-122">IOlkEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="a06d2-122">IOlkEnum::GetCount</span></span>](iolkenum-getcount.md)  
- [<span data-ttu-id="a06d2-123">IOlkEnum::Reset</span><span class="sxs-lookup"><span data-stu-id="a06d2-123">IOlkEnum::Reset</span></span>](iolkenum-reset.md) 
- [<span data-ttu-id="a06d2-124">IOlkEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="a06d2-124">IOlkEnum::Skip</span></span>](iolkenum-skip.md)

