---
title: IMAPISessionGetMsgStoresTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.GetMsgStoresTable
api_type:
- COM
ms.assetid: 77db2dff-4534-440f-a05c-635711cbc2c3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cc0039cf2210446704d25b2156bd4ff50041a524
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586275"
---
# <a name="imapisessiongetmsgstorestable"></a><span data-ttu-id="20f9b-103">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="20f9b-103">IMAPISession::GetMsgStoresTable</span></span>

  
  
<span data-ttu-id="20f9b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20f9b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20f9b-105">提供对消息存储表包含有关会话配置文件中的所有邮件存储的信息的访问。</span><span class="sxs-lookup"><span data-stu-id="20f9b-105">Provides access to the message store table that contains information about all the message stores in the session profile.</span></span>
  
```cpp
HRESULT GetMsgStoresTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="20f9b-106">参数</span><span class="sxs-lookup"><span data-stu-id="20f9b-106">Parameters</span></span>

 <span data-ttu-id="20f9b-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="20f9b-107">_ulFlags_</span></span>
  
> <span data-ttu-id="20f9b-108">[in]位掩码的标志，用于确定字符的字符串的列的格式。</span><span class="sxs-lookup"><span data-stu-id="20f9b-108">[in] A bitmask of flags that determines the format for columns that are character strings.</span></span> <span data-ttu-id="20f9b-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="20f9b-109">The following flag can be set:</span></span>
    
<span data-ttu-id="20f9b-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="20f9b-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="20f9b-111">字符串列的 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="20f9b-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="20f9b-112">如果未设置 MAPI_UNICODE 标志，字符串列的 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="20f9b-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
 <span data-ttu-id="20f9b-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="20f9b-113">_lppTable_</span></span>
  
> <span data-ttu-id="20f9b-114">[输出]指向与消息存储表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="20f9b-114">[out] A pointer to a pointer to the message store table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="20f9b-115">返回值</span><span class="sxs-lookup"><span data-stu-id="20f9b-115">Return value</span></span>

<span data-ttu-id="20f9b-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="20f9b-116">S_OK</span></span> 
  
> <span data-ttu-id="20f9b-117">已成功返回表。</span><span class="sxs-lookup"><span data-stu-id="20f9b-117">The table was successfully returned.</span></span>
    
<span data-ttu-id="20f9b-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="20f9b-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="20f9b-119">设置该 MAPI_UNICODE 标记和会话不支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="20f9b-119">The MAPI_UNICODE flag was set and the session does not support Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="20f9b-120">注解</span><span class="sxs-lookup"><span data-stu-id="20f9b-120">Remarks</span></span>

<span data-ttu-id="20f9b-121">**IMAPISession::GetMsgStoresTable**方法检索指向消息存储表的指针，由 MAPI 维护表包含有关配置文件中每个打开的邮件存储的信息。</span><span class="sxs-lookup"><span data-stu-id="20f9b-121">The **IMAPISession::GetMsgStoresTable** method retrieves a pointer to the message store table, a table maintained by MAPI that contains information about each open message store in the profile.</span></span> 
  
<span data-ttu-id="20f9b-122">将表存储有关必需的和可选消息中的列的完整列表，请参阅[邮件存储表](message-store-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="20f9b-122">For a complete list of required and optional columns in the message store table, see [Message Store Tables](message-store-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="20f9b-123">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="20f9b-123">Notes to callers</span></span>

<span data-ttu-id="20f9b-124">由于 MAPI 发生更改时在会话过程中更新消息存储表，调用消息存储表进行注册，以这些更改的通知的**Advise**方法。</span><span class="sxs-lookup"><span data-stu-id="20f9b-124">Because MAPI updates the message store table during the session whenever changes occur, call the **Advise** method of the message store table to register to be notified of these changes.</span></span> <span data-ttu-id="20f9b-125">可能发生的更改包括的新消息存储库添加、 删除现有的存储，并更改为默认存储。</span><span class="sxs-lookup"><span data-stu-id="20f9b-125">Possible changes include the addition of new message stores, removal of existing stores, and changes to the default store.</span></span> 
  
<span data-ttu-id="20f9b-126">_UlFlags_参数中设置 MAPI_UNICODE 标志会影响从[IMAPITable::QueryColumns](imapitable-querycolumns.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="20f9b-126">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> <span data-ttu-id="20f9b-127">此标志还将控制[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。</span><span class="sxs-lookup"><span data-stu-id="20f9b-127">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="20f9b-128">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="20f9b-128">MFCMAPI reference</span></span>

<span data-ttu-id="20f9b-129">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="20f9b-129">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="20f9b-130">**文件**</span><span class="sxs-lookup"><span data-stu-id="20f9b-130">**File**</span></span>|<span data-ttu-id="20f9b-131">**函数**</span><span class="sxs-lookup"><span data-stu-id="20f9b-131">**Function**</span></span>|<span data-ttu-id="20f9b-132">**Comment**</span><span class="sxs-lookup"><span data-stu-id="20f9b-132">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20f9b-133">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="20f9b-133">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="20f9b-134">CMainDlg::OnOpenMessageStoreTable</span><span class="sxs-lookup"><span data-stu-id="20f9b-134">CMainDlg::OnOpenMessageStoreTable</span></span>  <br/> |<span data-ttu-id="20f9b-135">MFCMAPI 使用**IMAPISession::GetMsgStoresTable**方法获取消息存储表，以使其可以在主要对话框的 MFCMAPI 呈现。</span><span class="sxs-lookup"><span data-stu-id="20f9b-135">MFCMAPI uses the **IMAPISession::GetMsgStoresTable** method to obtain the message store table so that it can be rendered in the main dialog box of MFCMAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="20f9b-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20f9b-136">See also</span></span>



[<span data-ttu-id="20f9b-137">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="20f9b-137">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
  
[<span data-ttu-id="20f9b-138">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="20f9b-138">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="20f9b-139">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="20f9b-139">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="20f9b-140">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="20f9b-140">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="20f9b-141">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="20f9b-141">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="20f9b-142">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="20f9b-142">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="20f9b-143">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="20f9b-143">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="20f9b-144">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="20f9b-144">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="20f9b-145">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="20f9b-145">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="20f9b-146">邮件存储区表</span><span class="sxs-lookup"><span data-stu-id="20f9b-146">Message Store Tables</span></span>](message-store-tables.md)

