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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 24718c50d02da5d60a6594f56ea6100650fe9f1a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775617"
---
# <a name="imapisupportmodifystatusrow"></a><span data-ttu-id="96b33-103">IMAPISupport::ModifyStatusRow</span><span class="sxs-lookup"><span data-stu-id="96b33-103">IMAPISupport::ModifyStatusRow</span></span>

  
  
<span data-ttu-id="96b33-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="96b33-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="96b33-105">通过添加新行或修改现有行来修改状态表。</span><span class="sxs-lookup"><span data-stu-id="96b33-105">Modifies the status table by adding a new row or modifying an existing row.</span></span>
  
```cpp
HRESULT ModifyStatusRow(
ULONG cValues,
LPSPropValue lpColumnVals,
ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="96b33-106">参数</span><span class="sxs-lookup"><span data-stu-id="96b33-106">Parameters</span></span>

 <span data-ttu-id="96b33-107">_cValues_</span><span class="sxs-lookup"><span data-stu-id="96b33-107">_cValues_</span></span>
  
> <span data-ttu-id="96b33-108">[in]属性包括新的或修改状态表中行数。</span><span class="sxs-lookup"><span data-stu-id="96b33-108">[in] The count of properties to be included in the new or modified status table row.</span></span> 
    
 <span data-ttu-id="96b33-109">_lpColumnVals_</span><span class="sxs-lookup"><span data-stu-id="96b33-109">_lpColumnVals_</span></span>
  
> <span data-ttu-id="96b33-110">[in]一个指向介绍了要为新的或修改状态表格行中的列包含的属性的属性值的数组。</span><span class="sxs-lookup"><span data-stu-id="96b33-110">[in] A pointer to an array of property values that describe the properties to be included as columns in the new or modified status table row.</span></span>
    
 <span data-ttu-id="96b33-111">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="96b33-111">_ulFlags_</span></span>
  
> <span data-ttu-id="96b33-112">[in]位掩码的标志，控制如何处理定义状态表格行的信息。</span><span class="sxs-lookup"><span data-stu-id="96b33-112">[in] A bitmask of flags that controls how information that defines the status table row is processed.</span></span> <span data-ttu-id="96b33-113">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="96b33-113">The following flag can be set:</span></span>
    
<span data-ttu-id="96b33-114">STATUSROW_UPDATE</span><span class="sxs-lookup"><span data-stu-id="96b33-114">STATUSROW_UPDATE</span></span> 
  
> <span data-ttu-id="96b33-115">指示 MAPI 合并包括数组所指的_lpColumnVals_与现有状态表行，而不是一个新行中的属性。</span><span class="sxs-lookup"><span data-stu-id="96b33-115">Directs MAPI to merge the properties included in the array pointed to by  _lpColumnVals_ with an existing status table row, rather than in a new row.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="96b33-116">返回值</span><span class="sxs-lookup"><span data-stu-id="96b33-116">Return value</span></span>

<span data-ttu-id="96b33-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="96b33-117">S_OK</span></span> 
  
> <span data-ttu-id="96b33-118">已成功更新状态表。</span><span class="sxs-lookup"><span data-stu-id="96b33-118">The status table was successfully updated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="96b33-119">说明</span><span class="sxs-lookup"><span data-stu-id="96b33-119">Remarks</span></span>

<span data-ttu-id="96b33-120">**IMAPISupport::ModifyStatusRow**方法将执行所有服务提供商支持对象。</span><span class="sxs-lookup"><span data-stu-id="96b33-120">The **IMAPISupport::ModifyStatusRow** method is implemented for all service provider support objects.</span></span> <span data-ttu-id="96b33-121">服务提供商调用**ModifyStatusRow**在登录时，将行添加到状态表和其他更新行在会话期间的时间。</span><span class="sxs-lookup"><span data-stu-id="96b33-121">Service providers call **ModifyStatusRow** at logon time to add a row to the status table and at other times during the session to update the row.</span></span> <span data-ttu-id="96b33-122">**ModifyStatusRow**将 MAPI 提供构建状态表所需的信息。</span><span class="sxs-lookup"><span data-stu-id="96b33-122">**ModifyStatusRow** provides MAPI with the information necessary to build the status table.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="96b33-123">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="96b33-123">Notes to callers</span></span>

<span data-ttu-id="96b33-124">调用**ModifyStatusRow**对您现有的状态表格行中的属性进行更改时，请设置 STATUSROW_UPDATE 标志。</span><span class="sxs-lookup"><span data-stu-id="96b33-124">Set the STATUSROW_UPDATE flag when you call **ModifyStatusRow** to make changes to the properties in your existing status table row.</span></span> <span data-ttu-id="96b33-125">这样通知 MAPI， _lpColumnVals_参数中传递仅正在更改的列。</span><span class="sxs-lookup"><span data-stu-id="96b33-125">Doing so informs MAPI that only the columns being changed are passed in the  _lpColumnVals_ parameter.</span></span> 
  
<span data-ttu-id="96b33-126">客户端可以使用状态表中的信息，以访问您状态的对象。</span><span class="sxs-lookup"><span data-stu-id="96b33-126">Clients can use the information in the status table to access your status object.</span></span> 
  
<span data-ttu-id="96b33-127">您应在您状态的表格行中包括的列的完整列表，请参阅[状态表](status-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="96b33-127">For a complete list of columns that you should include in your status table row, see [Status Tables](status-tables.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96b33-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96b33-128">See also</span></span>



[<span data-ttu-id="96b33-129">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="96b33-129">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

