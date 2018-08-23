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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 834b010dc4810e26264bb418de9630bc83b99810
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565289"
---
# <a name="imsgserviceadmingetprovidertable"></a><span data-ttu-id="bedb4-103">IMsgServiceAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="bedb4-103">IMsgServiceAdmin::GetProviderTable</span></span>

  
  
<span data-ttu-id="bedb4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bedb4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bedb4-105">提供对提供程序表中，在配置文件中的服务提供商的列表的访问。</span><span class="sxs-lookup"><span data-stu-id="bedb4-105">Provides access to the provider table, a listing of the service providers in the profile.</span></span>
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="bedb4-106">参数</span><span class="sxs-lookup"><span data-stu-id="bedb4-106">Parameters</span></span>

 <span data-ttu-id="bedb4-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bedb4-107">_ulFlags_</span></span>
  
> <span data-ttu-id="bedb4-108">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="bedb4-108">[in] Always NULL.</span></span>
    
 <span data-ttu-id="bedb4-109">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="bedb4-109">_lppTable_</span></span>
  
> <span data-ttu-id="bedb4-110">[输出]指向与提供程序表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="bedb4-110">[out] A pointer to a pointer to the provider table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bedb4-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bedb4-111">Return value</span></span>

<span data-ttu-id="bedb4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bedb4-112">S_OK</span></span> 
  
> <span data-ttu-id="bedb4-113">已成功返回提供程序表中。</span><span class="sxs-lookup"><span data-stu-id="bedb4-113">The provider table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bedb4-114">注解</span><span class="sxs-lookup"><span data-stu-id="bedb4-114">Remarks</span></span>

<span data-ttu-id="bedb4-115">**IMsgServiceAdmin::GetProviderTable**方法提供了访问 MAPI 提供程序表中，列出所有通讯簿、 消息存储和传输提供程序当前安装的配置文件中的表。</span><span class="sxs-lookup"><span data-stu-id="bedb4-115">The **IMsgServiceAdmin::GetProviderTable** method provides access to the MAPI provider table, a table that lists all the address book, message store, and transport providers currently installed in the profile.</span></span> 
  
<span data-ttu-id="bedb4-116">返回通过**IMsgServiceAdmin::GetProviderTable**的提供程序表不能与通过[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)方法返回的提供程序表，包含表示关联的信息的其他行与一个或多个服务提供程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="bedb4-116">Unlike the provider table returned through the [IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md) method, the provider table returned through **IMsgServiceAdmin::GetProviderTable** cannot include additional rows that represent information associated with one or more service providers in the profile.</span></span> 
  
<span data-ttu-id="bedb4-117">提供程序已被删除，或正在使用但被标记为删除，不包括在提供程序表中。</span><span class="sxs-lookup"><span data-stu-id="bedb4-117">Providers that have been deleted, or are in use but have been marked for deletion, are not included in the provider table.</span></span> <span data-ttu-id="bedb4-118">提供程序表是静态的这意味着，后续的新增功能或从配置文件的删除操作不会反映在表。</span><span class="sxs-lookup"><span data-stu-id="bedb4-118">Provider tables are static, meaning that subsequent additions to or deletions from the profile are not reflected in the table.</span></span> 
  
<span data-ttu-id="bedb4-119">如果在配置文件不具有任何提供程序， **GetProviderTable**将返回零行和 S_OK 返回值与 table。</span><span class="sxs-lookup"><span data-stu-id="bedb4-119">If the profile has no providers, **GetProviderTable** returns a table with zero rows and the S_OK return value.</span></span> 
  
<span data-ttu-id="bedb4-120">有关提供程序表中的列的完整列表，请参阅[提供程序表中](provider-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="bedb4-120">For a complete list of the columns in the provider table, see [Provider Table](provider-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="bedb4-121">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="bedb4-121">Notes to callers</span></span>

<span data-ttu-id="bedb4-122">若要检索顺序传输提供程序表中的行，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="bedb4-122">To retrieve the rows of a provider table in transport order, use the following procedure:</span></span>
  
1. <span data-ttu-id="bedb4-123">调用[IMAPITable::Restrict](imapitable-restrict.md)方法来实施属性限制与 MAPI_TRANSPORT_PROVIDER 的**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 属性相匹配。</span><span class="sxs-lookup"><span data-stu-id="bedb4-123">Call the [IMAPITable::Restrict](imapitable-restrict.md) method to impose a property restriction that matches the **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) property with MAPI_TRANSPORT_PROVIDER.</span></span>
    
2. <span data-ttu-id="bedb4-124">调用[IMAPITable::SortTable](imapitable-sorttable.md)方法以按**PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) 列的表格进行排序。</span><span class="sxs-lookup"><span data-stu-id="bedb4-124">Call the [IMAPITable::SortTable](imapitable-sorttable.md) method to sort the table by the **PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) column.</span></span> 
    
3. <span data-ttu-id="bedb4-125">调用[IMAPITable::QueryRows](imapitable-queryrows.md)方法以获取 table 的行。</span><span class="sxs-lookup"><span data-stu-id="bedb4-125">Call the [IMAPITable::QueryRows](imapitable-queryrows.md) method to get the rows of the table.</span></span> 
    
<span data-ttu-id="bedb4-126">这些呼叫的替代方法是使[HrQueryAllRows](hrqueryallrows.md)函数所有适当的数据结构中传递单个呼叫。</span><span class="sxs-lookup"><span data-stu-id="bedb4-126">An alternative to these calls is to make a single call to the [HrQueryAllRows](hrqueryallrows.md) function with all of the appropriate data structures passed in.</span></span> 
  
<span data-ttu-id="bedb4-127">如果检索每个行中的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列时，您可以使用此数组**MAPIUID**结构[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)将调用设置传输顺序。</span><span class="sxs-lookup"><span data-stu-id="bedb4-127">If you retrieve the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) columns in each of the rows, you can use this array of **MAPIUID** structures to set the transport order in a call to [IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md).</span></span>
  
<span data-ttu-id="bedb4-128">设置 MAPI_UNICODE 标志_ulFlags_参数中执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bedb4-128">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter does the following:</span></span> 
  
- <span data-ttu-id="bedb4-129">设置为 Unicode [IMAPITable::QueryColumns](imapitable-querycolumns.md)方法返回的提供程序表中的初始活动列的数据的 string 类型。</span><span class="sxs-lookup"><span data-stu-id="bedb4-129">Sets the string type to Unicode for data returned for the initial active columns of the provider table by the [IMAPITable::QueryColumns](imapitable-querycolumns.md) method.</span></span> <span data-ttu-id="bedb4-130">提供程序表中的初始活动列是**QueryColumns**方法之前包含表呼叫[IMAPITable::SetColumns](imapitable-setcolumns.md)方法的提供程序返回这些列。</span><span class="sxs-lookup"><span data-stu-id="bedb4-130">The initial active columns for a provider table are those columns the **QueryColumns** method returns before the provider that contains the table calls the [IMAPITable::SetColumns](imapitable-setcolumns.md) method.</span></span> 
    
- <span data-ttu-id="bedb4-131">设置为 Unicode **QueryRows**返回的提供程序表中的初始活动行的数据的 string 类型。</span><span class="sxs-lookup"><span data-stu-id="bedb4-131">Sets the string type to Unicode for data returned for the initial active rows of the provider table by **QueryRows**.</span></span> <span data-ttu-id="bedb4-132">提供程序表中的初始活动行是之前的提供程序包含表呼叫**SetColumns** **QueryRows**返回这些行。</span><span class="sxs-lookup"><span data-stu-id="bedb4-132">The initial active rows for a provider table are those rows **QueryRows** returns before the provider that contains the table calls **SetColumns**.</span></span> 
    
- <span data-ttu-id="bedb4-133">控件的排序顺序之前包含提供程序表中的客户端调用[IMAPITable::SortTable](imapitable-sorttable.md)方法，由[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的属性类型。</span><span class="sxs-lookup"><span data-stu-id="bedb4-133">Controls the property types of the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method before the client that contains the provider table calls the [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="bedb4-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bedb4-134">See also</span></span>



[<span data-ttu-id="bedb4-135">IMsgServiceAdmin::GetMsgServiceTable</span><span class="sxs-lookup"><span data-stu-id="bedb4-135">IMsgServiceAdmin::GetMsgServiceTable</span></span>](imsgserviceadmin-getmsgservicetable.md)
  
[<span data-ttu-id="bedb4-136">IMsgServiceAdmin::MsgServiceTransportOrder</span><span class="sxs-lookup"><span data-stu-id="bedb4-136">IMsgServiceAdmin::MsgServiceTransportOrder</span></span>](imsgserviceadmin-msgservicetransportorder.md)
  
[<span data-ttu-id="bedb4-137">IProviderAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="bedb4-137">IProviderAdmin::GetProviderTable</span></span>](iprovideradmin-getprovidertable.md)
  
[<span data-ttu-id="bedb4-138">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bedb4-138">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

