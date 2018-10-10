---
title: Error 对象的 ActiveX 数据对象 (ADO)
TOCTitle: Error Object (ADO)
ms:assetid: 97e478bf-8b25-03a8-9358-abba5069cba3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249678(v=office.15)
ms:contentKeyID: 48546477
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e5fbefa5d857e7c239cbbcfc4502d60aabce347e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468087"
---
# <a name="error-object-ado"></a>Error 对象 (ADO)


**适用于**： Access 2013 |Office 2013

包含有关数据访问错误的详细信息，该错误与涉及提供程序的单个操作相关。

## <a name="remarks"></a>说明

任何涉及 ADO 对象的操作都可能生成一个或多个提供程序错误。每个错误发生时，系统会将一个或多个 **Error** 对象放在 [Connection](errors-collection-ado.md) 对象的 [Errors](connection-object-ado.md) 集合中。当另一个 ADO 操作生成错误时，系统会清空 **Errors** 集合，并在 **Errors** 集合中放入新的 **Error** 对象集。


> [!NOTE]
> <P>[!注释] 每个 <STRONG>Error</STRONG> 对象代表一个特定的提供程序错误，而不是 ADO 错误。ADO 错误是对运行时异常处理机制公开的。例如，在 Microsoft Visual Basic 中，出现特定于 ADO 的错误将触发一个 <STRONG>On Error</STRONG> 事件，该错误会显示在 <STRONG>Error</STRONG> 对象中。有关 ADO 错误的完整列表，请参阅 <A href="errorvalueenum.md">ErrorValueEnum</A> 主题。</P>



您可以阅读 **Error** 对象的属性，以便了解有关每种错误的特定详细信息。这些属性包括：

  - [Description](description-property-ado.md) 属性，其中包含有关错误的文本。这是默认属性。

  - [Number](number-property-ado.md) 属性，其中包含错误常量的 **Long** 类型整数值。

  - [Source](source-property-ado-error.md) 属性，该属性标识产生错误的对象。当对数据源发出请求后，在 **Errors** 集合中产生多个 **Error** 对象时，该属性尤其有用。

  - [SQLState](sqlstate-property-ado.md) 和 [NativeError](nativeerror-property-ado.md) 属性，这些属性从 SQL 数据源提供信息。

发生提供程序错误时，该错误会被放入 **Connection** 对象的 **Errors** 集合中。ADO 支持通过一个 ADO 操作返回多个错误，以允许特定于该提供程序的错误信息。若要获取错误处理程序中的这些丰富错误信息，可使用语言或环境的相应错误捕获功能，然后使用嵌套循环来枚举 **Errors** 集合中每个 **Error** 对象的属性。

**Microsoft Visual Basic 和 VBScript 用户**如果没有任何有效的**Connection**对象，您将需要从**Error**对象中检索错误信息。

就像提供程序一样，ADO 会在进行可能产生新提供程序错误的调用之前，会清除 **OLE Error Info** 对象。但是，只有在提供程序生成新错误时，或者调用 **Clear** 方法时，才会清空 **Connection** 对象的 [Errors](clear-method-ado.md) 集合。

某些属性和方法会返回警告（这些警告显示为 **Errors** 集合中的 **Error** 对象），但不会停止程序的执行。在对 [Recordset](resync-method-ado.md) 对象调用 [Resync](updatebatch-method-ado.md)、[UpdateBatch](cancelbatch-method-ado.md) 或 [CancelBatch](recordset-object-ado.md) 方法，对 [Connection](open-method-ado-connection.md) 对象调用 **Open** 方法，或对 [Recordset](filter-property-ado.md) 对象设置 **Filter** 属性之前，请对 **Errors** 集合调用 **Clear** 方法。这样，便可以读取 [Errors](count-property-ado.md) 集合的 **Count** 属性，以测试返回的警告。

