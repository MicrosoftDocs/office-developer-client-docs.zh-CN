---
title: IMAPISessionGetMsgStoresTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.GetMsgStoresTable
api_type:
- COM
ms.assetid: 77db2dff-4534-440f-a05c-635711cbc2c3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5fced633023ebf00efaf5b667dc7994eeb5de316
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338827"
---
# <a name="imapisessiongetmsgstorestable"></a>IMAPISession::GetMsgStoresTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对包含有关会话配置文件中的所有邮件存储区的信息的邮件存储表的访问权限。
  
```cpp
HRESULT GetMsgStoresTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时标志的位掩码, 用于确定作为字符字符串的列的格式。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串列的格式为 ANSI。
    
 _lppTable_
  
> 排除指向邮件存储表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 已设置 MAPI_UNICODE 标志, 且会话不支持 UNICODE。
    
## <a name="remarks"></a>注解

**IMAPISession:: GetMsgStoresTable**方法检索指向邮件存储表的指针, 它是由 MAPI 维护的表, 其中包含有关配置文件中每个打开的邮件存储区的信息。 
  
有关邮件存储表中的必填和可选的列的完整列表, 请参阅[message store Tables](message-store-tables.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

由于每次发生更改时 MAPI 都会在会话过程中更新邮件存储表, 因此请调用邮件存储表的**Advise**方法以注册, 以获得这些更改的通知。 可能的更改包括添加新的邮件存储、删除现有存储和更改为默认存储。 
  
在_ulFlags_参数中设置 MAPI_UNICODE 标志将影响从[IMAPITable:: QueryColumns](imapitable-querycolumns.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)方法返回的列的格式。 此标志还按[IMAPITable:: QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序控制属性类型。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg  <br/> |CMainDlg:: OnOpenMessageStoreTable  <br/> |MFCMAPI 使用**IMAPISession:: GetMsgStoresTable**方法获取邮件存储表, 以便它可以在 MFCMAPI 的主对话框中呈现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[邮件存储表](message-store-tables.md)

