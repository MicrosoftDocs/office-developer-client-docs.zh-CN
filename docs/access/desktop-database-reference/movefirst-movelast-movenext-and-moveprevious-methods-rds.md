---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious methods (RDS)
ms:assetid: 32ef8fa9-c096-b4e7-3396-b88a6a9bd1a2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249101(v=office.15)
ms:contentKeyID: 48544092
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b5631ce68a0479146e15ba74b41af5669d86175a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716031"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-rds"></a>MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)

**适用于**： Access 2013、 Office 2013

用于移动到指定的 [Recordset](recordset-object-ado.md) 对象中的第一个、最后一个、下一个或上一个记录。

## <a name="syntax"></a>语法

*DataControl*。记录集。{ MoveFirst |MoveLast |MoveNext |MovePrevious}

## <a name="parameters"></a>Parameters

|参数|说明|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|

## <a name="remarks"></a>备注

您可以使用**Move**方法与**rds.DataControl**对象浏览网页上的数据绑定控件中的数据记录。 

例如，假设通过绑定到一个 **RDS.DataControl** 对象在网格中显示 **Recordset** 。 然后，可以包括"第一个"、"最后一个"、"下一个"和"上一个"按钮，用户单击这些按钮可以分别移动到所显示的 **Recordset** 中的第一个、最后一个、下一个或上一个记录。 通过在 onClick 过程中分别调用对应于"第一个"、"最后一个"、"下一个"和"上一个"按钮的 **RDS.DataControl** 对象的 **MoveFirst** 、 **MoveLast** 、 **MoveNext** 和 **MovePrevious** 方法来实现该目的。 [通讯簿示例](address-book-navigation-buttons.md)显示了如何执行该操作。

