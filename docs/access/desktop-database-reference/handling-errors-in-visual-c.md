---
title: 在 Visual c + + 中处理错误
TOCTitle: Handling errors in Visual C++
ms:assetid: 75e15699-0c84-1dca-654e-f9ac465c2a30
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249483(v=office.15)
ms:contentKeyID: 48545684
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 99f8a0f8c7b79769fba62b38ef5517781aea4600
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25945605"
---
# <a name="handling-errors-in-visual-c"></a>在 Visual c + + 中处理错误


**适用于**： Access 2013、 Office 2013

在 COM，大多数操作返回 HRESULT 返回代码，指示函数是否已成功完成。 \#导入指令生成周围每个"原始"方法或属性的包装代码，并检查返回的 HRESULT。 如果 HRESULT 指示故障，包装代码通过调用引发 COM 错误\_com\_问题\_errorex() hresult 返回作为参数的代码。 可以在**try-catch**块中捕获 COM error 对象。 (为效率的起见，捕获对\_com\_error 对象。)

请记住，这些是 ADO 错误：它们是由于 ADO 操作失败而导致的。基础提供程序返回的错误将作为 **Connection** 对象的 **Errors** 集合中的 **Error** 对象出现。

\#导入指令仅创建的方法和属性在 ADO.dll 中声明的错误处理例程。 但是，通过编写自己的错误检查宏或内联函数，可以利用此相同的错误处理机制。 有关示例，请参阅主题"Visual C++ 扩展"。

