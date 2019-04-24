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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279526"
---
# <a name="iprovideradmingetprovidertable"></a><span data-ttu-id="3c3d9-103">IProviderAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="3c3d9-103">IProviderAdmin::GetProviderTable</span></span>

  
  
<span data-ttu-id="3c3d9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3c3d9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3c3d9-105">提供对邮件服务的提供程序表的访问权限 (邮件服务中的服务提供程序的列表)。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-105">Provides access to the message service's provider table, a list of the service providers in the message service.</span></span>
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="3c3d9-106">参数</span><span class="sxs-lookup"><span data-stu-id="3c3d9-106">Parameters</span></span>

 <span data-ttu-id="3c3d9-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3c3d9-107">_ulFlags_</span></span>
  
> <span data-ttu-id="3c3d9-108">实时标志的位掩码, 用于控制提供程序表的列中返回的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-108">[in] A bitmask of flags that controls the type of the strings returned in the provider table's columns.</span></span> <span data-ttu-id="3c3d9-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="3c3d9-109">The following flag can be set:</span></span>
    
<span data-ttu-id="3c3d9-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3c3d9-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="3c3d9-111">字符串列采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-111">The string columns are in Unicode format.</span></span> <span data-ttu-id="3c3d9-112">如果未设置 MAPI_UNICODE 标志, 则列采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-112">If the MAPI_UNICODE flag is not set, the columns are in ANSI format.</span></span>
    
 <span data-ttu-id="3c3d9-113">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="3c3d9-113">_lppTable_</span></span>
  
> <span data-ttu-id="3c3d9-114">排除指向提供程序表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-114">[out] A pointer to a pointer to the provider table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3c3d9-115">返回值</span><span class="sxs-lookup"><span data-stu-id="3c3d9-115">Return value</span></span>

<span data-ttu-id="3c3d9-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c3d9-116">S_OK</span></span> 
  
> <span data-ttu-id="3c3d9-117">已成功返回 provider 表。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-117">The provider table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3c3d9-118">注解</span><span class="sxs-lookup"><span data-stu-id="3c3d9-118">Remarks</span></span>

<span data-ttu-id="3c3d9-119">**IProviderAdmin:: GetProviderTable**方法检索指向邮件服务的提供程序表的指针, 该表是 MAPI 维护的, 其中包含有关邮件服务中的每个服务提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-119">The **IProviderAdmin::GetProviderTable** method retrieves a pointer to the message service's provider table, a table that MAPI maintains that contains information about each service provider in the message service.</span></span> 
  
<span data-ttu-id="3c3d9-120">与[IMsgServiceAdmin:: GetProviderTable](imsgserviceadmin-getprovidertable.md)方法返回的 provider 表不同, **IProviderAdmin:: GetProviderTable**返回的 provider 表可能包含其他行, 这些行表示与一个或多个邮件服务中的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-120">Unlike the provider table returned by the [IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md) method, the provider table returned by **IProviderAdmin::GetProviderTable** may include additional rows that represent information associated with one or more of the service providers in the message service.</span></span> <span data-ttu-id="3c3d9-121">此额外信息将添加到配置文件中, 其中包含 mapisvc.inf 文件的 "节" 关键字。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-121">This extra information is added to the profile with the "Sections" keyword of the Mapisvc.inf file.</span></span> <span data-ttu-id="3c3d9-122">当提供程序有额外的配置文件节时, 它会在**PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) 属性中存储这些节的**MAPIUID**结构。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-122">When a provider has extra profile sections, it stores the **MAPIUID** structures for these sections in the **PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) property.</span></span> <span data-ttu-id="3c3d9-123">**PR_SERVICE_EXTRA_UIDS**保存在 "邮件服务配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-123">**PR_SERVICE_EXTRA_UIDS** is saved in the message service profile section.</span></span> 
  
<span data-ttu-id="3c3d9-124">已删除或正在使用但已被标记为删除的提供程序不会包括在提供程序表中。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-124">Providers that have been deleted, or are in use but have been marked for deletion, are not included in the provider table.</span></span> <span data-ttu-id="3c3d9-125">提供程序表是静态的, 这意味着在邮件服务中进行的后续添加或删除不会反映在表中。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-125">Provider tables are static, meaning that subsequent additions to or deletions from the message service are not reflected in the table.</span></span> 
  
<span data-ttu-id="3c3d9-126">如果消息服务没有提供程序, 则**IProviderAdmin:: GetProviderTable**将返回一个包含零行和 S_OK 返回值的表。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-126">If the message service has no providers, **IProviderAdmin::GetProviderTable** returns a table with zero rows and the S_OK return value.</span></span> 
  
<span data-ttu-id="3c3d9-127">在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)方法返回的列的格式。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-127">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter affects the format of the columns returned from the [IMAPITable::QueryColumns](imapitable-querycolumns.md) and [IMAPITable::QueryRows](imapitable-queryrows.md) methods.</span></span> 
  
<span data-ttu-id="3c3d9-128">此标志还按[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序控制属性类型。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-128">This flag also controls the property types in the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method.</span></span> 
  
<span data-ttu-id="3c3d9-129">有关 provider 表中各列的完整列表, 请参阅[provider table](provider-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-129">For a complete list of the columns in the provider table, see [Provider Table](provider-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="3c3d9-130">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="3c3d9-130">Notes to callers</span></span>

<span data-ttu-id="3c3d9-131">若要在传输顺序中检索提供程序表的行, 请按**PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) 列对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-131">To retrieve the rows of a provider table in transport order, sort the table by the **PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) column.</span></span> 
  
<span data-ttu-id="3c3d9-132">若要仅检索表示服务提供程序的那些行 (不包含任何额外行), 请将检索限制为其**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列中具有 PT_ERROR 值的行。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-132">To retrieve only those rows that represent service providers (without including any extra rows), limit your retrieval to the rows that have a value of PT_ERROR in their **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) column.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3c3d9-133">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="3c3d9-133">MFCMAPI reference</span></span>

<span data-ttu-id="3c3d9-134">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-134">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3c3d9-135">**文件**</span><span class="sxs-lookup"><span data-stu-id="3c3d9-135">**File**</span></span>|<span data-ttu-id="3c3d9-136">**函数**</span><span class="sxs-lookup"><span data-stu-id="3c3d9-136">**Function**</span></span>|<span data-ttu-id="3c3d9-137">**备注**</span><span class="sxs-lookup"><span data-stu-id="3c3d9-137">**Comment**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="3c3d9-138">MsgServiceTableDlg</span><span class="sxs-lookup"><span data-stu-id="3c3d9-138">MsgServiceTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="3c3d9-139">CMsgServiceTableDlg:: OnDisplayItem</span><span class="sxs-lookup"><span data-stu-id="3c3d9-139">CMsgServiceTableDlg::OnDisplayItem</span></span>  <br/> |<span data-ttu-id="3c3d9-140">MFCMAPI 使用**IProviderAdmin:: GetProviderTable**方法获取要在新对话框中呈现的提供程序表。</span><span class="sxs-lookup"><span data-stu-id="3c3d9-140">MFCMAPI uses the **IProviderAdmin::GetProviderTable** method to get the table of providers to render in a new dialog box.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3c3d9-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c3d9-141">See also</span></span>



[<span data-ttu-id="3c3d9-142">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="3c3d9-142">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md)
  
[<span data-ttu-id="3c3d9-143">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="3c3d9-143">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md)
  
[<span data-ttu-id="3c3d9-144">IMAPITable::QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="3c3d9-144">IMAPITable::QuerySortOrder</span></span>](imapitable-querysortorder.md)
  
[<span data-ttu-id="3c3d9-145">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="3c3d9-145">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
  
[<span data-ttu-id="3c3d9-146">IMsgServiceAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="3c3d9-146">IMsgServiceAdmin::GetProviderTable</span></span>](imsgserviceadmin-getprovidertable.md)
  
[<span data-ttu-id="3c3d9-147">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3c3d9-147">IProviderAdmin : IUnknown</span></span>](iprovideradminiunknown.md)


[<span data-ttu-id="3c3d9-148">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="3c3d9-148">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

