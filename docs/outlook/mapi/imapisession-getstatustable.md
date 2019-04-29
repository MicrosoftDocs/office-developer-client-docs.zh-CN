---
title: IMAPISessionGetStatusTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.GetStatusTable
api_type:
- COM
ms.assetid: 53428f8d-4838-46d1-a0ab-cafb194f4cc3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 17e936093536f548d16021523d9434f09777c6d9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407135"
---
# <a name="imapisessiongetstatustable"></a><span data-ttu-id="f7143-103">IMAPISession::GetStatusTable</span><span class="sxs-lookup"><span data-stu-id="f7143-103">IMAPISession::GetStatusTable</span></span>

  
  
<span data-ttu-id="f7143-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7143-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7143-105">提供对状态表的访问, 该表包含有关会话中所有 MAPI 资源的信息。</span><span class="sxs-lookup"><span data-stu-id="f7143-105">Provides access to the status table, a table that contains information about all the MAPI resources in the session.</span></span>
  
```cpp
HRESULT GetStatusTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="f7143-106">参数</span><span class="sxs-lookup"><span data-stu-id="f7143-106">Parameters</span></span>

 <span data-ttu-id="f7143-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f7143-107">_ulFlags_</span></span>
  
> <span data-ttu-id="f7143-108">实时标志的位掩码, 用于确定作为字符字符串的列的格式。</span><span class="sxs-lookup"><span data-stu-id="f7143-108">[in] A bitmask of flags that determines the format for columns that are character strings.</span></span> <span data-ttu-id="f7143-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="f7143-109">The following flag can be set:</span></span>
    
<span data-ttu-id="f7143-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f7143-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="f7143-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="f7143-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="f7143-112">如果未设置 MAPI_UNICODE 标志, 则字符串列的格式为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="f7143-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
 <span data-ttu-id="f7143-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="f7143-113">_lppTable_</span></span>
  
> <span data-ttu-id="f7143-114">排除指向状态表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f7143-114">[out] A pointer to a pointer to the status table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f7143-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f7143-115">Return value</span></span>

<span data-ttu-id="f7143-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7143-116">S_OK</span></span> 
  
> <span data-ttu-id="f7143-117">成功返回表。</span><span class="sxs-lookup"><span data-stu-id="f7143-117">The table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f7143-118">说明</span><span class="sxs-lookup"><span data-stu-id="f7143-118">Remarks</span></span>

<span data-ttu-id="f7143-119">**IMAPISession:: GetStatusTable**方法提供对状态表的访问, 该表包含有关会话中所有 MAPI 资源的信息。</span><span class="sxs-lookup"><span data-stu-id="f7143-119">The **IMAPISession::GetStatusTable** method provides access to the status table that contains information about all of the MAPI resources in the session.</span></span> <span data-ttu-id="f7143-120">表中有一行, 其中包含有关 mapi 子系统的信息、mapi 后台处理程序的一行、集成的通讯簿的一行, 以及配置文件中的每个服务提供程序的一行。</span><span class="sxs-lookup"><span data-stu-id="f7143-120">There is one row in the table for information about the MAPI subsystem, one row for the MAPI spooler, one row for the integrated address book, and one row for each service provider in the profile.</span></span> 
  
<span data-ttu-id="f7143-121">有关状态表中的必填列和可选列的完整列表, 请参阅[status Tables](status-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="f7143-121">For a complete list of required and optional columns in the status table, see [Status Tables](status-tables.md).</span></span> 
  
<span data-ttu-id="f7143-122">在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="f7143-122">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> <span data-ttu-id="f7143-123">此标志还按[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序控制属性类型。</span><span class="sxs-lookup"><span data-stu-id="f7143-123">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f7143-124">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f7143-124">MFCMAPI reference</span></span>

<span data-ttu-id="f7143-125">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f7143-125">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f7143-126">**文件**</span><span class="sxs-lookup"><span data-stu-id="f7143-126">**File**</span></span>|<span data-ttu-id="f7143-127">**函数**</span><span class="sxs-lookup"><span data-stu-id="f7143-127">**Function**</span></span>|<span data-ttu-id="f7143-128">**备注**</span><span class="sxs-lookup"><span data-stu-id="f7143-128">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7143-129">MainDlg</span><span class="sxs-lookup"><span data-stu-id="f7143-129">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="f7143-130">CMainDlg:: OnStatusTable</span><span class="sxs-lookup"><span data-stu-id="f7143-130">CMainDlg::OnStatusTable</span></span>  <br/> |<span data-ttu-id="f7143-131">MFCMAPI 使用**IMAPISession:: GetStatusTable**方法获取要呈现的状态表。</span><span class="sxs-lookup"><span data-stu-id="f7143-131">MFCMAPI uses the **IMAPISession::GetStatusTable** method to obtain the status table to be rendered.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f7143-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7143-132">See also</span></span>



[<span data-ttu-id="f7143-133">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f7143-133">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="f7143-134">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="f7143-134">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="f7143-135">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="f7143-135">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="f7143-136">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="f7143-136">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="f7143-137">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="f7143-137">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="f7143-138">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="f7143-138">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="f7143-139">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f7143-139">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="f7143-140">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f7143-140">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="f7143-141">状态表</span><span class="sxs-lookup"><span data-stu-id="f7143-141">Status Tables</span></span>](status-tables.md)

