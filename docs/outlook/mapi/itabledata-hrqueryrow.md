---
title: ITableDataHrQueryRow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData.HrQueryRow
api_type:
- COM
ms.assetid: 66ce8f36-2b2b-4a8e-b9b2-43782d8357a1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: da41fadc9a71a410dd115e28ce2cf9c81442b104
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348641"
---
# <a name="itabledatahrqueryrow"></a>ITableData::HrQueryRow

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索表行。
  
```cpp
HRESULT HrQueryRow(
  LPSPropValue lpSPropValue,
  LPSRow FAR * lppSRow,
  ULONG FAR * lpuliRow
);
```

## <a name="parameters"></a>参数

 _lpSPropValue_
  
> 实时一个指向属性值结构的指针, 该结构描述要检索的行的索引列。 属性值结构的**ulPropTag**成员应包含与_ulPropTagIndexColumn_参数相同的属性标记, 从调用[CreateTable](createtable.md)函数, 后者访问[ITableData](itabledataiunknown.md)实现。 
    
 _lppSRow_
  
> 排除指向检索到的行的指针的指针。 
    
 _lpuliRow_
  
> [in, out]在输入时, 是有效的指针或 NULL, 它指示无需返回任何信息。 在输出中, 指向行的行号的有效指针, 用于标识行在表中的位置的顺序编号。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索该行。
    
MAPI_E_INVALID_PARAMETER 
  
> _lpSPropValue_指向的[SPropValue](spropvalue.md)结构不包含 index 列属性。 
    
## <a name="remarks"></a>注解

**ITableData:: HrQueryRow**方法检索索引列与由_lpSPropValue_指向的属性结构中包含的索引列相匹配的行的所有属性。 如果调用方请求行号, 则**HrQueryRow**也会返回行号, 用于标识行在表中的位置。 
  
由于**HrQueryRow**不会修改_lpSPropValue_指向的**SPropValue**结构, 因此在**HrQueryRow**返回时, 调用方必须释放结构。 调用方还必须释放包含检索到的行的**SRow**结构。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropValue](spropvalue.md)
  
[SRow](srow.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

