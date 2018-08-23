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
ms.openlocfilehash: 681fd68fc068633912df1cb7f060b8c4111b5de8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566535"
---
# <a name="imsgstoregetreceivefoldertable"></a>IMsgStore::GetReceiveFolderTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供对接收文件夹表中，一个表，包括有关的所有接收的消息存储库文件夹的信息的访问。
  
```cpp
HRESULT GetReceiveFolderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable );
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]Flags 控件表访问的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许**GetReceiveFolderTable**返回成功，原因可能是完全可用于将呼叫者表之前。 如果表不完全支持，进行后续表呼叫会引发错误。 
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _lppTable_
  
> [输出]指向接收文件夹表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回接收文件夹表。
    
## <a name="remarks"></a>注解

**IMsgStore::GetReceiveFolderTable**方法可访问此表格显示所有的消息存储的属性设置接收文件夹。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

接收文件夹表中所需的列的列表，请参阅[接收文件夹表](receive-folder-tables.md)。 
  
实现您接收文件夹表，以支持设置属性限制**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 属性。 此启用对特定的轻松访问接收文件夹。
  
## <a name="notes-to-callers"></a>给调用方的说明

_UlFlags_参数中设置 MAPI_UNICODE 标志会影响从[IMAPITable::QueryColumns](imapitable-querycolumns.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的列的格式。 此标志还将控制[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg::OnDisplayReceiveFolderTable  <br/> |MFCMAPI 使用**IMsgStore::GetReceiveFolderTable**方法来获取要显示的接收文件夹表。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

