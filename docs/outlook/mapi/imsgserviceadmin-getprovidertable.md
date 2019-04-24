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
# <a name="imsgserviceadmingetprovidertable"></a>IMsgServiceAdmin::GetProviderTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对提供程序表的访问权限 (配置文件中的服务提供程序的列表)。
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时始终为 NULL。
    
 _lppTable_
  
> 排除指向提供程序表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回 provider 表。
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin:: GetProviderTable**方法提供对 MAPI 提供程序表的访问, 该表列出了当前安装在配置文件中的所有通讯簿、邮件存储和传输提供程序。 
  
与通过[IProviderAdmin:: GetProviderTable](iprovideradmin-getprovidertable.md)方法返回的 provider 表不同, 通过**IMsgServiceAdmin:: GetProviderTable**返回的提供程序表不能包含表示相关信息的其他行配置文件中的一个或多个服务提供程序。 
  
已删除或正在使用但已被标记为删除的提供程序不会包括在提供程序表中。 提供程序表是静态的, 这意味着, 配置文件中的后续添加或删除不会反映在表中。 
  
如果配置文件没有提供程序, 则**GetProviderTable**将返回一个包含零行和 S_OK 返回值的表。 
  
有关 provider 表中各列的完整列表, 请参阅[provider table](provider-tables.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要在传输顺序中检索提供程序表的行, 请使用以下过程:
  
1. 调用[IMAPITable:: Restrict](imapitable-restrict.md)方法将与**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 属性相匹配的属性限制强加 MAPI_TRANSPORT_PROVIDER。
    
2. 调用[IMAPITable:: SortTable](imapitable-sorttable.md)方法按**PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) 列对表进行排序。 
    
3. 调用[IMAPITable:: QueryRows](imapitable-queryrows.md)方法以获取表中的行。 
    
对这些调用的另一种方法是, 使用传入的所有相应数据结构对[HrQueryAllRows](hrqueryallrows.md)函数进行一次调用。 
  
如果在每个行中检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列, 则可以使用此**MAPIUID**结构数组在对[IMsgServiceAdmin:: MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)的调用中设置传输顺序。
  
在_ulFlags_参数中设置 MAPI_UNICODE 标志将执行以下操作: 
  
- 将由[IMAPITable:: QueryColumns](imapitable-querycolumns.md)方法为 provider 表的初始活动列返回的数据的字符串类型设置为 Unicode。 提供程序表的初始活动列是**QueryColumns**方法在包含该表调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法的提供程序之前返回的那些列。 
    
- 将**QueryRows**的提供程序表的初始活动行返回的数据的字符串类型设置为 Unicode。 提供程序表的初始活动行是在包含该表调用**SetColumns**的提供程序之前**QueryRows**返回的那些行。 
    
- 控制[imapitable:: QuerySortOrder](imapitable-querysortorder.md)方法在包含 provider 表的客户端调用[imapitable:: SortTable](imapitable-sorttable.md)方法之前返回的排序顺序的属性类型。 
    
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)
  
[IMsgServiceAdmin::MsgServiceTransportOrder](imsgserviceadmin-msgservicetransportorder.md)
  
[IProviderAdmin::GetProviderTable](iprovideradmin-getprovidertable.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)

