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
ms.openlocfilehash: 3ddfcdd95f0423ba92c37c434f18078eadf90d82
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594017"
---
# <a name="iprovideradmingetprovidertable"></a>IProviderAdmin::GetProviderTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供对邮件服务提供程序表中，消息服务的服务提供商的列表的访问。
  
```cpp
HRESULT GetProviderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志的控制提供程序表的列中返回的字符串的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 字符串列的 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，列的 ANSI 格式。
    
 _lppTable_
  
> [输出]指向与提供程序表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回提供程序表中。
    
## <a name="remarks"></a>注解

**IProviderAdmin::GetProviderTable**方法检索与邮件服务提供程序表，MAPI 维护，包含有关每个邮件服务中的服务提供商信息表的指针。 
  
返回**IProviderAdmin::GetProviderTable**的提供程序表可能与不同[IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md)方法返回的提供程序表，包括表示与一个或多个关联的信息的其他行邮件服务服务提供商。 此额外信息添加到使用 Mapisvc.inf 文件的"部分"关键字的配置文件。 当提供程序具有额外的配置文件节时，它**PR_SERVICE_EXTRA_UIDS** ([PidTagServiceExtraUids](pidtagserviceextrauids-canonical-property.md)) 属性中存储以下各节**MAPIUID**结构。 **PR_SERVICE_EXTRA_UIDS**保存在邮件服务配置文件部分。 
  
提供程序已被删除，或正在使用但被标记为删除，不包括在提供程序表中。 提供程序表是静态的这意味着，后续的新增功能或删除邮件服务的内容不会反映在表。 
  
如果邮件服务没有提供程序，请**IProviderAdmin::GetProviderTable**将返回零行和 S_OK 返回值与 table。 
  
_UlFlags_参数中设置 MAPI_UNICODE 标志会影响从[IMAPITable::QueryColumns](imapitable-querycolumns.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的列的格式。 
  
此标志还将控制[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。 
  
有关提供程序表中的列的完整列表，请参阅[提供程序表中](provider-tables.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要检索顺序传输提供程序表中的行，请按**PR_PROVIDER_ORDINAL** ([PidTagProviderOrdinal](pidtagproviderordinal-canonical-property.md)) 列进行排序的表。 
  
若要检索表示服务提供商 （不包括任何额外的行） 的行，限制您检索到有的 PT_ERROR 其**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列中的值的行。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
| MsgServiceTableDlg.cpp  <br/> |CMsgServiceTableDlg::OnDisplayItem  <br/> |MFCMAPI 使用**IProviderAdmin::GetProviderTable**方法来获取提供程序，呈现在新的对话框中的表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md)
  
[IProviderAdmin : IUnknown](iprovideradminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

