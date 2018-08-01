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
ms.openlocfilehash: ba540b0fd3371b3e12be9eeeb102a9bd9d7e8d22
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775545"
---
# <a name="imapisessiongetmsgstorestable"></a>IMAPISession::GetMsgStoresTable

  
  
**适用于**： Outlook 
  
提供对消息存储表包含有关会话配置文件中的所有邮件存储的信息的访问。
  
```cpp
HRESULT GetMsgStoresTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，用于确定字符的字符串的列的格式。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 字符串列的 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，字符串列的 ANSI 格式。
    
 _lppTable_
  
> [输出]指向与消息存储表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置该 MAPI_UNICODE 标记和会话不支持 Unicode。
    
## <a name="remarks"></a>说明

**IMAPISession::GetMsgStoresTable**方法检索指向消息存储表的指针，由 MAPI 维护表包含有关配置文件中每个打开的邮件存储的信息。 
  
将表存储有关必需的和可选消息中的列的完整列表，请参阅[邮件存储表](message-store-tables.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

由于 MAPI 发生更改时在会话过程中更新消息存储表，调用消息存储表进行注册，以这些更改的通知的**Advise**方法。 可能发生的更改包括的新消息存储库添加、 删除现有的存储，并更改为默认存储。 
  
_UlFlags_参数中设置 MAPI_UNICODE 标志会影响从[IMAPITable::QueryColumns](imapitable-querycolumns.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的列的格式。 此标志还将控制[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnOpenMessageStoreTable  <br/> |MFCMAPI 使用**IMAPISession::GetMsgStoresTable**方法获取消息存储表，以使其可以在主要对话框的 MFCMAPI 呈现。  <br/> |
   
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
  
[邮件存储区表](message-store-tables.md)

