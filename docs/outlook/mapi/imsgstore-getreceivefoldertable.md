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
ms.openlocfilehash: 681fd68fc068633912df1cb7f060b8c4111b5de8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566535"
---
# <a name="imsgstoregetreceivefoldertable"></a><span data-ttu-id="aaacf-103">IMsgStore::GetReceiveFolderTable</span><span class="sxs-lookup"><span data-stu-id="aaacf-103">IMsgStore::GetReceiveFolderTable</span></span>

  
  
<span data-ttu-id="aaacf-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aaacf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aaacf-105">提供对接收文件夹表中，一个表，包括有关的所有接收的消息存储库文件夹的信息的访问。</span><span class="sxs-lookup"><span data-stu-id="aaacf-105">Provides access to the receive folder table, a table that includes information about all of the receive folders for the message store.</span></span>
  
```cpp
HRESULT GetReceiveFolderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable );
```

## <a name="parameters"></a><span data-ttu-id="aaacf-106">参数</span><span class="sxs-lookup"><span data-stu-id="aaacf-106">Parameters</span></span>

 <span data-ttu-id="aaacf-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="aaacf-107">_ulFlags_</span></span>
  
> <span data-ttu-id="aaacf-108">[in]Flags 控件表访问的位掩码。</span><span class="sxs-lookup"><span data-stu-id="aaacf-108">[in] A bitmask of flags that controls table access.</span></span> <span data-ttu-id="aaacf-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="aaacf-109">The following flags can be set:</span></span>
    
<span data-ttu-id="aaacf-110">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="aaacf-110">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="aaacf-111">允许**GetReceiveFolderTable**返回成功，原因可能是完全可用于将呼叫者表之前。</span><span class="sxs-lookup"><span data-stu-id="aaacf-111">Allows **GetReceiveFolderTable** to return successfully, possibly before the table is fully available to the caller.</span></span> <span data-ttu-id="aaacf-112">如果表不完全支持，进行后续表呼叫会引发错误。</span><span class="sxs-lookup"><span data-stu-id="aaacf-112">If the table is not fully available, making a subsequent table call can raise an error.</span></span> 
    
<span data-ttu-id="aaacf-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="aaacf-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="aaacf-114">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="aaacf-114">The returned strings are in Unicode format.</span></span> <span data-ttu-id="aaacf-115">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="aaacf-115">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="aaacf-116">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="aaacf-116">_lppTable_</span></span>
  
> <span data-ttu-id="aaacf-117">[输出]指向接收文件夹表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="aaacf-117">[out] A pointer to a pointer to the receive folder table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="aaacf-118">返回值</span><span class="sxs-lookup"><span data-stu-id="aaacf-118">Return value</span></span>

<span data-ttu-id="aaacf-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="aaacf-119">S_OK</span></span> 
  
> <span data-ttu-id="aaacf-120">已成功返回接收文件夹表。</span><span class="sxs-lookup"><span data-stu-id="aaacf-120">The receive folder table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="aaacf-121">注解</span><span class="sxs-lookup"><span data-stu-id="aaacf-121">Remarks</span></span>

<span data-ttu-id="aaacf-122">**IMsgStore::GetReceiveFolderTable**方法可访问此表格显示所有的消息存储的属性设置接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="aaacf-122">The **IMsgStore::GetReceiveFolderTable** method provides access to a table that shows the property settings for all of the message store's receive folders.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="aaacf-123">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="aaacf-123">Notes to implementers</span></span>

<span data-ttu-id="aaacf-124">接收文件夹表中所需的列的列表，请参阅[接收文件夹表](receive-folder-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="aaacf-124">For a list of required columns in a receive folder table, see [Receive Folder Tables](receive-folder-tables.md).</span></span> 
  
<span data-ttu-id="aaacf-125">实现您接收文件夹表，以支持设置属性限制**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="aaacf-125">Implement your receive folder tables to support setting property restrictions on the **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property.</span></span> <span data-ttu-id="aaacf-126">此启用对特定的轻松访问接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="aaacf-126">This enables easy access to particular receive folders.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="aaacf-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="aaacf-127">Notes to callers</span></span>

<span data-ttu-id="aaacf-128">_UlFlags_参数中设置 MAPI_UNICODE 标志会影响从[IMAPITable::QueryColumns](imapitable-querycolumns.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="aaacf-128">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> <span data-ttu-id="aaacf-129">此标志还将控制[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。</span><span class="sxs-lookup"><span data-stu-id="aaacf-129">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="aaacf-130">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="aaacf-130">MFCMAPI reference</span></span>

<span data-ttu-id="aaacf-131">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="aaacf-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="aaacf-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="aaacf-132">**File**</span></span>|<span data-ttu-id="aaacf-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="aaacf-133">**Function**</span></span>|<span data-ttu-id="aaacf-134">**Comment**</span><span class="sxs-lookup"><span data-stu-id="aaacf-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aaacf-135">MsgStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="aaacf-135">MsgStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="aaacf-136">CMsgStoreDlg::OnDisplayReceiveFolderTable</span><span class="sxs-lookup"><span data-stu-id="aaacf-136">CMsgStoreDlg::OnDisplayReceiveFolderTable</span></span>  <br/> |<span data-ttu-id="aaacf-137">MFCMAPI 使用**IMsgStore::GetReceiveFolderTable**方法来获取要显示的接收文件夹表。</span><span class="sxs-lookup"><span data-stu-id="aaacf-137">MFCMAPI uses the **IMsgStore::GetReceiveFolderTable** method to get the receive folder table to display.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="aaacf-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aaacf-138">See also</span></span>



[<span data-ttu-id="aaacf-139">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="aaacf-139">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="aaacf-140">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="aaacf-140">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="aaacf-141">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="aaacf-141">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="aaacf-142">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="aaacf-142">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="aaacf-143">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="aaacf-143">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)


[<span data-ttu-id="aaacf-144">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="aaacf-144">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

