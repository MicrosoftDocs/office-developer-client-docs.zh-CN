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
# <a name="imsgserviceadmingetprovidertable"></a>IMsgServiceAdmin::GetProviderTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对提供程序表（配置文件中的服务提供程序列表）的访问权限。
  
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
  
> [out]指向指向提供程序表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回提供程序表。
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin：：GetProviderTable** 方法提供对 MAPI 提供程序表的访问，该表列出了配置文件中当前安装的所有通讯簿、邮件存储和传输提供程序。 
  
与通过 [IProviderAdmin：：GetProviderTable](iprovideradmin-getprovidertable.md) 方法返回的提供程序表不同，通过 **IMsgServiceAdmin：：GetProviderTable** 返回的提供程序表不能包含表示与配置文件中的一个或多个服务提供程序关联的信息的其他行。 
  
提供程序表中不包含已删除或已在使用中但标记为删除的提供程序。 提供程序表是静态的，这意味着对配置文件的后续添加或删除不会反映在表中。 
  
如果配置文件没有提供程序 **，GetProviderTable** 将返回包含零行的表，S_OK返回值。 
  
有关提供程序表中的列的完整列表，请参阅[Provider Table。](provider-tables.md) 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要按传输顺序检索提供程序表的行，请使用以下过程：
  
1. 调用[IMAPITable：：Restrict](imapitable-restrict.md)方法以施加与[PidTagResourceType PR_RESOURCE_TYPE (PidTagResourceType](pidtagresourcetype-canonical-property.md)) 属性与 MAPI_TRANSPORT_PROVIDER。 
    
2. 调用[IMAPITable：：SortTable](imapitable-sorttable.md)方法按[PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)列PR_PROVIDER_ORDINAL (表) 排序。  
    
3. 调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法来获取表的行。 
    
这些调用的替代方法是使用传入的所有适当数据结构对 [HrQueryAllRows](hrqueryallrows.md) 函数进行单个调用。 
  
如果检索每行中的 **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列，可以使用 **此 MAPIUID** 结构数组在 [调用 IMsgServiceAdmin：：MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)时设置传输顺序。
  
在  _ulFlags_ MAPI_UNICODE设置 MAPI_UNICODE 标记将执行以下操作： 
  
- 对于由 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 方法为提供程序表的初始活动列返回的数据，将字符串类型设置为 Unicode。 提供程序表的初始活动列是 **QueryColumns** 方法在包含该表的提供程序调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 方法之前返回的列。 
    
- 对于 QueryRows 为提供程序表的初始活动行返回的数据，将字符串类型设置为 **Unicode。** 提供程序表的初始活动行是 **QueryRows** 在包含该表的提供程序调用 **SetColumns** 之前返回的行。 
    
- 在包含提供程序表的客户端调用[IMAPITable：：SortTable](imapitable-sorttable.md)方法之前，控制[IMAPITable：：QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。 
    
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)
  
[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)
  
[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

