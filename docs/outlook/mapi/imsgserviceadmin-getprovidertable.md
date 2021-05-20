---
title: IMsgServiceAdminGetProviderTable
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.GetProviderTable
api_type:
- COM
ms.assetid: 7180bff2-91ad-4e11-923e-2a9acefa3215
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1185a35df471fc3f85cbf50fd8ad3baa3927e72b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428765"
---
# <a name="imsgserviceadmingetprovidertable"></a><span data-ttu-id="2feb6-103">IMsgServiceAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="2feb6-103">IMsgServiceAdmin::GetProviderTable</span></span>

  
  
<span data-ttu-id="2feb6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2feb6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2feb6-105">提供对提供程序表（配置文件中的服务提供程序列表）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2feb6-105">Provides access to the provider table, a listing of the service providers in the profile.</span></span>
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="2feb6-106">参数</span><span class="sxs-lookup"><span data-stu-id="2feb6-106">Parameters</span></span>

 <span data-ttu-id="2feb6-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2feb6-107">_ulFlags_</span></span>
  
> <span data-ttu-id="2feb6-108">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2feb6-108">[in] Always NULL.</span></span>
    
 <span data-ttu-id="2feb6-109">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="2feb6-109">_lppTable_</span></span>
  
> <span data-ttu-id="2feb6-110">[out]指向指向提供程序表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2feb6-110">[out] A pointer to a pointer to the provider table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2feb6-111">返回值</span><span class="sxs-lookup"><span data-stu-id="2feb6-111">Return value</span></span>

<span data-ttu-id="2feb6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2feb6-112">S_OK</span></span> 
  
> <span data-ttu-id="2feb6-113">已成功返回提供程序表。</span><span class="sxs-lookup"><span data-stu-id="2feb6-113">The provider table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2feb6-114">备注</span><span class="sxs-lookup"><span data-stu-id="2feb6-114">Remarks</span></span>

<span data-ttu-id="2feb6-115">**IMsgServiceAdmin：：GetProviderTable** 方法提供对 MAPI 提供程序表的访问，该表列出了配置文件中当前安装的所有通讯簿、邮件存储和传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2feb6-115">The **IMsgServiceAdmin::GetProviderTable** method provides access to the MAPI provider table, a table that lists all the address book, message store, and transport providers currently installed in the profile.</span></span> 
  
<span data-ttu-id="2feb6-116">与通过 [IProviderAdmin：：GetProviderTable](iprovideradmin-getprovidertable.md) 方法返回的提供程序表不同，通过 **IMsgServiceAdmin：：GetProviderTable** 返回的提供程序表不能包含表示与配置文件中的一个或多个服务提供程序关联的信息的其他行。</span><span class="sxs-lookup"><span data-stu-id="2feb6-116">Unlike the provider table returned through the [IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md) method, the provider table returned through **IMsgServiceAdmin::GetProviderTable** cannot include additional rows that represent information associated with one or more service providers in the profile.</span></span> 
  
<span data-ttu-id="2feb6-117">提供程序表中不包含已删除或已在使用中但标记为删除的提供程序。</span><span class="sxs-lookup"><span data-stu-id="2feb6-117">Providers that have been deleted, or are in use but have been marked for deletion, are not included in the provider table.</span></span> <span data-ttu-id="2feb6-118">提供程序表是静态的，这意味着对配置文件的后续添加或删除不会反映在表中。</span><span class="sxs-lookup"><span data-stu-id="2feb6-118">Provider tables are static, meaning that subsequent additions to or deletions from the profile are not reflected in the table.</span></span> 
  
<span data-ttu-id="2feb6-119">如果配置文件没有提供程序 **，GetProviderTable** 将返回包含零行的表，S_OK返回值。</span><span class="sxs-lookup"><span data-stu-id="2feb6-119">If the profile has no providers, **GetProviderTable** returns a table with zero rows and the S_OK return value.</span></span> 
  
<span data-ttu-id="2feb6-120">有关提供程序表中的列的完整列表，请参阅[Provider Table。](provider-tables.md)</span><span class="sxs-lookup"><span data-stu-id="2feb6-120">For a complete list of the columns in the provider table, see [Provider Table](provider-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="2feb6-121">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2feb6-121">Notes to callers</span></span>

<span data-ttu-id="2feb6-122">若要按传输顺序检索提供程序表的行，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="2feb6-122">To retrieve the rows of a provider table in transport order, use the following procedure:</span></span>
  
1. <span data-ttu-id="2feb6-123">调用[IMAPITable：：Restrict](imapitable-restrict.md)方法以施加与[PidTagResourceType PR_RESOURCE_TYPE (PidTagResourceType](pidtagresourcetype-canonical-property.md)) 属性与 MAPI_TRANSPORT_PROVIDER。 </span><span class="sxs-lookup"><span data-stu-id="2feb6-123">Call the [IMAPITable::Restrict](imapitable-restrict.md) method to impose a property restriction that matches the **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) property with MAPI_TRANSPORT_PROVIDER.</span></span>
    
2. <span data-ttu-id="2feb6-124">调用[IMAPITable：：SortTable](imapitable-sorttable.md)方法按[PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)列PR_PROVIDER_ORDINAL (表) 排序。 </span><span class="sxs-lookup"><span data-stu-id="2feb6-124">Call the [IMAPITable::SortTable](imapitable-sorttable.md) method to sort the table by the **PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) column.</span></span> 
    
3. <span data-ttu-id="2feb6-125">调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法来获取表的行。</span><span class="sxs-lookup"><span data-stu-id="2feb6-125">Call the [IMAPITable::QueryRows](imapitable-queryrows.md) method to get the rows of the table.</span></span> 
    
<span data-ttu-id="2feb6-126">这些调用的替代方法是使用传入的所有适当数据结构对 [HrQueryAllRows](hrqueryallrows.md) 函数进行单个调用。</span><span class="sxs-lookup"><span data-stu-id="2feb6-126">An alternative to these calls is to make a single call to the [HrQueryAllRows](hrqueryallrows.md) function with all of the appropriate data structures passed in.</span></span> 
  
<span data-ttu-id="2feb6-127">如果检索每行中的 **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列，可以使用 **此 MAPIUID** 结构数组在 [调用 IMsgServiceAdmin：：MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)时设置传输顺序。</span><span class="sxs-lookup"><span data-stu-id="2feb6-127">If you retrieve the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) columns in each of the rows, you can use this array of **MAPIUID** structures to set the transport order in a call to [IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md).</span></span>
  
<span data-ttu-id="2feb6-128">在  _ulFlags_ MAPI_UNICODE设置 MAPI_UNICODE 标记将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2feb6-128">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter does the following:</span></span> 
  
- <span data-ttu-id="2feb6-129">对于由 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 方法为提供程序表的初始活动列返回的数据，将字符串类型设置为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="2feb6-129">Sets the string type to Unicode for data returned for the initial active columns of the provider table by the [IMAPITable::QueryColumns](imapitable-querycolumns.md) method.</span></span> <span data-ttu-id="2feb6-130">提供程序表的初始活动列是 **QueryColumns** 方法在包含该表的提供程序调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 方法之前返回的列。</span><span class="sxs-lookup"><span data-stu-id="2feb6-130">The initial active columns for a provider table are those columns the **QueryColumns** method returns before the provider that contains the table calls the [IMAPITable::SetColumns](imapitable-setcolumns.md) method.</span></span> 
    
- <span data-ttu-id="2feb6-131">对于 QueryRows 为提供程序表的初始活动行返回的数据，将字符串类型设置为 **Unicode。**</span><span class="sxs-lookup"><span data-stu-id="2feb6-131">Sets the string type to Unicode for data returned for the initial active rows of the provider table by **QueryRows**.</span></span> <span data-ttu-id="2feb6-132">提供程序表的初始活动行是 **QueryRows** 在包含该表的提供程序调用 **SetColumns** 之前返回的行。</span><span class="sxs-lookup"><span data-stu-id="2feb6-132">The initial active rows for a provider table are those rows **QueryRows** returns before the provider that contains the table calls **SetColumns**.</span></span> 
    
- <span data-ttu-id="2feb6-133">在包含提供程序表的客户端调用[IMAPITable：：SortTable](imapitable-sorttable.md)方法之前，控制[IMAPITable：：QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。</span><span class="sxs-lookup"><span data-stu-id="2feb6-133">Controls the property types of the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method before the client that contains the provider table calls the [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="2feb6-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2feb6-134">See also</span></span>



[<span data-ttu-id="2feb6-135">IMsgServiceAdmin::GetMsgServiceTable</span><span class="sxs-lookup"><span data-stu-id="2feb6-135">IMsgServiceAdmin::GetMsgServiceTable</span></span>](imsgserviceadmin-getmsgservicetable.md)
  
[<span data-ttu-id="2feb6-136">IMsgServiceAdmin::MsgServiceTransportOrder</span><span class="sxs-lookup"><span data-stu-id="2feb6-136">IMsgServiceAdmin::MsgServiceTransportOrder</span></span>](imsgserviceadmin-msgservicetransportorder.md)
  
[<span data-ttu-id="2feb6-137">IProviderAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="2feb6-137">IProviderAdmin::GetProviderTable</span></span>](iprovideradmin-getprovidertable.md)
  
[<span data-ttu-id="2feb6-138">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2feb6-138">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

