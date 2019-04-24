---
title: 处理 Visual C++ 中的错误
TOCTitle: Handling errors in Visual C++
ms:assetid: 75e15699-0c84-1dca-654e-f9ac465c2a30
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249483(v=office.15)
ms:contentKeyID: 48545684
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d0e76dc3cc9634a1531a34058bf7a1baf636c94c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292025"
---
# <a name="handling-errors-in-visual-c"></a>处理 Visual C++ 中的错误


**适用于**：Access 2013、Office 2013

在 COM 中, 大多数操作返回一个 HRESULT 返回代码, 该代码指示函数是否已成功完成。 import \#指令在每个 "raw" 方法或属性的周围生成包装代码, 并检查返回的 HRESULT。 如果 HRESULT 指示失败, 则包装代码会通过调用\_com\_问题\_errorex (), 并将 HRESULT 返回代码作为参数来引发 com 错误。 可以在**try-catch**块中捕获 COM error 对象。 (为了提高效率, 请捕获对\_com\_error 对象的引用。)

请记住，这些是 ADO 错误：它们是由于 ADO 操作失败而导致的。基础提供程序返回的错误将作为 **Connection** 对象的 **Errors** 集合中的 **Error** 对象出现。

\#import 指令仅为在 ADO 中声明的方法和属性创建错误处理例程。 但是，通过编写自己的错误检查宏或内联函数，可以利用此相同的错误处理机制。 有关示例，请参阅主题"Visual C++ 扩展"。

