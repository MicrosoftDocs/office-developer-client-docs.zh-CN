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
ms.openlocfilehash: 5fced633023ebf00efaf5b667dc7994eeb5de316
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338827"
---
# <a name="imapisessiongetmsgstorestable"></a><span data-ttu-id="b1221-103">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="b1221-103">IMAPISession::GetMsgStoresTable</span></span>

  
  
<span data-ttu-id="b1221-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b1221-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b1221-105">提供对包含有关会话配置文件中的所有邮件存储区的信息的邮件存储表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b1221-105">Provides access to the message store table that contains information about all the message stores in the session profile.</span></span>
  
```cpp
HRESULT GetMsgStoresTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="b1221-106">参数</span><span class="sxs-lookup"><span data-stu-id="b1221-106">Parameters</span></span>

 <span data-ttu-id="b1221-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b1221-107">_ulFlags_</span></span>
  
> <span data-ttu-id="b1221-108">实时标志的位掩码, 用于确定作为字符字符串的列的格式。</span><span class="sxs-lookup"><span data-stu-id="b1221-108">[in] A bitmask of flags that determines the format for columns that are character strings.</span></span> <span data-ttu-id="b1221-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="b1221-109">The following flag can be set:</span></span>
    
<span data-ttu-id="b1221-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b1221-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b1221-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b1221-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="b1221-112">如果未设置 MAPI_UNICODE 标志, 则字符串列的格式为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="b1221-112">If the MAPI_UNICODE flag is not set, the string columns are in ANSI format.</span></span>
    
 <span data-ttu-id="b1221-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="b1221-113">_lppTable_</span></span>
  
> <span data-ttu-id="b1221-114">排除指向邮件存储表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b1221-114">[out] A pointer to a pointer to the message store table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b1221-115">返回值</span><span class="sxs-lookup"><span data-stu-id="b1221-115">Return value</span></span>

<span data-ttu-id="b1221-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1221-116">S_OK</span></span> 
  
> <span data-ttu-id="b1221-117">成功返回表。</span><span class="sxs-lookup"><span data-stu-id="b1221-117">The table was successfully returned.</span></span>
    
<span data-ttu-id="b1221-118">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="b1221-118">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="b1221-119">已设置 MAPI_UNICODE 标志, 且会话不支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="b1221-119">The MAPI_UNICODE flag was set and the session does not support Unicode.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b1221-120">注解</span><span class="sxs-lookup"><span data-stu-id="b1221-120">Remarks</span></span>

<span data-ttu-id="b1221-121">**IMAPISession:: GetMsgStoresTable**方法检索指向邮件存储表的指针, 它是由 MAPI 维护的表, 其中包含有关配置文件中每个打开的邮件存储区的信息。</span><span class="sxs-lookup"><span data-stu-id="b1221-121">The **IMAPISession::GetMsgStoresTable** method retrieves a pointer to the message store table, a table maintained by MAPI that contains information about each open message store in the profile.</span></span> 
  
<span data-ttu-id="b1221-122">有关邮件存储表中的必填和可选的列的完整列表, 请参阅[message store Tables](message-store-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="b1221-122">For a complete list of required and optional columns in the message store table, see [Message Store Tables](message-store-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b1221-123">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b1221-123">Notes to callers</span></span>

<span data-ttu-id="b1221-124">由于每次发生更改时 MAPI 都会在会话过程中更新邮件存储表, 因此请调用邮件存储表的**Advise**方法以注册, 以获得这些更改的通知。</span><span class="sxs-lookup"><span data-stu-id="b1221-124">Because MAPI updates the message store table during the session whenever changes occur, call the **Advise** method of the message store table to register to be notified of these changes.</span></span> <span data-ttu-id="b1221-125">可能的更改包括添加新的邮件存储、删除现有存储和更改为默认存储。</span><span class="sxs-lookup"><span data-stu-id="b1221-125">Possible changes include the addition of new message stores, removal of existing stores, and changes to the default store.</span></span> 
  
<span data-ttu-id="b1221-126">在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="b1221-126">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> <span data-ttu-id="b1221-127">此标志还按[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序控制属性类型。</span><span class="sxs-lookup"><span data-stu-id="b1221-127">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b1221-128">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="b1221-128">MFCMAPI reference</span></span>

<span data-ttu-id="b1221-129">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b1221-129">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b1221-130">**文件**</span><span class="sxs-lookup"><span data-stu-id="b1221-130">**File**</span></span>|<span data-ttu-id="b1221-131">**函数**</span><span class="sxs-lookup"><span data-stu-id="b1221-131">**Function**</span></span>|<span data-ttu-id="b1221-132">**备注**</span><span class="sxs-lookup"><span data-stu-id="b1221-132">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b1221-133">MainDlg</span><span class="sxs-lookup"><span data-stu-id="b1221-133">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="b1221-134">CMainDlg:: OnOpenMessageStoreTable</span><span class="sxs-lookup"><span data-stu-id="b1221-134">CMainDlg::OnOpenMessageStoreTable</span></span>  <br/> |<span data-ttu-id="b1221-135">MFCMAPI 使用**IMAPISession:: GetMsgStoresTable**方法获取邮件存储表, 以便它可以在 MFCMAPI 的主对话框中呈现。</span><span class="sxs-lookup"><span data-stu-id="b1221-135">MFCMAPI uses the **IMAPISession::GetMsgStoresTable** method to obtain the message store table so that it can be rendered in the main dialog box of MFCMAPI.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b1221-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1221-136">See also</span></span>



[<span data-ttu-id="b1221-137">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="b1221-137">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
  
[<span data-ttu-id="b1221-138">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b1221-138">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="b1221-139">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="b1221-139">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="b1221-140">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="b1221-140">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="b1221-141">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="b1221-141">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="b1221-142">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="b1221-142">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="b1221-143">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="b1221-143">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
  
[<span data-ttu-id="b1221-144">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b1221-144">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="b1221-145">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b1221-145">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="b1221-146">邮件存储表</span><span class="sxs-lookup"><span data-stu-id="b1221-146">Message Store Tables</span></span>](message-store-tables.md)

