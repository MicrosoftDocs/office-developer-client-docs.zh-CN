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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317379"
---
# <a name="imsgserviceadmingetprovidertable"></a><span data-ttu-id="7a28e-103">IMsgServiceAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="7a28e-103">IMsgServiceAdmin::GetProviderTable</span></span>

  
  
<span data-ttu-id="7a28e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7a28e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7a28e-105">提供对提供程序表的访问权限 (配置文件中的服务提供程序的列表)。</span><span class="sxs-lookup"><span data-stu-id="7a28e-105">Provides access to the provider table, a listing of the service providers in the profile.</span></span>
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="7a28e-106">参数</span><span class="sxs-lookup"><span data-stu-id="7a28e-106">Parameters</span></span>

 <span data-ttu-id="7a28e-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="7a28e-107">_ulFlags_</span></span>
  
> <span data-ttu-id="7a28e-108">实时始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7a28e-108">[in] Always NULL.</span></span>
    
 <span data-ttu-id="7a28e-109">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="7a28e-109">_lppTable_</span></span>
  
> <span data-ttu-id="7a28e-110">排除指向提供程序表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7a28e-110">[out] A pointer to a pointer to the provider table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7a28e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7a28e-111">Return value</span></span>

<span data-ttu-id="7a28e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a28e-112">S_OK</span></span> 
  
> <span data-ttu-id="7a28e-113">已成功返回 provider 表。</span><span class="sxs-lookup"><span data-stu-id="7a28e-113">The provider table was successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7a28e-114">注解</span><span class="sxs-lookup"><span data-stu-id="7a28e-114">Remarks</span></span>

<span data-ttu-id="7a28e-115">**IMsgServiceAdmin:: GetProviderTable**方法提供对 MAPI 提供程序表的访问, 该表列出了当前安装在配置文件中的所有通讯簿、邮件存储和传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a28e-115">The **IMsgServiceAdmin::GetProviderTable** method provides access to the MAPI provider table, a table that lists all the address book, message store, and transport providers currently installed in the profile.</span></span> 
  
<span data-ttu-id="7a28e-116">与通过[IProviderAdmin:: GetProviderTable](iprovideradmin-getprovidertable.md)方法返回的 provider 表不同, 通过**IMsgServiceAdmin:: GetProviderTable**返回的提供程序表不能包含表示相关信息的其他行配置文件中的一个或多个服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="7a28e-116">Unlike the provider table returned through the [IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md) method, the provider table returned through **IMsgServiceAdmin::GetProviderTable** cannot include additional rows that represent information associated with one or more service providers in the profile.</span></span> 
  
<span data-ttu-id="7a28e-117">已删除或正在使用但已被标记为删除的提供程序不会包括在提供程序表中。</span><span class="sxs-lookup"><span data-stu-id="7a28e-117">Providers that have been deleted, or are in use but have been marked for deletion, are not included in the provider table.</span></span> <span data-ttu-id="7a28e-118">提供程序表是静态的, 这意味着, 配置文件中的后续添加或删除不会反映在表中。</span><span class="sxs-lookup"><span data-stu-id="7a28e-118">Provider tables are static, meaning that subsequent additions to or deletions from the profile are not reflected in the table.</span></span> 
  
<span data-ttu-id="7a28e-119">如果配置文件没有提供程序, 则**GetProviderTable**将返回一个包含零行和 S_OK 返回值的表。</span><span class="sxs-lookup"><span data-stu-id="7a28e-119">If the profile has no providers, **GetProviderTable** returns a table with zero rows and the S_OK return value.</span></span> 
  
<span data-ttu-id="7a28e-120">有关 provider 表中各列的完整列表, 请参阅[provider table](provider-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="7a28e-120">For a complete list of the columns in the provider table, see [Provider Table](provider-tables.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="7a28e-121">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7a28e-121">Notes to callers</span></span>

<span data-ttu-id="7a28e-122">若要在传输顺序中检索提供程序表的行, 请使用以下过程:</span><span class="sxs-lookup"><span data-stu-id="7a28e-122">To retrieve the rows of a provider table in transport order, use the following procedure:</span></span>
  
1. <span data-ttu-id="7a28e-123">调用[IMAPITable:: Restrict](imapitable-restrict.md)方法将与**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 属性相匹配的属性限制强加 MAPI_TRANSPORT_PROVIDER。</span><span class="sxs-lookup"><span data-stu-id="7a28e-123">Call the [IMAPITable::Restrict](imapitable-restrict.md) method to impose a property restriction that matches the **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) property with MAPI_TRANSPORT_PROVIDER.</span></span>
    
2. <span data-ttu-id="7a28e-124">调用[IMAPITable:: SortTable](imapitable-sorttable.md)方法按**PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) 列对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="7a28e-124">Call the [IMAPITable::SortTable](imapitable-sorttable.md) method to sort the table by the **PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) column.</span></span> 
    
3. <span data-ttu-id="7a28e-125">调用[IMAPITable:: QueryRows](imapitable-queryrows.md)方法以获取表中的行。</span><span class="sxs-lookup"><span data-stu-id="7a28e-125">Call the [IMAPITable::QueryRows](imapitable-queryrows.md) method to get the rows of the table.</span></span> 
    
<span data-ttu-id="7a28e-126">对这些调用的另一种方法是, 使用传入的所有相应数据结构对[HrQueryAllRows](hrqueryallrows.md)函数进行一次调用。</span><span class="sxs-lookup"><span data-stu-id="7a28e-126">An alternative to these calls is to make a single call to the [HrQueryAllRows](hrqueryallrows.md) function with all of the appropriate data structures passed in.</span></span> 
  
<span data-ttu-id="7a28e-127">如果在每个行中检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列, 则可以使用此**MAPIUID**结构数组在对[IMsgServiceAdmin:: MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)的调用中设置传输顺序。</span><span class="sxs-lookup"><span data-stu-id="7a28e-127">If you retrieve the **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) columns in each of the rows, you can use this array of **MAPIUID** structures to set the transport order in a call to [IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md).</span></span>
  
<span data-ttu-id="7a28e-128">在_ulFlags_参数中设置 MAPI_UNICODE 标志将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="7a28e-128">Setting the MAPI_UNICODE flag in the  _ulFlags_ parameter does the following:</span></span> 
  
- <span data-ttu-id="7a28e-129">将由[IMAPITable:: QueryColumns](imapitable-querycolumns.md)方法为 provider 表的初始活动列返回的数据的字符串类型设置为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="7a28e-129">Sets the string type to Unicode for data returned for the initial active columns of the provider table by the [IMAPITable::QueryColumns](imapitable-querycolumns.md) method.</span></span> <span data-ttu-id="7a28e-130">提供程序表的初始活动列是**QueryColumns**方法在包含该表调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法的提供程序之前返回的那些列。</span><span class="sxs-lookup"><span data-stu-id="7a28e-130">The initial active columns for a provider table are those columns the **QueryColumns** method returns before the provider that contains the table calls the [IMAPITable::SetColumns](imapitable-setcolumns.md) method.</span></span> 
    
- <span data-ttu-id="7a28e-131">将**QueryRows**的提供程序表的初始活动行返回的数据的字符串类型设置为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="7a28e-131">Sets the string type to Unicode for data returned for the initial active rows of the provider table by **QueryRows**.</span></span> <span data-ttu-id="7a28e-132">提供程序表的初始活动行是在包含该表调用**SetColumns**的提供程序之前**QueryRows**返回的那些行。</span><span class="sxs-lookup"><span data-stu-id="7a28e-132">The initial active rows for a provider table are those rows **QueryRows** returns before the provider that contains the table calls **SetColumns**.</span></span> 
    
- <span data-ttu-id="7a28e-133">控制[imapitable:: QuerySortOrder](imapitable-querysortorder.md)方法在包含 provider 表的客户端调用[imapitable:: SortTable](imapitable-sorttable.md)方法之前返回的排序顺序的属性类型。</span><span class="sxs-lookup"><span data-stu-id="7a28e-133">Controls the property types of the sort order returned by the [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) method before the client that contains the provider table calls the [IMAPITable::SortTable](imapitable-sorttable.md) method.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="7a28e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a28e-134">See also</span></span>



[<span data-ttu-id="7a28e-135">IMsgServiceAdmin::GetMsgServiceTable</span><span class="sxs-lookup"><span data-stu-id="7a28e-135">IMsgServiceAdmin::GetMsgServiceTable</span></span>](imsgserviceadmin-getmsgservicetable.md)
  
[<span data-ttu-id="7a28e-136">IMsgServiceAdmin::MsgServiceTransportOrder</span><span class="sxs-lookup"><span data-stu-id="7a28e-136">IMsgServiceAdmin::MsgServiceTransportOrder</span></span>](imsgserviceadmin-msgservicetransportorder.md)
  
[<span data-ttu-id="7a28e-137">IProviderAdmin::GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="7a28e-137">IProviderAdmin::GetProviderTable</span></span>](iprovideradmin-getprovidertable.md)
  
[<span data-ttu-id="7a28e-138">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7a28e-138">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)

