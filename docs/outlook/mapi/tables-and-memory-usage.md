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
  
从表中检索数据时，一个重要的问题是内存使用量。 缺少可用内存会导致 [IMAPITable：：QueryRows](imapitable-queryrows.md) 和 [HrQueryAllRows](hrqueryallrows.md) 失败，返回的行数少于所需的行数。 确定用于检索表数据的方法或函数取决于表是否可以容纳在内存中，如果失败是可接受的，则确定表是否可以容纳在内存中。 
  
由于一次确定适合内存中的数据量并不总是一件容易的事情，MAPI 提供了一些基本准则，以便客户端应用程序或服务提供商遵循这些准则。 请记住，根据特定的表实现和基础数据的存储方法，始终存在例外。
  
以下指南可用于评估表内存使用情况：
  
- 可以容忍在兆字节范围内偶尔工作集内存使用量的客户端，并可以假定他们在将整个表读取到内存中时没有问题。 
    
- 限制会影响表的内存使用率。 具有大量行（如内容表）的严格限制表可以容纳在内存中，而不受限制的大型表通常不能容纳。 
    
- MAPI 拥有的几个表（如状态表、配置文件表、邮件服务表、提供程序表和邮件存储表）通常适合内存中。 这些表通常是小表。 但是，存在例外情况。 例如，基于服务器的配置文件提供程序可能会生成一个无法容纳的较大配置文件表。
    
若要检索表中适合内存的所有行，而没有任何问题，请调用 [HrQueryAllRows，](hrqueryallrows.md)将最大行数设置为 0。
  
若要从表中检索可能适合或不适合内存的所有行，从而生成错误，请调用指定最大行数的 **HrQueryAllRows。** 最大行数应设置为大于所需最小行数的行数。 如果客户端必须至少从 300 行表中访问 50 行，则最大行数应设置为至少 51 行。 
  
若要从表中检索不应放入内存的所有行，请调用具有相对较小行数的循环中的 [IMAPITable：：QueryRows，](imapitable-queryrows.md) 如以下代码示例所示： 
  
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

当此循环完成并且已处理表中的所有行且  _cRows_ 为零时，游标的位置通常位于表的底部。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

