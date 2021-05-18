---
title: IOlkEnumGetNext
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b387f896-c213-fc07-a12a-33917e620837
description: 获取枚举器中的下一个帐户。
ms.openlocfilehash: e2ad98f7d7e71bd91d48b3824423e305baab429a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405987"
---
# <a name="iolkenumgetnext"></a><span data-ttu-id="48c38-103">IOlkEnum::GetNext</span><span class="sxs-lookup"><span data-stu-id="48c38-103">IOlkEnum::GetNext</span></span>

<span data-ttu-id="48c38-104">获取枚举器中的下一个帐户。</span><span class="sxs-lookup"><span data-stu-id="48c38-104">Gets the next account in the enumerator.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="48c38-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="48c38-105">Quick info</span></span>

<span data-ttu-id="48c38-106">请参阅 [IOlkEnum](iolkenum.md)。</span><span class="sxs-lookup"><span data-stu-id="48c38-106">See [IOlkEnum](iolkenum.md).</span></span>
  
```cpp
HRESULT IOlkEnum:: GetNext( 
    LPUNKNOWN *ppunk 
);

```

## <a name="parameters"></a><span data-ttu-id="48c38-107">参数</span><span class="sxs-lookup"><span data-stu-id="48c38-107">Parameters</span></span>

<span data-ttu-id="48c38-108">_ppunk_</span><span class="sxs-lookup"><span data-stu-id="48c38-108">_ppunk_</span></span>
  
> <span data-ttu-id="48c38-109">[in]指向客户端可查询以获取 [IOlkAccount](iolkaccount.md)接口的 **IUnknown** 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="48c38-109">[in] A pointer to an **IUnknown** interface that the client can query to obtain an [IOlkAccount](iolkaccount.md) interface.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="48c38-110">返回值</span><span class="sxs-lookup"><span data-stu-id="48c38-110">Return values</span></span>

|<span data-ttu-id="48c38-111">**[HRESULT]**</span><span class="sxs-lookup"><span data-stu-id="48c38-111">**HRESULT**</span></span>|<span data-ttu-id="48c38-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="48c38-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48c38-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="48c38-113">S_OK</span></span>  <br/> |<span data-ttu-id="48c38-114">调用成功。</span><span class="sxs-lookup"><span data-stu-id="48c38-114">The call succeeded.</span></span>  <br/> |
|<span data-ttu-id="48c38-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="48c38-115">S_FALSE</span></span>  <br/> |<span data-ttu-id="48c38-116">枚举器已到达末尾。</span><span class="sxs-lookup"><span data-stu-id="48c38-116">The enumerator has reached the end.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="48c38-117">备注</span><span class="sxs-lookup"><span data-stu-id="48c38-117">Remarks</span></span>

<span data-ttu-id="48c38-118">*ppunk* 指定的接口继承自 **IUnknown**。</span><span class="sxs-lookup"><span data-stu-id="48c38-118">The interface specified by  *ppunk*  inherits from **IUnknown**.</span></span> <span data-ttu-id="48c38-119">客户端可以使用 **IUnknown：：QueryInterface** (查询此接口) 以获取 **指向 IOlkAccount** 接口的指针，并获取或设置此帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="48c38-119">The client can query this interface (using **IUnknown::QueryInterface**) to obtain a pointer to an **IOlkAccount** interface, and get or set information for this account.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="48c38-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48c38-120">See also</span></span>

- [<span data-ttu-id="48c38-121">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="48c38-121">Constants (Account management API)</span></span>](constants-account-management-api.md) 
- [<span data-ttu-id="48c38-122">IOlkEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="48c38-122">IOlkEnum::GetCount</span></span>](iolkenum-getcount.md)  
- [<span data-ttu-id="48c38-123">IOlkEnum::Reset</span><span class="sxs-lookup"><span data-stu-id="48c38-123">IOlkEnum::Reset</span></span>](iolkenum-reset.md) 
- [<span data-ttu-id="48c38-124">IOlkEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="48c38-124">IOlkEnum::Skip</span></span>](iolkenum-skip.md)

