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
# <a name="iprovideradmingetprovidertable"></a>IProviderAdmin::GetProviderTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对邮件服务提供程序表（邮件服务中的服务提供程序列表）的访问权限。
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制提供程序表列返回的字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未MAPI_UNICODE，则列采用 ANSI 格式。
    
 _lppTable_
  
> [out]指向指向提供程序表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回提供程序表。
    
## <a name="remarks"></a>备注

**IProviderAdmin：：GetProviderTable** 方法检索指向邮件服务的提供程序表（MAPI 维护的包含有关邮件服务中每个服务提供程序的信息的表）的指针。 
  
与 [IMsgServiceAdmin：：GetProviderTable](imsgserviceadmin-getprovidertable.md) 方法返回的提供程序表不同 **，IProviderAdmin：：GetProviderTable** 返回的提供程序表可能包含表示与邮件服务中的一个或多个服务提供程序关联的信息的其他行。 此额外信息将添加到具有 Mapisvc.inf 文件的"Sections"关键字的配置文件中。 当提供程序具有额外的配置文件节时，它将这些节的 **MAPIUID** 结构存储在 **PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) 属性中。 **PR_SERVICE_EXTRA_UIDS** 保存在邮件服务配置文件部分。 
  
提供程序表中不包含已删除或已在使用中但标记为删除的提供程序。 提供程序表是静态的，这意味着对邮件服务的后续添加或删除不会反映在表中。 
  
如果邮件服务没有提供程序，则 **IProviderAdmin：：GetProviderTable** 返回零行的表，S_OK返回值。 
  
在  _ulFlags_ 参数中设置 MAPI_UNICODE 标志会影响 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法返回的列的格式。 
  
此标志还按 [IMAPITable：：QuerySortOrder](imapitable-querysortorder.md) 方法返回的排序顺序控制属性类型。 
  
有关提供程序表中的列的完整列表，请参阅[Provider Table。](provider-tables.md) 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要按传输顺序检索提供程序表的行，请按[PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)列PR_PROVIDER_ORDINAL (表) 排序。  
  
若要仅检索那些表示服务提供商 (而不包括任何额外行) 的行，请限制检索其 PR_RESOURCE_TYPE ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列中值为 **PT_ERROR** 的行。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
| MsgServiceTableDlg.cpp  <br/> |CMsgServiceTableDlg：：OnDisplayItem  <br/> |MFCMAPI 使用 **IProviderAdmin：：GetProviderTable** 方法获取要呈现到新对话框中的提供程序表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

