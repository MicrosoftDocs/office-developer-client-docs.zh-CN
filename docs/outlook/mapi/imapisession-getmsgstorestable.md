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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428135"
---
# <a name="imapisessiongetmsgstorestable"></a>IMAPISession::GetMsgStoresTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对包含有关会话配置文件中所有邮件存储的信息的邮件存储表的访问。
  
```cpp
HRESULT GetMsgStoresTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]标志的位掩码，用于确定作为字符串的列的格式。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 字符串列采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串列采用 ANSI 格式。
    
 _lppTable_
  
> [out]指向指向消息存储表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 已MAPI_UNICODE该标记，并且会话不支持 Unicode。
    
## <a name="remarks"></a>备注

**IMAPISession：：GetMsgStoresTable** 方法检索指向消息存储表的指针，该表由 MAPI 维护，其中包含有关配置文件中每个打开的邮件存储的信息。 
  
有关邮件存储表中必需列和可选列的完整列表，请参阅邮件 [存储表](message-store-tables.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

由于 MAPI 将在会话期间随时更新邮件存储表，因此请调用邮件存储表的 **Advise** 方法以注册以通知这些更改。 可能的更改包括添加新邮件存储、删除现有存储以及更改默认存储。 
  
在  _ulFlags_ 参数中设置 MAPI_UNICODE 标志会影响 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法返回的列的格式。 此标志还按 [IMAPITable：：QuerySortOrder](imapitable-querysortorder.md) 方法返回的排序顺序控制属性类型。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg：：OnOpenMessageStoreTable  <br/> |MFCMAPI 使用 **IMAPISession：：GetMsgStoresTable** 方法获取邮件存储表，以便它可以呈现在 MFCMAPI 的主对话框中。  <br/> |
   
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

