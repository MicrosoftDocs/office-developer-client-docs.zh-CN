---
title: IProviderAdminGetProviderTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.GetProviderTable
api_type:
- COM
ms.assetid: e9deaa7c-430b-4e97-8ed6-f7c615956e0f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ddfcdd95f0423ba92c37c434f18078eadf90d82
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594017"
---
# <a name="iprovideradmingetprovidertable"></a><span data-ttu-id="c9dbe-103">IProviderAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="c9dbe-103">IProviderAdmin::GetProviderTable</span></span>

  
  
<span data-ttu-id="c9dbe-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c9dbe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c9dbe-105">提供对邮件服务提供程序表中，消息服务的服务提供商的列表的访问。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-105">Provides access to the message service's provider table, a list of the service providers in the message service.</span></span>
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="c9dbe-106">参数</span><span class="sxs-lookup"><span data-stu-id="c9dbe-106">Parameters</span></span>

 <span data-ttu-id="c9dbe-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c9dbe-107">_ulFlags_</span></span>
  
> <span data-ttu-id="c9dbe-108">[in]位掩码的标志的控制提供程序表的列中返回的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-108">[in] A bitmask of flags that controls the type of the strings returned in the provider table's columns.</span></span> <span data-ttu-id="c9dbe-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="c9dbe-109">The following flag can be set:</span></span>
    
<span data-ttu-id="c9dbe-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="c9dbe-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="c9dbe-111">字符串列的 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="c9dbe-112">如果未设置 MAPI_UNICODE 标志，列的 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-112">If the MAPI_UNICODE flag is not set, the columns are in ANSI format.</span></span>
    
 <span data-ttu-id="c9dbe-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="c9dbe-113">_lppTable_</span></span>
  
> <span data-ttu-id="c9dbe-114">[输出]指向与提供程序表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-114">[out] A pointer to a pointer to the provider table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c9dbe-115">返回值</span><span class="sxs-lookup"><span data-stu-id="c9dbe-115">Return value</span></span>

<span data-ttu-id="c9dbe-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9dbe-116">S_OK</span></span> 
  
> <span data-ttu-id="c9dbe-117">已成功返回提供程序表中。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-117">The provider table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c9dbe-118">注解</span><span class="sxs-lookup"><span data-stu-id="c9dbe-118">Remarks</span></span>

<span data-ttu-id="c9dbe-119">**IProviderAdmin::GetProviderTable**方法检索与邮件服务提供程序表，MAPI 维护，包含有关每个邮件服务中的服务提供商信息表的指针。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-119">The **IProviderAdmin::GetProviderTable** method retrieves a pointer to the message service's provider table, a table that MAPI maintains that contains information about each service provider in the message service.</span></span> 
  
<span data-ttu-id="c9dbe-120">返回**IProviderAdmin::GetProviderTable**的提供程序表可能与不同[IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md)方法返回的提供程序表，包括表示与一个或多个关联的信息的其他行邮件服务服务提供商。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-120">Unlike the provider table returned by the [IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md) method, the provider table returned by **IProviderAdmin::GetProviderTable** may include additional rows that represent information associated with one or more of the service providers in the message service.</span></span> <span data-ttu-id="c9dbe-121">此额外信息添加到使用 Mapisvc.inf 文件的"部分"关键字的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-121">This extra information is added to the profile with the "Sections" keyword of the Mapisvc.inf file.</span></span> <span data-ttu-id="c9dbe-122">当提供程序具有额外的配置文件节时，它**PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) 属性中存储以下各节**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-122">When a provider has extra profile sections, it stores the **MAPIUID** structures for these sections in the **PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) property.</span></span> <span data-ttu-id="c9dbe-123">**PR_SERVICE_EXTRA_UIDS**保存在邮件服务配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-123">**PR_SERVICE_EXTRA_UIDS** is saved in the message service profile section.</span></span> 
  
<span data-ttu-id="c9dbe-124">提供程序已被删除，或正在使用但被标记为删除，不包括在提供程序表中。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-124">Providers that have been deleted, or are in use but have been marked for deletion, are not included in the provider table.</span></span> <span data-ttu-id="c9dbe-125">提供程序表是静态的这意味着，后续的新增功能或删除邮件服务的内容不会反映在表。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-125">Provider tables are static, meaning that subsequent additions to or deletions from the message service are not reflected in the table.</span></span> 
  
<span data-ttu-id="c9dbe-126">如果邮件服务没有提供程序，请**IProviderAdmin::GetProviderTable**将返回零行和 S_OK 返回值与 table。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-126">If the message service has no providers, **IProviderAdmin::GetProviderTable** returns a table with zero rows and the S_OK return value.</span></span> 
  
<span data-ttu-id="c9dbe-127">_UlFlags_参数中设置 MAPI_UNICODE 标志会影响从[IMAPITable::QueryColumns](imapitable-querycolumns.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-127">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> 
  
<span data-ttu-id="c9dbe-128">此标志还将控制[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-128">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
<span data-ttu-id="c9dbe-129">有关提供程序表中的列的完整列表，请参阅[提供程序表中](provider-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-129">For a complete list of the columns in the provider table, see [Provider Table](provider-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c9dbe-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c9dbe-130">Notes to callers</span></span>

<span data-ttu-id="c9dbe-131">若要检索顺序传输提供程序表中的行，请按**PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) 列进行排序的表。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-131">To retrieve the rows of a provider table in transport order, sort the table by the **PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) column.</span></span> 
  
<span data-ttu-id="c9dbe-132">若要检索表示服务提供商 （不包括任何额外的行） 的行，限制您检索到有的 PT_ERROR 其**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列中的值的行。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-132">To retrieve only those rows that represent service providers (without including any extra rows), limit your retrieval to the rows that have a value of PT_ERROR in their **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) column.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c9dbe-133">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="c9dbe-133">MFCMAPI reference</span></span>

<span data-ttu-id="c9dbe-134">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c9dbe-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="c9dbe-135">**File**</span></span>|<span data-ttu-id="c9dbe-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="c9dbe-136">**Function**</span></span>|<span data-ttu-id="c9dbe-137">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c9dbe-137">**Comment**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="c9dbe-138">MsgServiceTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="c9dbe-138">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="c9dbe-139">CMsgServiceTableDlg::OnDisplayItem</span><span class="sxs-lookup"><span data-stu-id="c9dbe-139">CMsgServiceTableDlg::OnDisplayItem</span></span>  <br/> |<span data-ttu-id="c9dbe-140">MFCMAPI 使用**IProviderAdmin::GetProviderTable**方法来获取提供程序，呈现在新的对话框中的表。</span><span class="sxs-lookup"><span data-stu-id="c9dbe-140">MFCMAPI uses the **IProviderAdmin::GetProviderTable** method to get the table of providers to render in a new dialog box.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c9dbe-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9dbe-141">See also</span></span>



[<span data-ttu-id="c9dbe-142">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="c9dbe-142">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="c9dbe-143">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="c9dbe-143">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="c9dbe-144">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="c9dbe-144">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="c9dbe-145">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="c9dbe-145">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="c9dbe-146">IMsgServiceAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="c9dbe-146">IMsgServiceAdmin::GetProviderTable</span></span>](imsgserviceadmin-getprovidertable.md)
  
[<span data-ttu-id="c9dbe-147">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c9dbe-147">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)


[<span data-ttu-id="c9dbe-148">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c9dbe-148">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

