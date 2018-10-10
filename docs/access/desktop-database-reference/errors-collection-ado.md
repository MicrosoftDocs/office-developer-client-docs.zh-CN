---
title: Errors 集合 (ADO)
TOCTitle: Errors Collection (ADO)
ms:assetid: 76c234b8-7fec-11c5-275e-864d5d880ee7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249486(v=office.15)
ms:contentKeyID: 48545706
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b177df4fabd378b19866a15fa57312b87c39b524
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466056"
---
# <a name="errors-collection-ado"></a>Errors 集合 (ADO)


**适用于**： Access 2013 |Office 2013

包含为了响应与单个提供程序相关的失败提供程序而创建的所有 [Error](error-object-ado.md) 对象。

## <a name="remarks"></a>说明

任何涉及 ADO 对象的操作都可能生成一个或多个提供程序错误。每个错误发生时，系统会将一个或多个 **Error** 对象放在 **Connection** 对象的 [Errors](connection-object-ado.md) 集合中。当另一个 ADO 操作生成错误时，系统会清空 **Errors** 集合，并在 **Errors** 集合中放入新的 **Error** 对象集。

每个 **Error** 对象代表一个特定的提供程序错误，而不是 ADO 错误。ADO 错误是对运行时异常处理机制公开的。例如，在 Microsoft Visual Basic 中，出现特定于 ADO 的错误将触发一个 [onError](onerror-event-rds.md) 事件，该错误会显示在 **Err** 对象中。

不生成错误的 ADO 操作对 **Errors** 集合没有影响。使用 [Clear](clear-method-ado.md) 方法可手动清空 **Errors** 集合。

**Errors** 集合中的 **Error** 对象集描述在响应单个语句时生成的所有错误。通过枚举 **Errors** 集合中的特定错误，您的错误处理例程可以更精确地确定错误的原因和根源，并采取相应的步骤进行恢复。

某些属性和方法会返回警告（这些警告显示为 **Errors** 集合中的 **Error** 对象），但不会停止程序的执行。在对 [Recordset](resync-method-ado.md) 对象调用 [Resync](updatebatch-method-ado.md)、[UpdateBatch](cancelbatch-method-ado.md) 或 [CancelBatch](recordset-object-ado.md) 方法，对 [Connection](open-method-ado-connection.md) 对象调用 **Open** 方法，或对 [Recordset](filter-property-ado.md) 对象设置 **Filter** 属性之前，请对 **Errors** 集合调用 **Clear** 方法。这样，便可以读取 [Errors](count-property-ado.md) 集合的 **Count** 属性，以测试返回的警告。


> [!NOTE]
> <P>[!注释] 有关单个 ADO 操作如何生成多个错误的更详细解释，请参阅 <STRONG>Error</STRONG> 对象主题。</P>


