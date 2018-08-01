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
ms.openlocfilehash: 5c62e5919c6e605aa4b60f48072996ed1fd4c355
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775186"
---
# <a name="hrqueryallrows"></a>HrQueryAllRows

  
  
**适用于**： Outlook 
  
检索表中的所有行。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向从中检索行的 MAPI 表。 
    
 _ptaga_
  
> [in]指向包含属性的数组[SPropTagArray](sproptagarray.md)结构标记指示表格列。 这些标记用于选择要检索的特定列。 如果_ptaga_参数为 NULL，则**HrQueryAllRows**检索当前表视图_ptable_参数中传递的整个列集。 
    
 _展示_
  
> [in]指向包含检索限制[SRestriction](srestriction.md)结构。 如果_展示_参数为 NULL，则**HrQueryAllRows**使没有限制。 
    
 _pso_
  
> [in]标识要检索列的排序顺序[SSortOrderSet](ssortorderset.md)结构的指针。 如果_pso_参数为 NULL，则使用表的默认排序次序。 
    
 _crowsMax_
  
> [in]要检索的行的最大数量。 如果_crowsMax_参数的值为零，检索的行数不限制设置。 
    
 _pprows_
  
> [输出]为包含指向检索到的表格行的指针数组返回[SRowSet](srowset.md)结构指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫检索预期的表格行。 
    
MAPI_E_TABLE_TOO_BIG 
  
> 值大于数为_crowsMax_参数传递的表中的行数。 
    
## <a name="remarks"></a>说明

客户端应用程序或服务提供商具有不能控制**HrQueryAllRows**尝试检索，以外通过提出限制_展示_参数指向的行数。 _CrowsMax_参数不会限制为特定的表格行数检索但而定义最大可用来保存所有检索的行的内存量。 仅针对大规模内存溢出保护是通过设置_crowsMax_提供应急功能。 错误返回 MAPI_E_TABLE_TOO_BIG 意味着表包含太多行一次性彻底保留在内存中。 
  
表的通常较小，如消息存储表或提供程序表中，通常可以安全地检索与**HrQueryAllRows**。 应在使用[IMAPITable::QueryRows](imapitable-queryrows.md)方法的小节遍历危险的太大，内容或甚至收件人目录，如表。 
  
如果调用**HrQueryAllRows**时未定义任何表属性，也会返回与属性类型 PT_NULL 属性标识符 PROP_ID_NULL 
  

