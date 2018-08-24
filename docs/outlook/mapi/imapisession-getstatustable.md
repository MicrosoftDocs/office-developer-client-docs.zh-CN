---
title: IMAPISessionGetStatusTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.GetStatusTable
api_type:
- COM
ms.assetid: 53428f8d-4838-46d1-a0ab-cafb194f4cc3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 48a69fa49735014dcbfffad0673f1d4da62452e7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594829"
---
# <a name="imapisessiongetstatustable"></a>IMAPISession::GetStatusTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对状态表中，一个表，包含会话中所有 MAPI 资源的信息的访问。
  
```cpp
HRESULT GetStatusTable(
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
  
> [输出]指向状态表格的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回表。
    
## <a name="remarks"></a>注解

**IMAPISession::GetStatusTable**方法提供了访问状态表包含有关的所有 MAPI 资源会话中的信息。 没有有关 MAPI 子系统表中的一个行、 一行，MAPI 后台处理程序、 一行，集成的通讯簿中，和配置文件中每个服务提供商的一行。 
  
必需的和可选状态表中的列的完整列表，请参阅[状态表](status-tables.md)。 
  
_UlFlags_参数中设置 MAPI_UNICODE 标志会影响从[IMAPITable::QueryColumns](imapitable-querycolumns.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)方法返回的列的格式。 此标志还将控制[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)方法返回的排序顺序的属性类型。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnStatusTable  <br/> |MFCMAPI 使用**IMAPISession::GetStatusTable**方法获取 status 表来呈现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPITable : IUnknown](imapitableiunknown.md)
  
[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMAPITable::SortTable](imapitable-sorttable.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[状态表](status-tables.md)

