---
title: 表和内存使用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7ac11e60-6b2c-4241-96e2-20219f84d949
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: afd69f5a3fff69f670d6be78ba4957307cdb6995
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436858"
---
# <a name="tables-and-memory-usage"></a>表和内存使用

**适用于**：Outlook 2013 | Outlook 2016 
  
通过从表检索数据而连接的一个重要问题是内存使用率。 缺少可用内存会导致[IMAPITable:: QueryRows](imapitable-queryrows.md)和[HrQueryAllRows](hrqueryallrows.md)失败, 返回的行数小于所需的行数。 确定用于检索表数据的方法或函数取决于表是否可以在内存中使用, 如果故障是可接受的, 则是如此。 
  
由于很难确定一次内存中适合的数据量, 因此 MAPI 提供了有关要遵循的客户端应用程序或服务提供商的一些基本准则。 请注意, 始终有一些异常, 这取决于特定的表实现以及基础数据的存储方式。
  
以下准则可用于评估表内存使用率:
  
- 可以容忍 mb 范围内的偶尔工作集内存使用率的客户端, 并可假定它们在将整个表读取到内存中不会出现问题。 
    
- 限制会对表的内存使用产生影响。 具有大量行 (如内容表) 的严格受限制的表可能会在内存中显示, 而不受限制的大表通常不能装入。 
    
- MAPI (如状态、配置文件、邮件服务、提供程序和邮件存储表) 所拥有的几个表通常会放入内存中。 这些通常是小型表格。 不过, 也有一些例外情况。 例如, 基于服务器的配置文件提供程序可能会生成一个较大的配置文件表, 该表将无法合适。
    
若要检索表中的所有行, 这些行将适合不出现任何问题的内存, 请调用[HrQueryAllRows](hrqueryallrows.md), 将最大行数设置为零。
  
若要检索表中可能有也可能不符合内存的所有行, 请生成错误, 请调用**HrQueryAllRows**指定最大行数。 最大行数应设置为大于所需的最小行数的数字。 如果客户端必须从300行表访问至少50行, 则最多应将最大行数至少设置为51。 
  
若要检索表中不符合预期内存的所有行, 请调用[IMAPITable:: QueryRows](imapitable-queryrows.md)在相对较小的行计数的循环中, 如以下代码示例所示: 
  
```cpp
HRESULT     hr;
LPSRowSet   pRows = NULL;
LONG        irow;
LONG            cAsk = 50;                  // adjust this value
while ((hr = pTable->QueryRows(cAsk, 0, &pRows)) == hrSuccess
        && pRows->cRows != 0)
{
    for (irow = 0; irow < prows->cRows; ++irow)
    {
        // process the row...
    }
    FreeProws(pRows);
    pRows = NULL;
}
if (hr)
{
    // handle the error...
}
 
```

当此循环完成且表中的所有行均已处理且_cRows_为0时, 光标的位置通常位于表的底部。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

