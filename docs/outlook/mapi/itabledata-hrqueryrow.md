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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ef0dc212a6a6f761cd8dd0cae5312c548c02ae50
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583818"
---
# <a name="itabledatahrqueryrow"></a>ITableData::HrQueryRow

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检索表格行。
  
```cpp
HRESULT HrQueryRow(
  LPSPropValue lpSPropValue,
  LPSRow FAR * lppSRow,
  ULONG FAR * lpuliRow
);
```

## <a name="parameters"></a>参数

 _lpSPropValue_
  
> [in]指向描述要检索的行的索引列的属性值结构的指针。 属性值结构的**ulPropTag**成员应包含作为_ulPropTagIndexColumn_参数从访问[ITableData](itabledataiunknown.md)实现[CreateTable](createtable.md)函数调用的相同属性标记。 
    
 _lppSRow_
  
> [输出]指向到检索行的指针的指针。 
    
 _lpuliRow_
  
> [传入、 传出]在输入、 有效的指针或 NULL，表示不需要返回任何信息。 在输出中、 有效的指针指向行的行号，标识表中的行的位置的顺序编号。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索行。
    
MAPI_E_INVALID_PARAMETER 
  
> [SPropValue](spropvalue.md)结构不包含索引列属性的_lpSPropValue_点。 
    
## <a name="remarks"></a>注解

**ITableData::HrQueryRow**方法检索的所有行已索引列包含指向_lpSPropValue_属性结构中的索引列的值相匹配的属性。 **HrQueryRow**还返回行数，如果呼叫者请求其标识表中的行的位置。 
  
因为**HrQueryRow**不修改所指的_lpSPropValue_ **SPropValue**结构，呼叫者时**HrQueryRow**返回必须释放结构。 呼叫者还必须释放**SRow**结构包含检索的行。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropValue](spropvalue.md)
  
[SRow](srow.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

