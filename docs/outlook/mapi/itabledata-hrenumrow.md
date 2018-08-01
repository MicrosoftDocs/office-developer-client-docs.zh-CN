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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6c149a215a048b96408025e08df55972fa989f46
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776084"
---
# <a name="itabledatahrenumrow"></a><span data-ttu-id="25960-103">ITableData::HrEnumRow</span><span class="sxs-lookup"><span data-stu-id="25960-103">ITableData::HrEnumRow</span></span>

  
  
<span data-ttu-id="25960-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="25960-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="25960-105">检索根据其位置表中的行。</span><span class="sxs-lookup"><span data-stu-id="25960-105">Retrieves a row based on its position in the table.</span></span> 
  
```cpp
HRESULT HrEnumRow(
  ULONG ulRowNumber,
  LPSRow FAR * lppSRow
);
```

## <a name="parameters"></a><span data-ttu-id="25960-106">参数</span><span class="sxs-lookup"><span data-stu-id="25960-106">Parameters</span></span>

 <span data-ttu-id="25960-107">_ulRowNumber_</span><span class="sxs-lookup"><span data-stu-id="25960-107">_ulRowNumber_</span></span>
  
> <span data-ttu-id="25960-108">[in]要为其返回属性的行数。</span><span class="sxs-lookup"><span data-stu-id="25960-108">[in] The number of the row for which to return properties.</span></span> <span data-ttu-id="25960-109">_UlRowNumber_参数中的值可以是 0，表示在表中，通过 n-1，这表明表中的最后一行的第一行中的任何值。</span><span class="sxs-lookup"><span data-stu-id="25960-109">The value in the  _ulRowNumber_ parameter can be any value from 0, which indicates the first row in the table, through n - 1, which indicates the last row in the table.</span></span> 
    
 <span data-ttu-id="25960-110">_lppSRow_</span><span class="sxs-lookup"><span data-stu-id="25960-110">_lppSRow_</span></span>
  
> <span data-ttu-id="25960-111">[输出]指向介绍目标行[SRow](srow.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="25960-111">[out] A pointer to a pointer to an [SRow](srow.md) structure that describes the target row.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="25960-112">返回值</span><span class="sxs-lookup"><span data-stu-id="25960-112">Return value</span></span>

<span data-ttu-id="25960-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="25960-113">S_OK</span></span> 
  
> <span data-ttu-id="25960-114">已成功检索行或_ulRowNumber_参数指定的行号行不存在。</span><span class="sxs-lookup"><span data-stu-id="25960-114">The row was retrieved successfully, or a row for the row number specified by the  _ulRowNumber_ parameter does not exist.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="25960-115">说明</span><span class="sxs-lookup"><span data-stu-id="25960-115">Remarks</span></span>

<span data-ttu-id="25960-116">**ITableData::HrEnumRow**方法检索行基于序列号。</span><span class="sxs-lookup"><span data-stu-id="25960-116">The **ITableData::HrEnumRow** method retrieves a row based on a sequential number.</span></span> <span data-ttu-id="25960-117">这个数字表示插入的顺序 （0 表示的第一行和减 1 之间的行数指示最后一行）。</span><span class="sxs-lookup"><span data-stu-id="25960-117">This number represents the order of insertion (0 indicates the first row, and the number of rows minus 1 indicates the last row).</span></span> <span data-ttu-id="25960-118">MAPI 维护表数据对象的生存期内行插入此时间顺序。</span><span class="sxs-lookup"><span data-stu-id="25960-118">MAPI maintains this chronological order of row insertion for the lifetime of the table data object.</span></span> 
  
<span data-ttu-id="25960-119">如果号码中指定的_ulRowNumber_不对应于表中的行， **HrEnumRow** ，则返回 S_OK 和_lppSRow_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="25960-119">If the number specified in  _ulRowNumber_ does not correspond to a row in the table, **HrEnumRow** returns S_OK and sets the  _lppSRow_ parameter to NULL.</span></span> 
  
<span data-ttu-id="25960-120">MAPI 创建表格数据对象时使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数返回**SRow**结构分配内存。</span><span class="sxs-lookup"><span data-stu-id="25960-120">MAPI allocates memory for the returned **SRow** structure by using the [MAPIAllocateBuffer](mapiallocatebuffer.md) function when the table data object is created.</span></span> <span data-ttu-id="25960-121">呼叫者必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放此内存。</span><span class="sxs-lookup"><span data-stu-id="25960-121">The caller must release this memory by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="25960-122">若要检索行从表格中插入了它们的顺序，表数据对象的用户，请调用**HrEnumRow**方法。</span><span class="sxs-lookup"><span data-stu-id="25960-122">To retrieve rows from a table in the order that they were inserted, table data object users call the **HrEnumRow** method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="25960-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25960-123">See also</span></span>



[<span data-ttu-id="25960-124">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="25960-124">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="25960-125">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="25960-125">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="25960-126">SRow</span><span class="sxs-lookup"><span data-stu-id="25960-126">SRow</span></span>](srow.md)
  
[<span data-ttu-id="25960-127">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="25960-127">ITableData : IUnknown</span></span>](itabledataiunknown.md)

