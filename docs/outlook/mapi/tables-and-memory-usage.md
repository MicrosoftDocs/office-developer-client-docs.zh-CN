---
title: 表和内存使用情况
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7ac11e60-6b2c-4241-96e2-20219f84d949
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 390cec0cc59f189f83af2c5339512d82e125771e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778964"
---
# <a name="tables-and-memory-usage"></a>表和内存使用情况

**适用于**： Outlook 
  
与表中检索数据连接的重要问题是内存使用率。 可用内存不足可能导致[IMAPITable::QueryRows](imapitable-queryrows.md)和[HrQueryAllRows](hrqueryallrows.md)失败，返回所需的行数小于。 决定哪些方法或函数用于检索表数据取决于是否可以预期表以适合在内存中，并不能转换，如果是可接受的失败。 
  
因为并非始终容易地确定将一次适合内存的数据量，MAPI 提供了客户端应用程序或服务提供商，若要遵循一些基本的原则。 请记住都始终例外，基于特定的表实现和如何存储基础数据。
  
以下准则可用于评估表内存使用情况：
  
- 可以容忍偶尔兆字节范围中的工作集内存使用率，并可以假定它们的客户端会读取到内存整个表没有问题。 
    
- 限制会影响的内存表的使用情况。 预计严格限制的表与广泛的行数，如内容目录，而不受限制的大型表通常不能适合内存。 
    
- 有几个 MAPI 拥有如状态、 配置文件、 消息服务、 提供商和邮件存储表的表通常适合内存中。 这些是通常小表。 但是，有一些例外。 例如，基于服务器的配置文件提供程序可能会生成不能以适应较大的配置文件表。
    
若要从将适合与没有问题的内存表中检索的所有行，调用[HrQueryAllRows](hrqueryallrows.md)，将最大行数设置为零。
  
若要检索的所有行从一个表，可能是也可能不适合内存，生成一个错误，调用**HrQueryAllRows**指定最大行数。 最大行数应设置为数大于的最小所需的行数。 如果客户端必须访问 300 行表中至少 50 行，最大行数应设置为至少 51。 
  
若要检索的表中不应适合内存中的所有行，调用[IMAPITable::QueryRows](imapitable-queryrows.md)循环与相对较小的行数，如下面的代码示例所示： 
  
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

此循环完成和已处理表中的所有行，并且_cRows_为零，光标位置通常会在表的底部。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

