---
title: IMsgStoreGetReceiveFolderTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.GetReceiveFolderTable
api_type:
- COM
ms.assetid: d115ab58-07d2-4b49-8e08-2881c2924102
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 303c2ef855d5cfc1d6614bda92b46c2da97717c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421352"
---
# <a name="imsgstoregetreceivefoldertable"></a><span data-ttu-id="57931-103">IMsgStore::GetReceiveFolderTable</span><span class="sxs-lookup"><span data-stu-id="57931-103">IMsgStore::GetReceiveFolderTable</span></span>

  
  
<span data-ttu-id="57931-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="57931-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="57931-105">提供对接收文件夹表的访问权限, 该表包含有关邮件存储区的所有接收文件夹的信息。</span><span class="sxs-lookup"><span data-stu-id="57931-105">Provides access to the receive folder table, a table that includes information about all of the receive folders for the message store.</span></span>
  
```cpp
HRESULT GetReceiveFolderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable );
```

## <a name="parameters"></a><span data-ttu-id="57931-106">参数</span><span class="sxs-lookup"><span data-stu-id="57931-106">Parameters</span></span>

 <span data-ttu-id="57931-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="57931-107">_ulFlags_</span></span>
  
> <span data-ttu-id="57931-108">实时用于控制表访问的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="57931-108">[in] A bitmask of flags that controls table access.</span></span> <span data-ttu-id="57931-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="57931-109">The following flags can be set:</span></span>
    
<span data-ttu-id="57931-110">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="57931-110">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="57931-111">允许**GetReceiveFolderTable**成功返回, 这可能是在将表完全提供给调用程序之前。</span><span class="sxs-lookup"><span data-stu-id="57931-111">Allows **GetReceiveFolderTable** to return successfully, possibly before the table is fully available to the caller.</span></span> <span data-ttu-id="57931-112">如果该表不是完全可用的, 则进行后续的表调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="57931-112">If the table is not fully available, making a subsequent table call can raise an error.</span></span> 
    
<span data-ttu-id="57931-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="57931-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="57931-114">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="57931-114">The returned strings are in Unicode format.</span></span> <span data-ttu-id="57931-115">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="57931-115">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="57931-116">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="57931-116">_lppTable_</span></span>
  
> <span data-ttu-id="57931-117">排除指向接收文件夹表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="57931-117">[out] A pointer to a pointer to the receive folder table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="57931-118">返回值</span><span class="sxs-lookup"><span data-stu-id="57931-118">Return value</span></span>

<span data-ttu-id="57931-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="57931-119">S_OK</span></span> 
  
> <span data-ttu-id="57931-120">已成功返回接收文件夹表。</span><span class="sxs-lookup"><span data-stu-id="57931-120">The receive folder table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="57931-121">说明</span><span class="sxs-lookup"><span data-stu-id="57931-121">Remarks</span></span>

<span data-ttu-id="57931-122">**IMsgStore:: GetReceiveFolderTable**方法提供对显示所有邮件存储区接收文件夹的属性设置的表格的访问权限。</span><span class="sxs-lookup"><span data-stu-id="57931-122">The **IMsgStore::GetReceiveFolderTable** method provides access to a table that shows the property settings for all of the message store's receive folders.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="57931-123">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="57931-123">Notes to implementers</span></span>

<span data-ttu-id="57931-124">有关接收文件夹表中所需列的列表, 请参阅[receive folder Tables](receive-folder-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="57931-124">For a list of required columns in a receive folder table, see [Receive Folder Tables](receive-folder-tables.md).</span></span> 
  
<span data-ttu-id="57931-125">实现您的接收文件夹表, 以支持设置**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性的属性限制。</span><span class="sxs-lookup"><span data-stu-id="57931-125">Implement your receive folder tables to support setting property restrictions on the **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property.</span></span> <span data-ttu-id="57931-126">这样可以轻松访问特定的接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="57931-126">This enables easy access to particular receive folders.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="57931-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="57931-127">Notes to callers</span></span>

<span data-ttu-id="57931-128">在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="57931-128">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> <span data-ttu-id="57931-129">此标志还按[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序控制属性类型。</span><span class="sxs-lookup"><span data-stu-id="57931-129">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="57931-130">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="57931-130">MFCMAPI reference</span></span>

<span data-ttu-id="57931-131">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="57931-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="57931-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="57931-132">**File**</span></span>|<span data-ttu-id="57931-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="57931-133">**Function**</span></span>|<span data-ttu-id="57931-134">**备注**</span><span class="sxs-lookup"><span data-stu-id="57931-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57931-135">MsgStoreDlg</span><span class="sxs-lookup"><span data-stu-id="57931-135">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="57931-136">CMsgStoreDlg:: OnDisplayReceiveFolderTable</span><span class="sxs-lookup"><span data-stu-id="57931-136">CMsgStoreDlg::OnDisplayReceiveFolderTable</span></span>  <br/> |<span data-ttu-id="57931-137">MFCMAPI 使用**IMsgStore:: GetReceiveFolderTable**方法获取要显示的接收文件夹表。</span><span class="sxs-lookup"><span data-stu-id="57931-137">MFCMAPI uses the **IMsgStore::GetReceiveFolderTable** method to get the receive folder table to display.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="57931-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57931-138">See also</span></span>



[<span data-ttu-id="57931-139">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="57931-139">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="57931-140">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="57931-140">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="57931-141">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="57931-141">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="57931-142">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="57931-142">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="57931-143">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="57931-143">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="57931-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="57931-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

