---
title: 错误 （访问桌面数据库参考 （英文）
TOCTitle: Errors
ms:assetid: 42f5cab9-f32a-d789-10e8-8d73892427f6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249199(v=office.15)
ms:contentKeyID: 48544490
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 38a89767de9fca317b3ed25fd81c7bf016a8ba46
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466740"
---
# <a name="errors"></a>错误


**适用于**： Access 2013 |Office 2013

任何涉及 ADO 对象的操作都可以生成提供程序错误。每个错误发生时，系统会将 **Error** 对象放在 **Connection** 对象的 **Errors** 集合中。有关在 ADO 应用程序中处理警告和错误的详细信息，请参阅 [第 6 章：错误处理](chapter-6-error-handling.md)。

应用程序错误可以由单独的机制引发。例如，在 Visual Basic 中， **Err** 对象将包含应用程序级别的错误。

