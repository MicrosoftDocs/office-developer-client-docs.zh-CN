---
title: ITableDataHrEnumRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrEnumRow
api_type:
- COM
ms.assetid: b25d9f2b-9454-4983-98f7-6a051a3b8a04
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6c149a215a048b96408025e08df55972fa989f46
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776084"
---
# <a name="itabledatahrenumrow"></a>ITableData::HrEnumRow

  
  
**适用于**： Outlook 
  
检索根据其位置表中的行。 
  
```cpp
HRESULT HrEnumRow(
  ULONG ulRowNumber,
  LPSRow FAR * lppSRow
);
```

## <a name="parameters"></a>参数

 _ulRowNumber_
  
> [in]要为其返回属性的行数。 _UlRowNumber_参数中的值可以是 0，表示在表中，通过 n-1，这表明表中的最后一行的第一行中的任何值。 
    
 _lppSRow_
  
> [输出]指向介绍目标行[SRow](srow.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索行或_ulRowNumber_参数指定的行号行不存在。 
    
## <a name="remarks"></a>说明

**ITableData::HrEnumRow**方法检索行基于序列号。 这个数字表示插入的顺序 （0 表示的第一行和减 1 之间的行数指示最后一行）。 MAPI 维护表数据对象的生存期内行插入此时间顺序。 
  
如果号码中指定的_ulRowNumber_不对应于表中的行， **HrEnumRow** ，则返回 S_OK 和_lppSRow_参数设置为 NULL。 
  
MAPI 创建表格数据对象时使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数返回**SRow**结构分配内存。 呼叫者必须通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放此内存。 
  
若要检索行从表格中插入了它们的顺序，表数据对象的用户，请调用**HrEnumRow**方法。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SRow](srow.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

