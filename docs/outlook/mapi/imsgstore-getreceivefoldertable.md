---
title: IMsgStoreGetReceiveFolderTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.GetReceiveFolderTable
api_type:
- COM
ms.assetid: d115ab58-07d2-4b49-8e08-2881c2924102
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 303c2ef855d5cfc1d6614bda92b46c2da97717c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421352"
---
# <a name="imsgstoregetreceivefoldertable"></a>IMsgStore::GetReceiveFolderTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对接收文件夹表的访问权限，该表包含有关邮件存储的所有接收文件夹的信息。
  
```cpp
HRESULT GetReceiveFolderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable );
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制表访问的标志的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **GetReceiveFolderTable** 在表完全可供调用方使用之前成功返回。 如果表并非完全可用，则进行后续表调用可能会引发错误。 
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _lppTable_
  
> [out]指向接收文件夹表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回接收文件夹表。
    
## <a name="remarks"></a>备注

**IMsgStore：：GetReceiveFolderTable** 方法提供对表的访问权限，该表显示邮件存储的所有接收文件夹的属性设置。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

有关接收文件夹表中所需列的列表，请参阅 [接收文件夹表](receive-folder-tables.md)。 
  
实现接收文件夹表以支持在[PidTagRecordKey](pidtagrecordkey-canonical-property.md)属性PR_RECORD_KEY (设置) 限制。  这便于访问特定的接收文件夹。
  
## <a name="notes-to-callers"></a>给调用方的说明

在  _ulFlags_ 参数中设置 MAPI_UNICODE 标志会影响 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法返回的列的格式。 此标志还按 [IMAPITable：：QuerySortOrder](imapitable-querysortorder.md) 方法返回的排序顺序控制属性类型。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg：：OnDisplayReceiveFolderTable  <br/> |MFCMAPI 使用 **IMsgStore：：GetReceiveFolderTable** 方法获取要显示的接收文件夹表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

