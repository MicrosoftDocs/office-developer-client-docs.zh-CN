---
title: GetChunk 方法 (ADO)
TOCTitle: GetChunk method (ADO)
ms:assetid: 1ef1c37a-8453-8d3b-251a-d16e0d519fd7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248979(v=office.15)
ms:contentKeyID: 48543629
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 27d6f2c9884441042d67615072738c7762f4f789
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949913"
---
# <a name="getchunk-method-ado"></a>GetChunk 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于返回较大文本或二进制数据 [Field](field-object-ado.md) 对象的全部内容或部分内容。

## <a name="syntax"></a>语法

*变量* = *字段*。GetChunk （*大小*）

## <a name="return-value"></a>返回值

返回 **变量型** 值。

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Size* |**长整型** 表达式，等于您要检索的字节数或字符数。|

## <a name="remarks"></a>备注

对 **Field** 对象使用 **GetChunk** 方法可以检索其部分或全部长整型二进制数据或字符数据。如果系统内存有限，则可以使用 **GetChunk** 方法对部分（而不是全部）长整型值进行操作。

**GetChunk** 调用返回的数据会分配给*变量*。如果 *Size* 大于剩余的数据，则 **GetChunk** 方法仅返回剩余的数据，而不会使用空格来填充*变量*。如果字段空白，则 **GetChunk** 方法返回一个 Null 值。

每个随后的 **GetChunk** 调用从上一个 **GetChunk** 调用停止的地方开始检索数据。但是，如果您从某个字段检索数据，随后设置或读取当前记录中另一个字段的值，ADO 将假定您已经从第一个字段检索完数据。如果再次对第一个字段调用 **GetChunk** 方法，ADO 将把调用解释为新的 **GetChunk** 操作，并从数据的开头开始读取。如果访问其他 [Recordset](recordset-object-ado.md) 对象中的字段，且这些字段不是第一个 **Recordset** 对象的克隆，则不会中断 **GetChunk** 操作。

如果将 **Field** 对象的 [Attributes](attributes-property-ado.md) 属性的 **adFldLong** 位设置为 **True** ，则可以对该字段使用 **GetChunk** 方法。

如果对 **Field** 对象使用 **GetChunk** 方法时没用当前记录，将发生错误 3021（无当前记录）。


> [!NOTE]
> [!注释] **GetChunk** 方法不会作用于 **Record** 对象的 [Field](record-object-ado.md) 对象。它不会执行任何操作，并且将生成运行时错误。


