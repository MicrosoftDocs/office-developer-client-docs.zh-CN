---
title: IMAPISupportModifyStatusRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ModifyStatusRow
api_type:
- COM
ms.assetid: a304ca8f-e404-4535-be76-0b673f2061a0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8c76e6059670e782ea6530ec8e94f77abfe5b9fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417159"
---
# <a name="imapisupportmodifystatusrow"></a><span data-ttu-id="5d878-103">IMAPISupport::ModifyStatusRow</span><span class="sxs-lookup"><span data-stu-id="5d878-103">IMAPISupport::ModifyStatusRow</span></span>

  
  
<span data-ttu-id="5d878-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d878-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d878-105">通过添加新行或修改现有行来修改状态表。</span><span class="sxs-lookup"><span data-stu-id="5d878-105">Modifies the status table by adding a new row or modifying an existing row.</span></span>
  
```cpp
HRESULT ModifyStatusRow(
ULONG cValues,
LPSPropValue lpColumnVals,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="5d878-106">参数</span><span class="sxs-lookup"><span data-stu-id="5d878-106">Parameters</span></span>

 <span data-ttu-id="5d878-107">_cValues_</span><span class="sxs-lookup"><span data-stu-id="5d878-107">_cValues_</span></span>
  
> <span data-ttu-id="5d878-108">实时要包含在新的或修改的状态表行中的属性的计数。</span><span class="sxs-lookup"><span data-stu-id="5d878-108">[in] The count of properties to be included in the new or modified status table row.</span></span> 
    
 <span data-ttu-id="5d878-109">_lpColumnVals_</span><span class="sxs-lookup"><span data-stu-id="5d878-109">_lpColumnVals_</span></span>
  
> <span data-ttu-id="5d878-110">实时指向属性值数组的指针, 这些属性值描述要作为新的或修改的状态表行中的列包含的属性。</span><span class="sxs-lookup"><span data-stu-id="5d878-110">[in] A pointer to an array of property values that describe the properties to be included as columns in the new or modified status table row.</span></span>
    
 <span data-ttu-id="5d878-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5d878-111">_ulFlags_</span></span>
  
> <span data-ttu-id="5d878-112">实时标志的位掩码, 用于控制如何处理定义状态表行的信息。</span><span class="sxs-lookup"><span data-stu-id="5d878-112">[in] A bitmask of flags that controls how information that defines the status table row is processed.</span></span> <span data-ttu-id="5d878-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="5d878-113">The following flag can be set:</span></span>
    
<span data-ttu-id="5d878-114">STATUSROW_UPDATE</span><span class="sxs-lookup"><span data-stu-id="5d878-114">STATUSROW_UPDATE</span></span> 
  
> <span data-ttu-id="5d878-115">指示 MAPI 将由_lpColumnVals_指向的数组中包含的属性与现有状态表行 (而不是新行) 合并。</span><span class="sxs-lookup"><span data-stu-id="5d878-115">Directs MAPI to merge the properties included in the array pointed to by  _lpColumnVals_ with an existing status table row, rather than in a new row.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="5d878-116">返回值</span><span class="sxs-lookup"><span data-stu-id="5d878-116">Return value</span></span>

<span data-ttu-id="5d878-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d878-117">S_OK</span></span> 
  
> <span data-ttu-id="5d878-118">已成功更新状态表。</span><span class="sxs-lookup"><span data-stu-id="5d878-118">The status table was successfully updated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5d878-119">说明</span><span class="sxs-lookup"><span data-stu-id="5d878-119">Remarks</span></span>

<span data-ttu-id="5d878-120">**IMAPISupport:: ModifyStatusRow**方法是为所有服务提供程序支持对象实现的。</span><span class="sxs-lookup"><span data-stu-id="5d878-120">The **IMAPISupport::ModifyStatusRow** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="5d878-121">服务提供程序在登录时调用**ModifyStatusRow**以向状态表中添加行, 并在会话过程中的其他时间将行添加到更新行。</span><span class="sxs-lookup"><span data-stu-id="5d878-121">Service providers call **ModifyStatusRow** at logon time to add a row to the status table and at other times during the session to update the row.</span></span> <span data-ttu-id="5d878-122">**ModifyStatusRow**为 MAPI 提供生成状态表所需的信息。</span><span class="sxs-lookup"><span data-stu-id="5d878-122">**ModifyStatusRow** provides MAPI with the information necessary to build the status table.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="5d878-123">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="5d878-123">Notes to callers</span></span>

<span data-ttu-id="5d878-124">调用**ModifyStatusRow**时设置 STATUSROW_UPDATE 标志, 以对现有状态表行中的属性进行更改。</span><span class="sxs-lookup"><span data-stu-id="5d878-124">Set the STATUSROW_UPDATE flag when you call **ModifyStatusRow** to make changes to the properties in your existing status table row.</span></span> <span data-ttu-id="5d878-125">这样做会通知 MAPI 仅在_lpColumnVals_参数中传递所更改的列。</span><span class="sxs-lookup"><span data-stu-id="5d878-125">Doing so informs MAPI that only the columns being changed are passed in the  _lpColumnVals_ parameter.</span></span> 
  
<span data-ttu-id="5d878-126">客户端可以使用状态表中的信息访问状态对象。</span><span class="sxs-lookup"><span data-stu-id="5d878-126">Clients can use the information in the status table to access your status object.</span></span> 
  
<span data-ttu-id="5d878-127">若要获取您的状态表行中应包含的列的完整列表, 请参阅[状态表](status-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5d878-127">For a complete list of columns that you should include in your status table row, see [Status Tables](status-tables.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d878-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d878-128">See also</span></span>



[<span data-ttu-id="5d878-129">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5d878-129">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

