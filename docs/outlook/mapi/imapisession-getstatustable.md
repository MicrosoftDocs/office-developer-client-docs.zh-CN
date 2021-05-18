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
ms.openlocfilehash: 17e936093536f548d16021523d9434f09777c6d9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407135"
---
# <a name="imapisessiongetstatustable"></a>IMAPISession::GetStatusTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供对状态表（包含有关会话中所有 MAPI 资源的信息的表）的访问权限。
  
```cpp
HRESULT GetStatusTable(
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
  
> [out]指向指向状态表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回表。
    
## <a name="remarks"></a>备注

**IMAPISession：：GetStatusTable** 方法提供对包含有关会话中所有 MAPI 资源的信息的状态表的访问。 表中有一行有关 MAPI 子系统的信息，一行用于 MAPI 后台处理程序，一行用于集成通讯簿，一行用于配置文件中每个服务提供商。 
  
有关状态表中必需列和可选列的完整列表，请参阅 [状态表](status-tables.md)。 
  
在  _ulFlags_ 参数中设置 MAPI_UNICODE 标志会影响 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 和 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法返回的列的格式。 此标志还按 [IMAPITable：：QuerySortOrder](imapitable-querysortorder.md) 方法返回的排序顺序控制属性类型。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg：：OnStatusTable  <br/> |MFCMAPI 使用 **IMAPISession：：GetStatusTable** 方法获取要呈现的状态表。  <br/> |
   
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

