---
title: 错误 (Access desktop database reference)
TOCTitle: Errors
ms:assetid: 42f5cab9-f32a-d789-10e8-8d73892427f6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249199(v=office.15)
ms:contentKeyID: 48544490
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 056ec0b34991348728898b4c0fc4a1a516a9913f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293355"
---
# <a name="errors"></a>Errors

**适用于**：Access 2013、Office 2013

任何涉及 ADO 对象的操作都可能生成一个或多个提供程序错误。 每个错误发生时，系统会将一个或多个 **Error** 对象放在 **Connection** 对象的 **Errors** 集合中。 有关在 ADO 应用程序中处理警告和错误的详细信息, 请参阅[第6章: 错误处理](chapter-6-error-handling.md)。

应用程序错误可以由单独的机制引发。例如，在 Visual Basic 中， **Err** 对象将包含应用程序级别的错误。

