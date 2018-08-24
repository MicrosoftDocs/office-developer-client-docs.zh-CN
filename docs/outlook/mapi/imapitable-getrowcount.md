---
title: IMAPITableGetRowCount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable.GetRowCount
api_type:
- COM
ms.assetid: 44a12c92-7462-4acf-9520-5d4c2d7f1d47
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 71178f1a531bd381387e0aa7fbacb02d4431a401
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584322"
---
# <a name="imapitablegetrowcount"></a>IMAPITable::GetRowCount

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回表中的总行数。 
  
```cpp
HRESULT GetRowCount(
ULONG ulFlags,
ULONG FAR * lpulCount
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 保留;必须为零。
    
 _lpulCount_
  
> [输出]指向的表中的行数。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的行计数。
    
MAPI_E_BUSY 
  
> 正在阻止从起始行计数检索操作是另一个操作。 应允许正在进行的操作完成或应停止。
    
MAPI_E_NO_SUPPORT 
  
> 表无法计算行的数。
    
MAPI_W_APPROX_COUNT 
  
> 调用成功，但因为完全行计数无法确定可能是由于内存限制返回近似行计数。 若要测试此警告，请使用**HR_FAILED**宏。 请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPITable::GetRowCount**方法检索表中的行的总数。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果无法确定表的确切的行数，返回 MAPI_W_APPROX_COUNT 和近似行计数中_lpulCount_参数的内容。 
  
## <a name="notes-to-callers"></a>给调用方的说明

使用**GetRowCount**以找出多少行表包含在调用[IMAPITable::QueryRows](imapitable-queryrows.md)方法来检索数据之前。 如果表中有小于 20 个行，则安全地呼叫**QueryPosition**检索整张表格。 如果表中有超过 20 个行，请考虑使多个调用**QueryPosition**和限制的每个呼叫中检索的行数。 
  
某些表格中不支持**GetRowCount** ，并返回 MAPI_E_NO_SUPPORT。 如果不支持**GetRowCount** ，另一个方法可能是呼叫[IMAPITable::QueryPosition](imapitable-queryposition.md)。 使用**QueryPosition**的结果，您可以确定当前行和最后一行之间的关系。 
  
**GetRowCount**返回 MAPI_E_BUSY，因为它是暂时无法检索行数时, 调用[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md)方法。 返回**WaitForCompletion**时, 重试**GetRowCount**调用。 另一种方法检测是否正在执行异步操作是调用[IMAPITable::GetStatus](imapitable-getstatus.md)方法，并检查_lpulTableState_参数的内容。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |CopyFolderContents  <br/> |MFCMAPI 使用**IMAPITable::GetRowCount**方法确定源表中多少行，因此可以分配内存要进行复制。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::GetStatus](imapitable-getstatus.md)
  
[IMAPITable::QueryPosition](imapitable-queryposition.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

