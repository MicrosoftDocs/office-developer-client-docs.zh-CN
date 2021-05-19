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
ms.openlocfilehash: 843a61696def4398c22a244a7f3f66d7e5dc75ce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434471"
---
# <a name="iprovideradmingetprovidertable"></a><span data-ttu-id="07dac-103">IProviderAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="07dac-103">IProviderAdmin::GetProviderTable</span></span>

  
  
<span data-ttu-id="07dac-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="07dac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="07dac-105">提供对邮件服务提供程序表（邮件服务中的服务提供程序列表）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="07dac-105">Provides access to the message service's provider table, a list of the service providers in the message service.</span></span>
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="07dac-106">参数</span><span class="sxs-lookup"><span data-stu-id="07dac-106">Parameters</span></span>

 <span data-ttu-id="07dac-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="07dac-107">_ulFlags_</span></span>
  
> <span data-ttu-id="07dac-108">[in]控制提供程序表列返回的字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="07dac-108">[in] A bitmask of flags that controls the type of the strings returned in the provider table's columns.</span></span> <span data-ttu-id="07dac-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="07dac-109">The following flag can be set:</span></span>
    
<span data-ttu-id="07dac-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="07dac-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="07dac-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="07dac-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="07dac-112">如果未MAPI_UNICODE，则列采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="07dac-112">If the MAPI_UNICODE flag is not set, the columns are in ANSI format.</span></span>
    
 <span data-ttu-id="07dac-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="07dac-113">_lppTable_</span></span>
  
> <span data-ttu-id="07dac-114">[out]指向指向提供程序表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="07dac-114">[out] A pointer to a pointer to the provider table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="07dac-115">返回值</span><span class="sxs-lookup"><span data-stu-id="07dac-115">Return value</span></span>

<span data-ttu-id="07dac-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="07dac-116">S_OK</span></span> 
  
> <span data-ttu-id="07dac-117">已成功返回提供程序表。</span><span class="sxs-lookup"><span data-stu-id="07dac-117">The provider table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="07dac-118">备注</span><span class="sxs-lookup"><span data-stu-id="07dac-118">Remarks</span></span>

<span data-ttu-id="07dac-119">**IProviderAdmin：：GetProviderTable** 方法检索指向邮件服务的提供程序表（MAPI 维护的包含有关邮件服务中每个服务提供程序的信息的表）的指针。</span><span class="sxs-lookup"><span data-stu-id="07dac-119">The **IProviderAdmin::GetProviderTable** method retrieves a pointer to the message service's provider table, a table that MAPI maintains that contains information about each service provider in the message service.</span></span> 
  
<span data-ttu-id="07dac-120">与 [IMsgServiceAdmin：：GetProviderTable](imsgserviceadmin-getprovidertable.md) 方法返回的提供程序表不同 **，IProviderAdmin：：GetProviderTable** 返回的提供程序表可能包含表示与邮件服务中的一个或多个服务提供程序关联的信息的其他行。</span><span class="sxs-lookup"><span data-stu-id="07dac-120">Unlike the provider table returned by the [IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md) method, the provider table returned by **IProviderAdmin::GetProviderTable** may include additional rows that represent information associated with one or more of the service providers in the message service.</span></span> <span data-ttu-id="07dac-121">此额外信息将添加到具有 Mapisvc.inf 文件的"Sections"关键字的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="07dac-121">This extra information is added to the profile with the "Sections" keyword of the Mapisvc.inf file.</span></span> <span data-ttu-id="07dac-122">当提供程序具有额外的配置文件节时，它将这些节的 **MAPIUID** 结构存储在 **PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="07dac-122">When a provider has extra profile sections, it stores the **MAPIUID** structures for these sections in the **PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) property.</span></span> <span data-ttu-id="07dac-123">**PR_SERVICE_EXTRA_UIDS** 保存在邮件服务配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="07dac-123">**PR_SERVICE_EXTRA_UIDS** is saved in the message service profile section.</span></span> 
  
<span data-ttu-id="07dac-124">提供程序表中不包含已删除或已在使用中但标记为删除的提供程序。</span><span class="sxs-lookup"><span data-stu-id="07dac-124">Providers that have been deleted, or are in use but have been marked for deletion, are not included in the provider table.</span></span> <span data-ttu-id="07dac-125">提供程序表是静态的，这意味着对邮件服务的后续添加或删除不会反映在表中。</span><span class="sxs-lookup"><span data-stu-id="07dac-125">Provider tables are static, meaning that subsequent additions to or deletions from the message service are not reflected in the table.</span></span> 
  
<span data-ttu-id="07dac-126">如果邮件服务没有提供程序，则 **IProviderAdmin：：GetProviderTable** 返回零行的表，S_OK返回值。</span><span class="sxs-lookup"><span data-stu-id="07dac-126">If the message service has no providers, **IProviderAdmin::GetProviderTable** returns a table with zero rows and the S_OK return value.</span></span> 
  
<span data-ttu-id="07dac-127">在  _ulFlags_ 参数中设置 MAPI_UNICODE 标志会影响 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="07dac-127">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> 
  
<span data-ttu-id="07dac-128">此标志还按 [IMAPITable：：QuerySortOrder](imapitable-querysortorder.md) 方法返回的排序顺序控制属性类型。</span><span class="sxs-lookup"><span data-stu-id="07dac-128">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
<span data-ttu-id="07dac-129">有关提供程序表中的列的完整列表，请参阅[Provider Table。](provider-tables.md)</span><span class="sxs-lookup"><span data-stu-id="07dac-129">For a complete list of the columns in the provider table, see [Provider Table](provider-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="07dac-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="07dac-130">Notes to callers</span></span>

<span data-ttu-id="07dac-131">若要按传输顺序检索提供程序表的行，请按[PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)列PR_PROVIDER_ORDINAL (表) 排序。 </span><span class="sxs-lookup"><span data-stu-id="07dac-131">To retrieve the rows of a provider table in transport order, sort the table by the **PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) column.</span></span> 
  
<span data-ttu-id="07dac-132">若要仅检索那些表示服务提供商 (而不包括任何额外行) 的行，请限制检索其 PR_RESOURCE_TYPE ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列中值为 **PT_ERROR** 的行。</span><span class="sxs-lookup"><span data-stu-id="07dac-132">To retrieve only those rows that represent service providers (without including any extra rows), limit your retrieval to the rows that have a value of PT_ERROR in their **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) column.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="07dac-133">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="07dac-133">MFCMAPI reference</span></span>

<span data-ttu-id="07dac-134">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="07dac-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="07dac-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="07dac-135">**File**</span></span>|<span data-ttu-id="07dac-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="07dac-136">**Function**</span></span>|<span data-ttu-id="07dac-137">**备注**</span><span class="sxs-lookup"><span data-stu-id="07dac-137">**Comment**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="07dac-138">MsgServiceTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="07dac-138">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="07dac-139">CMsgServiceTableDlg：：OnDisplayItem</span><span class="sxs-lookup"><span data-stu-id="07dac-139">CMsgServiceTableDlg::OnDisplayItem</span></span>  <br/> |<span data-ttu-id="07dac-140">MFCMAPI 使用 **IProviderAdmin：：GetProviderTable** 方法获取要呈现到新对话框中的提供程序表。</span><span class="sxs-lookup"><span data-stu-id="07dac-140">MFCMAPI uses the **IProviderAdmin::GetProviderTable** method to get the table of providers to render in a new dialog box.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="07dac-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07dac-141">See also</span></span>



[<span data-ttu-id="07dac-142">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="07dac-142">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="07dac-143">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="07dac-143">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="07dac-144">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="07dac-144">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="07dac-145">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="07dac-145">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="07dac-146">IMsgServiceAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="07dac-146">IMsgServiceAdmin::GetProviderTable</span></span>](imsgserviceadmin-getprovidertable.md)
  
[<span data-ttu-id="07dac-147">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="07dac-147">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)


[<span data-ttu-id="07dac-148">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="07dac-148">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

