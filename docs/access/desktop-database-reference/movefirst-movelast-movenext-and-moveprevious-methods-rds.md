---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious Methods (RDS)
ms:assetid: 32ef8fa9-c096-b4e7-3396-b88a6a9bd1a2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249101(v=office.15)
ms:contentKeyID: 48544092
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f4671e57e3edb44bc1c927ca11f2cf79e70c2699
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467411"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-rds"></a>MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (RDS)


**适用于**： Access 2013 |Office 2013

用于移动到指定的 [Recordset](recordset-object-ado.md) 对象中的第一个、最后一个、下一个或上一个记录。

## <a name="syntax"></a>语法

*DataControl*。记录集。{ MoveFirst |MoveLast |MoveNext |MovePrevious}

## <a name="parameters"></a>参数

  - *DataControl*

  - 一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。

## <a name="remarks"></a>说明

可以将 **Move** 方法用于 **RDS.DataControl** 对象以便在网页上数据绑定的控件中的数据记录中导航。例如，假设通过绑定到一个 **RDS.DataControl** 对象在网格中显示 **Recordset** 。然后，可以包括"第一个"、"最后一个"、"下一个"和"上一个"按钮，用户单击这些按钮可以分别移动到所显示的 **Recordset** 中的第一个、最后一个、下一个或上一个记录。通过在 onClick 过程中分别调用对应于"第一个"、"最后一个"、"下一个"和"上一个"按钮的 **RDS.DataControl** 对象的 **MoveFirst** 、 **MoveLast** 、 **MoveNext** 和 **MovePrevious** 方法来实现该目的。 [通讯簿示例](address-book-navigation-buttons.md)显示了如何执行该操作。

