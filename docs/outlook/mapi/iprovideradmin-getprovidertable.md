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
# <a name="iprovideradmingetprovidertable"></a>IProviderAdmin::GetProviderTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对邮件服务的提供程序表的访问权限 (邮件服务中的服务提供程序的列表)。
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 用于控制提供程序表的列中返回的字符串的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则列采用 ANSI 格式。
    
 _lppTable_
  
> 排除指向提供程序表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回 provider 表。
    
## <a name="remarks"></a>注解

**IProviderAdmin:: GetProviderTable**方法检索指向邮件服务的提供程序表的指针, 该表是 MAPI 维护的, 其中包含有关邮件服务中的每个服务提供程序的信息。 
  
与[IMsgServiceAdmin:: GetProviderTable](imsgserviceadmin-getprovidertable.md)方法返回的 provider 表不同, **IProviderAdmin:: GetProviderTable**返回的 provider 表可能包含其他行, 这些行表示与一个或多个邮件服务中的服务提供程序。 此额外信息将添加到配置文件中, 其中包含 mapisvc.inf 文件的 "节" 关键字。 当提供程序有额外的配置文件节时, 它会在**PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) 属性中存储这些节的**MAPIUID**结构。 **PR_SERVICE_EXTRA_UIDS**保存在 "邮件服务配置文件" 部分。 
  
已删除或正在使用但已被标记为删除的提供程序不会包括在提供程序表中。 提供程序表是静态的, 这意味着在邮件服务中进行的后续添加或删除不会反映在表中。 
  
如果消息服务没有提供程序, 则**IProviderAdmin:: GetProviderTable**将返回一个包含零行和 S_OK 返回值的表。 
  
在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)方法返回的列的格式。 
  
此标志还按[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序控制属性类型。 
  
有关 provider 表中各列的完整列表, 请参阅[provider table](provider-tables.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要在传输顺序中检索提供程序表的行, 请按**PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) 列对表进行排序。 
  
若要仅检索表示服务提供程序的那些行 (不包含任何额外行), 请将检索限制为其**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列中具有 PT_ERROR 值的行。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
| MsgServiceTableDlg  <br/> |CMsgServiceTableDlg:: OnDisplayItem  <br/> |MFCMAPI 使用**IProviderAdmin:: GetProviderTable**方法获取要在新对话框中呈现的提供程序表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

