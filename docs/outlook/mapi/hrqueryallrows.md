---
title: HrQueryAllRows
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrQueryAllRows
api_type:
- HeaderDef
ms.assetid: b08fadcf-cdf3-48b7-9489-d7f745266482
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0f09304f21180d9ebc2a1e1dcc54ebadd3622804
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422892"
---
# <a name="hrqueryallrows"></a>HrQueryAllRows

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索表的所有行。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
HRESULT HrQueryAllRows(
  LPMAPITABLE ptable,
  LPSPropTagArray ptaga,
  LPSRestriction pres,
  LPSSortOrderSet psos,
  LONG crowsMax,
  LPSRowSet FAR * pprows
);
```

## <a name="parameters"></a>参数

 _ptable_
  
> [in]指向从中检索行的 MAPI 表的指针。 
    
 _ptaga_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，该结构包含指示表列的属性标记数组。 这些标记用于选择要检索的特定列。 如果  _ptaga_ 参数为 **NULL，HrQueryAllRows** 将检索在  _ptable_ 参数中传递的当前表视图的整个列集。 
    
 _pres_
  
> [in]指向包含检索限制的 [SRestriction](srestriction.md) 结构的指针。 如果  _pres_ 参数为 NULL， **则 HrQueryAllRows** 将没有任何限制。 
    
 _psos_
  
> [in]指向标识要检索的列的排序顺序的 [SSortOrderSet](ssortorderset.md) 结构的指针。 如果  _psos_ 参数为 NULL，则使用表的默认排序顺序。 
    
 _一些_
  
> [in]要检索的最大行数。 如果  _为 0，则对_ 检索到的行数没有限制。 
    
 _pprows_
  
> [out]指向返回的 [SRowSet](srowset.md) 结构的指针的指针，该结构包含指向检索到的表行的指针数组。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用检索表的预期行。 
    
MAPI_E_TABLE_TOO_BIG 
  
> 表格中的行数大于为  _用户传递的 rowssMax_ 参数所传递的行数。 
    
## <a name="remarks"></a>备注

客户端应用程序或服务提供商无法控制 **HrQueryAllRows** 尝试检索的行数，但通过阻止  _pres_ 参数指向的限制。 _一个系统_ 参数不限制检索到一定数量的表行，而是定义可用于保留所有检索到的行的最大内存量。 防止大量内存溢出的唯一保护是 stopgap 功能，它通过  _设置 overflowsMax 提供_。 错误返回MAPI_E_TABLE_TOO_BIG意味着表包含太多行，无法一次在内存中全部存储。 
  
通常较小的表（如邮件存储表或提供程序表）通常可以使用 **HrQueryAllRows** 安全检索。 应该使用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法在子节中遍历风险非常大的表，如内容表甚至收件人表。 
  
如果调用 **HrQueryAllRows** 时未定义任何表属性，则返回的属性类型为 PT_NULL，属性标识符为 PROP_ID_NULL 
  

