---
title: ITableDataHrEnumRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrEnumRow
api_type:
- COM
ms.assetid: b25d9f2b-9454-4983-98f7-6a051a3b8a04
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 50fd96acd0989459c9887770ec5a3a236f182da5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348893"
---
# <a name="itabledatahrenumrow"></a><span data-ttu-id="f3fdc-103">ITableData::HrEnumRow</span><span class="sxs-lookup"><span data-stu-id="f3fdc-103">ITableData::HrEnumRow</span></span>

  
  
<span data-ttu-id="f3fdc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3fdc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3fdc-105">根据行在表中的位置对其进行检索。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-105">Retrieves a row based on its position in the table.</span></span> 
  
```cpp
HRESULT HrEnumRow(
  ULONG ulRowNumber,
  LPSRow FAR * lppSRow
);
```

## <a name="parameters"></a><span data-ttu-id="f3fdc-106">参数</span><span class="sxs-lookup"><span data-stu-id="f3fdc-106">Parameters</span></span>

 <span data-ttu-id="f3fdc-107">_ulRowNumber_</span><span class="sxs-lookup"><span data-stu-id="f3fdc-107">_ulRowNumber_</span></span>
  
> <span data-ttu-id="f3fdc-108">实时要为其返回属性的行的编号。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-108">[in] The number of the row for which to return properties.</span></span> <span data-ttu-id="f3fdc-109">_ulRowNumber_参数中的值可以是0中的任何值, 它指示表中的第一行, 即表示表中的最后一行的 n-1。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-109">The value in the  _ulRowNumber_ parameter can be any value from 0, which indicates the first row in the table, through n - 1, which indicates the last row in the table.</span></span> 
    
 <span data-ttu-id="f3fdc-110">_lppSRow_</span><span class="sxs-lookup"><span data-stu-id="f3fdc-110">_lppSRow_</span></span>
  
> <span data-ttu-id="f3fdc-111">排除指向描述目标行的[SRow](srow.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-111">[out] A pointer to a pointer to an [SRow](srow.md) structure that describes the target row.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="f3fdc-112">返回值</span><span class="sxs-lookup"><span data-stu-id="f3fdc-112">Return value</span></span>

<span data-ttu-id="f3fdc-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3fdc-113">S_OK</span></span> 
  
> <span data-ttu-id="f3fdc-114">已成功检索行, 或_ulRowNumber_参数所指定的行号的行不存在。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-114">The row was retrieved successfully, or a row for the row number specified by the  _ulRowNumber_ parameter does not exist.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f3fdc-115">注解</span><span class="sxs-lookup"><span data-stu-id="f3fdc-115">Remarks</span></span>

<span data-ttu-id="f3fdc-116">**ITableData:: HrEnumRow**方法根据顺序编号检索行。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-116">The **ITableData::HrEnumRow** method retrieves a row based on a sequential number.</span></span> <span data-ttu-id="f3fdc-117">此数字表示插入顺序 (0 表示第一行, 行数减1表示最后一行)。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-117">This number represents the order of insertion (0 indicates the first row, and the number of rows minus 1 indicates the last row).</span></span> <span data-ttu-id="f3fdc-118">MAPI 在表数据对象的生存期内保持行插入的时间顺序。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-118">MAPI maintains this chronological order of row insertion for the lifetime of the table data object.</span></span> 
  
<span data-ttu-id="f3fdc-119">如果_ulRowNumber_中指定的数字不对应于表中的行, 则**HrEnumRow**将返回 S_OK, 并将_lppSRow_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-119">If the number specified in  _ulRowNumber_ does not correspond to a row in the table, **HrEnumRow** returns S_OK and sets the  _lppSRow_ parameter to NULL.</span></span> 
  
<span data-ttu-id="f3fdc-120">在创建 table data 对象时, MAPI 使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数为返回的**SRow**结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-120">MAPI allocates memory for the returned **SRow** structure by using the [MAPIAllocateBuffer](mapiallocatebuffer.md) function when the table data object is created.</span></span> <span data-ttu-id="f3fdc-121">调用方必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数来释放此内存。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-121">The caller must release this memory by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="f3fdc-122">若要按插入顺序检索表中的行, 则表数据对象用户调用**HrEnumRow**方法。</span><span class="sxs-lookup"><span data-stu-id="f3fdc-122">To retrieve rows from a table in the order that they were inserted, table data object users call the **HrEnumRow** method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f3fdc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3fdc-123">See also</span></span>



[<span data-ttu-id="f3fdc-124">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="f3fdc-124">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="f3fdc-125">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="f3fdc-125">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="f3fdc-126">SRow</span><span class="sxs-lookup"><span data-stu-id="f3fdc-126">SRow</span></span>](srow.md)
  
[<span data-ttu-id="f3fdc-127">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f3fdc-127">ITableData : IUnknown</span></span>](itabledataiunknown.md)

