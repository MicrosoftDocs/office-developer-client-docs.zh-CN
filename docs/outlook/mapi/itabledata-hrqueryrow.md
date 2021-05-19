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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434765"
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
  
> [in]指向描述要检索的行的索引列的属性值结构的指针。 属性值 **结构的 ulPropTag** 成员应包含与调用 [CreateTable](createtable.md)函数时 _ulPropTagIndexColumn_ 参数相同的属性标记，该函数访问 [ITableData](itabledataiunknown.md)实现。 
    
 _lppSRow_
  
> [out]指向检索到的行的指针的指针。 
    
 _lp一Row_
  
> [in， out]输入时，表示无需返回任何信息的有效指针或 NULL。 在 output 上，指向行的行号的有效指针，一个标识行在表中位置的顺序编号。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索行。
    
MAPI_E_INVALID_PARAMETER 
  
> _lpSPropValue_ 指向的 [SPropValue](spropvalue.md)结构不包含索引列属性。 
    
## <a name="remarks"></a>备注

**ITableData：：HrQueryRow** 方法检索具有与 _lpSPropValue_ 指向的属性结构中包含的索引列的值匹配的索引列的行的所有属性。 **HrQueryRow** 还会返回行号（如果调用方请求它）来标识行在表中的位置。 
  
因为 **HrQueryRow** 不会修改 _lpSPropValue_ 指向的 **SPropValue** 结构，所以当 **HrQueryRow** 返回时，调用方必须释放该结构。 调用方还必须释放包含检索到的行的 **SRow** 结构。 
  
## <a name="see-also"></a>另请参阅



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[SPropValue](spropvalue.md)
  
[SRow](srow.md)
  
[ITableData : IUnknown](itabledataiunknown.md)

