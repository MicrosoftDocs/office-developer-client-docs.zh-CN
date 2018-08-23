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
# <a name="imsgserviceadmingetprovidertable"></a>IMsgServiceAdmin::GetProviderTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供对提供程序表中，在配置文件中的服务提供商的列表的访问。
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]始终为 NULL。
    
 _lppTable_
  
> [输出]指向与提供程序表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回提供程序表中。
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin::GetProviderTable**方法提供了访问 MAPI 提供程序表中，列出所有通讯簿、 消息存储和传输提供程序当前安装的配置文件中的表。 
  
返回通过**IMsgServiceAdmin::GetProviderTable**的提供程序表不能与通过[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)方法返回的提供程序表，包含表示关联的信息的其他行与一个或多个服务提供程序配置文件中。 
  
提供程序已被删除，或正在使用但被标记为删除，不包括在提供程序表中。 提供程序表是静态的这意味着，后续的新增功能或从配置文件的删除操作不会反映在表。 
  
如果在配置文件不具有任何提供程序， **GetProviderTable**将返回零行和 S_OK 返回值与 table。 
  
有关提供程序表中的列的完整列表，请参阅[提供程序表中](provider-tables.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要检索顺序传输提供程序表中的行，请使用以下过程：
  
1. 调用[IMAPITable::Restrict](imapitable-restrict.md)方法来实施属性限制与 MAPI_TRANSPORT_PROVIDER 的**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 属性相匹配。
    
2. 调用[IMAPITable::SortTable](imapitable-sorttable.md)方法以按**PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) 列的表格进行排序。 
    
3. 调用[IMAPITable::QueryRows](imapitable-queryrows.md)方法以获取 table 的行。 
    
这些呼叫的替代方法是使[HrQueryAllRows](hrqueryallrows.md)函数所有适当的数据结构中传递单个呼叫。 
  
如果检索每个行中的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列时，您可以使用此数组**MAPIUID**结构[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)将调用设置传输顺序。
  
设置 MAPI_UNICODE 标志_ulFlags_参数中执行以下任务： 
  
- 设置为 Unicode [IMAPITable::QueryColumns](imapitable-querycolumns.md)方法返回的提供程序表中的初始活动列的数据的 string 类型。 提供程序表中的初始活动列是**QueryColumns**方法之前包含表呼叫[IMAPITable::SetColumns](imapitable-setcolumns.md)方法的提供程序返回这些列。 
    
- 设置为 Unicode **QueryRows**返回的提供程序表中的初始活动行的数据的 string 类型。 提供程序表中的初始活动行是之前的提供程序包含表呼叫**SetColumns** **QueryRows**返回这些行。 
    
- 控件的排序顺序之前包含提供程序表中的客户端调用[IMAPITable::SortTable](imapitable-sorttable.md)方法，由[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的属性类型。 
    
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)
  
[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)
  
[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

