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
ms.openlocfilehash: b13bf3bdd8392efc42ad189e48dffad8636f0708
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425601"
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
  
> [out]指向表中行数的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回行数。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作，以防止行计数检索操作启动。 应允许完成或停止进行中的操作。
    
MAPI_E_NO_SUPPORT 
  
> 表格无法计算行数。
    
MAPI_W_APPROX_COUNT 
  
> 调用成功，但返回了近似的行计数，因为可能由于内存限制无法确定确切的行计数。 若要测试此警告，请使用 **HR_FAILED** 宏。 请参阅 [使用宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPITable：：GetRowCount** 方法检索表中的总行数。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果无法确定表的确切行数，则返回 MAPI_W_APPROX_COUNT  _lpulCount_ 参数的内容中的近似行数。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在调用 [IMAPITable：：QueryRows](imapitable-queryrows.md)方法以检索数据之前，使用 **GetRowCount** 可了解表包含的行数。 如果表中少于 20 行，可以安全地调用 **QueryPosition** 来检索整个表。 如果表中超过 20 行，请考虑多次调用 **QueryPosition** 并限制每次调用中检索到的行数。 
  
某些表不支持 **GetRowCount** 并返回MAPI_E_NO_SUPPORT。 如果 **不支持 GetRowCount，** 另一种可能调用 [IMAPITable：：QueryPosition](imapitable-queryposition.md)。 使用 **QueryPosition 中的结果**，可以确定当前行和最后一行之间的关系。 
  
当 **GetRowCount** 由于MAPI_E_BUSY检索行数而返回值时，请调用 [IMAPITable：：WaitForCompletion](imapitable-waitforcompletion.md) 方法。 当 **WaitForCompletion** 返回时，重试对 **GetRowCount 的调用**。 检测异步操作是否正在进行的另一个方法是调用 [IMAPITable：：GetStatus](imapitable-getstatus.md) 方法并检查  _lpulTableState_ 参数的内容。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |CopyFolderContents  <br/> |MFCMAPI 使用 **IMAPITable：：GetRowCount** 方法确定源表中有多少行，以便分配内存以执行复制。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable::GetStatus](imapitable-getstatus.md)
  
[IMAPITable::QueryPosition](imapitable-queryposition.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::WaitForCompletion](imapitable-waitforcompletion.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

