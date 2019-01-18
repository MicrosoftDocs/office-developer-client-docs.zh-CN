---
title: Clear 方法-ActiveX 数据对象 (ADO)
TOCTitle: Clear method (ADO)
ms:assetid: 5d51f42c-147b-1fcf-d05b-123e5714ecb7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249329(v=office.15)
ms:contentKeyID: 48545110
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b0d76480bdb5d5a3ab258e103a00707af303a4d3
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716857"
---
# <a name="clear-method-ado"></a>Clear 方法 (ADO)


**适用于**： Access 2013、 Office 2013

用于从 **Errors** 集合中删除所有 **Error** 对象。

## <a name="syntax"></a>语法

*错误*。清除

## <a name="remarks"></a>备注

可以对 **Errors** 集合使用 [Clear](errors-collection-ado.md) 方法，以从集合中删除所有现有 [Error](error-object-ado.md) 对象。如果发生错误，ADO 将自动清除 **Errors** 集合，并基于新的错误用 **Error** 对象填充集合。

某些属性和方法会返回警告，显示为 **Errors** 集合中的 **Error** 对象，但不会停止程序的执行。在对 [Recordset](resync-method-ado.md) 对象调用 [Resync](updatebatch-method-ado.md)、[UpdateBatch](cancelbatch-method-ado.md) 或 [CancelBatch](recordset-object-ado.md) 方法，对 [Connection](open-method-ado-connection.md) 对象调用 [Open](connection-object-ado.md) 方法，或对 [Recordset](filter-property-ado.md) 对象设置 **Filter** 属性之前，请对 **Errors** 集合调用 **Clear** 方法。这样，便可以读取 [Errors](count-property-ado.md) 集合的 **Count** 属性，以测试返回的警告。

